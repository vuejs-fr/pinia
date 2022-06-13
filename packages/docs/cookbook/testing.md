# Tests des stores

Les stores seront, par conception, utilisés à de nombreux endroits et peuvent rendre les tests beaucoup plus difficiles qu'ils ne devraient l'être. Heureusement, ce n'est pas forcément le cas. Nous devons faire attention à trois choses lorsque nous testons des stores :

- L'instance `pinia` : Les stores ne peuvent pas fonctionner sans elle
- Les `actions` : la plupart du temps, elles contiennent la logique la plus complexe de nos stores. Ne serait-il pas agréable qu'elles soient simulées par défaut ?
- Les plugins : Si vous comptez sur des plugins, vous devrez aussi les installer pour les tests.

En fonction de ce que vous testez et de la manière dont vous le faites, nous devons nous occuper de ces trois éléments différemment :

- [Test des stores](#testing-stores)
  - [Test unitaire d'un store](#unit-testing-a-store)
  - [Composants des tests unitaires](#unit-testing-components)
    - [État initial](#initial-state)
    - [Personnalisation du comportement des actions](#customizing-behavior-of-actions)
    - [Spécification de la fonction createSpy](#specifying-the-createspy-function)
    - [Getters de simulation](#mocking-getters)
    - [Plugins pour Pinia](#pinia-plugins)
  - [Les tests E2E](#e2e-tests)
  - [Composants de test unitaire (Vue 2)](#unit-test-components-vue-2)

## Test unitaire d'un store

Pour tester un store, la partie la plus importante est de créer une instance `pinia` :

```js
// counterStore.spec.ts
import { setActivePinia, createPinia } from "pinia";
import { useCounter } from "../src/stores/counter";

describe("Counter Store", () => {
  beforeEach(() => {
    // crée un nouveau pinia et le rend actif pour qu'il soit automatiquement récupéré automatiquement
    // par tout appel à useStore() sans avoir à le lui passer
    // `useStore(pinia)`
    setActivePinia(createPinia());
  });

  it("increments", () => {
    const counter = useCounter();
    expect(counter.n).toBe(0);
    counter.increment();
    expect(counter.n).toBe(1);
  });

  it("increments by amount", () => {
    const counter = useCounter();
    counter.increment(10);
    expect(counter.n).toBe(10);
  });
});
```

Si vous avez des plugins de store, il y a une chose importante à savoir : **les plugins ne seront pas utilisés tant que `pinia` n'est pas installé dans une App**. Ceci peut être résolu en créant une application vide ou une fausse application :

```js
import { setActivePinia, createPinia } from "pinia";
import { createApp } from "vue";
import { somePlugin } from "../src/stores/plugin";

// même code que ci-dessus...

// vous n'avez pas besoin de créer une application par test
const app = createApp({});
beforeEach(() => {
  const pinia = createPinia().use(somePlugin);
  app.use(pinia);
  setActivePinia(pinia);
});
```

## Unit testing components

Cela peut être réalisé avec `createTestingPinia()`, qui renvoie une instance de pinia conçue pour faciliter les tests unitaires des composants.

Commencez par installer `@pinia/testing` :

```shell
npm i -D @pinia/testing
```

Et assurez-vous de créer une pinia de test dans vos tests lorsque vous montez un composant :

```js
import { mount } from "@vue/test-utils";
import { createTestingPinia } from "@pinia/testing";

const wrapper = mount(Counter, {
  global: {
    plugins: [createTestingPinia()],
  },
});

const store = useSomeStore(); // utilise le test pinia !

// l'état peut être directement manipulé
store.name = "my new name";
// peut également être fait par le biais du patch
store.$patch({ name: "new name" });
expect(store.name).toBe("new name");

// Les actions sont stubées par défaut, ce qui signifie qu'elles n'exécutent pas leur code par défaut.
// Voir ci-dessous pour personnaliser ce comportement.
store.someAction();

expect(store.someAction).toHaveBeenCalledTimes(1);
expect(store.someAction).toHaveBeenLastCalledWith();
```

Veuillez noter que si vous utilisez Vue 2, `@vue/test-utils` nécessite une [configuration légèrement différente](#unit-test-components-vue-2).

### État initial

Vous pouvez définir l'état initial de **tous vos stores** lors de la création d'un pinia de test en passant un objet `initialState`. Cet objet sera utilisé par le pinia de test pour _patch_ les stores lorsqu'ils sont créés. Disons que vous voulez initialiser l'état de ce store :

```ts
import { defineStore } from "pinia";

const useCounterStore = defineStore("counter", {
  state: () => ({ n: 0 }),
  // ...
});
```

Puisque le store est nommé _"counter"_, vous devez ajouter un objet correspondant à `initialState` :

```ts
// somewhere in your test
const wrapper = mount(Counter, {
  global: {
    plugins: [
      createTestingPinia({
        initialState: {
          counter: { n: 20 }, // démarrer le compteur à 20 au lieu de 0
        },
      }),
    ],
  },
});

const store = useSomeStore(); // utilise le test pinia !
store.n; // 20
```

### Personnalisation du comportement des actions

Le module `createTestingPinia` remplace toutes les actions des stores, sauf indication contraire. Cela vous permet de tester vos composants et vos stores séparément.

Si vous voulez inverser ce comportement et exécuter normalement vos actions pendant les tests, spécifiez `stubActions : false` en appelant `createTestingPinia` :

```js
const wrapper = mount(Counter, {
  global: {
    plugins: [createTestingPinia({ stubActions: false })],
  },
});

const store = useSomeStore();

// Cet appel va maintenant exécuter l'implémentation définie par le store.
store.someAction();

// ...mais il est toujours entouré d'un espion, ce qui permet d'inspecter les appels.
expect(store.someAction).toHaveBeenCalledTimes(1);
```

### Spécifier la fonction createSpy

Lorsque vous utilisez Jest, ou vitest avec `globals : true`, `createTestingPinia` stubs automatiquement les actions utilisant la fonction spy basée sur le framework de test existant (`jest.fn` ou `vitest.fn`). Si vous utilisez un autre framework, vous devrez fournir une option [createSpy](/api/interfaces/pinia_testing.TestingOptions.html#createspy) :

```js
import sinon from "sinon";

createTestingPinia({
  createSpy: sinon.spy, // utiliser l'espion de Sinon pour emballer les actions
});
```

Vous trouverez d'autres exemples dans [les tests du paquet testing](https://github.com/vuejs/pinia/blob/v2/packages/testing/src/testing.spec.ts).

### Simuler les getters

Par défaut, tous les getter seront calculés comme une utilisation normale, mais vous pouvez forcer manuellement une valeur en définissant le getter à ce que vous voulez :

```ts
import { defineStore } from "pinia";
import { createTestingPinia } from "@pinia/testing";

const useCounter = defineStore("counter", {
  state: () => ({ n: 1 }),
  getters: {
    double: (state) => state.n * 2,
  },
});

const pinia = createTestingPinia();
const counter = useCounter(pinia);

counter.double = 3; // 🪄 les getters ne sont accessibles en écriture que dans les tests

// mettre à undefined pour réinitialiser le comportement par défaut
// @ts-expect-error : généralement c'est un nombre
counter.double = undefined;
counter.double; // 2 (=1 x 2)
```

### Les Plugins Pinia

Si vous avez des plugins pinia, assurez-vous de les passer lors de l'appel à `createTestingPinia()` afin qu'ils soient correctement appliqués. **Ne les ajoutez pas avec `testingPinia.use(MyPlugin)`** comme vous le feriez avec un pinia normal :

```js
import { createTestingPinia } from "@pinia/testing";
import { somePlugin } from "../src/stores/plugin";

// dans un test
const wrapper = mount(Counter, {
  global: {
    plugins: [
      createTestingPinia({
        stubActions: false,
        plugins: [somePlugin],
      }),
    ],
  },
});
```

## Tests E2E

Quand il s'agit de pinia, vous n'avez pas besoin de changer quoi que ce soit pour les tests e2e, c'est tout l'intérêt des tests e2e ! Vous pourriez peut-être tester les requêtes HTTP, mais cela dépasse largement le cadre de ce guide 😄.

## Composants de test unitaire (Vue 2)

Si vous utilisez [Vue Test Utils 1] (https://v1.test-utils.vuejs.org/), installez Pinia sur un `localVue` :

```js
import { PiniaVuePlugin } from "pinia";
import { createLocalVue, mount } from "@vue/test-utils";
import { createTestingPinia } from "@pinia/testing";

const localVue = createLocalVue();
localVue.use(PiniaVuePlugin);

const wrapper = mount(Counter, {
  localVue,
  pinia: createTestingPinia(),
});

const store = useSomeStore(); // utilise le test pinia !
```
