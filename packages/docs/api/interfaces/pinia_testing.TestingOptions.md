---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[API Documentation](../index.md) / [@pinia/testing](../modules/pinia_testing.md) / TestingOptions

# Interface: TestingOptions

[@pinia/testing](../modules/pinia_testing.md).TestingOptions

## Propriétés

### fakeApp

• `Optional` **fakeApp**: `boolean`

Crée une application vide et appelle `app.use(pinia)` avec le test créé
pinia. Ceci vous permet d'utiliser des plugins tout en stockant des tests unitaires, car
Les plugins **attendent que pinia soit installé pour être exécutés**.
La valeur par défaut est false.

#### Défini dans

[packages/testing/src/testing.ts:57](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L57)

___

### initialState

• `Optional` **initialState**: [`StateTree`](../modules/pinia.md#statetree)

Permet de définir un état initial partiel de tous vos stores. Cet état est appliqué après la création d'un store,
ce qui vous permet de ne définir que les quelques propriétés requises dans votre test.

#### Défini dans

[packages/testing/src/testing.ts:27](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L27)

___

### plugins

• `Optional` **plugins**: [`PiniaPlugin`](pinia.PiniaPlugin.md)[]

Les plugins à installer avant le plugin de test. Ajoutez tous les plugins utilisés dans
votre application qui sera utilisée lors des tests.

#### Défini dans

[packages/testing/src/testing.ts:33](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L33)

___

### stubActions

• `Optional` **stubActions**: `boolean`

Lorsqu'il est défini à false, les actions sont seulement espionnées, elles sont toujours exécutées. Lorsque
défini à true, les actions seront remplacées par des espions, ce qui aura pour conséquence que leur code
code ne sera pas exécuté. La valeur par défaut est true. NOTE : lorsque vous fournissez `createSpy()`,
il rendra **seulement** l'argument `fn` `undefined`. Vous devez toujours
gérer cela dans `createSpy()`.

#### Défini dans

[packages/testing/src/testing.ts:42](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L42)

___

### stubPatch

• `Optional` **stubPatch**: `boolean`

Lorsqu'il a la valeur true, les appels à `$patch()` ne changeront pas l'état. La valeur par défaut est
false. NOTE : lorsque vous fournissez `createSpy()`, il rendra **seulement** l'argument `fn`
l'argument `undefined`. Vous devez toujours le gérer dans `createSpy()`.

#### Défini dans

[packages/testing/src/testing.ts:49](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L49)

## Méthodes

### createSpy

▸ `Optional` **createSpy**(`fn?`): (...`args`: `any`[]) => `any`

Fonction utilisée pour créer un espion pour les actions et `$patch()`. Pré-configuré
avec `jest.fn()` dans les projets jest ou `vi.fn()` dans les projets vitest.

#### Paramètres

| Name | Type |
| :------ | :------ |
| `fn?` | (...`args`: `any`[]) => `any` |

#### Renvoie

`fn`

▸ (...`args`): `any`

##### Paramètres

| Name | Type |
| :------ | :------ |
| `...args` | `any`[] |

##### Renvoie

`any`

#### Défini dans

[packages/testing/src/testing.ts:63](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L63)
