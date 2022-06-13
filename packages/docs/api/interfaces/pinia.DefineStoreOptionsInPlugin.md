---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / DefineStoreOptionsInPlugin

# Interface: DefineStoreOptionsInPlugin<Id, S, G, A\>

[pinia](../modules/pinia.md).DefineStoreOptionsInPlugin

Les `options` disponibles lors de la création d'un plugin pinia.

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](../modules/pinia.md#statetree) |
| `G` | `G` |
| `A` | `A` |

## Hiérarchie

- `Omit`<[`DefineStoreOptions`](pinia.DefineStoreOptions.md)<`Id`, `S`, `G`, `A`\>, ``"id"`` \| ``"actions"``\>

  ↳ **`DefineStoreOptionsInPlugin`**

## Propriétés

### actions

• **actions**: `A`

Objet extrait des actions. Ajouté par useStore() lorsque le store est construit
en utilisant l'API de configuration, sinon utilise celui passé à `defineStore()`.
La valeur par défaut est un objet vide si aucune action n'est définie.

#### Défini dans

[packages/pinia/src/types.ts:721](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L721)

___

### getters

• `Optional` **getters**: `G` & `ThisType`<`UnwrapRef`<`S`\> & [`_StoreWithGetters`](../modules/pinia.md#_storewithgetters)<`G`\> & [`PiniaCustomProperties`](pinia.PiniaCustomProperties.md)<`string`, [`StateTree`](../modules/pinia.md#statetree), [`_GettersTree`](../modules/pinia.md#_getterstree)<[`StateTree`](../modules/pinia.md#statetree)\>, [`_ActionsTree`](../modules/pinia.md#_actionstree)\>\> & [`_GettersTree`](../modules/pinia.md#_getterstree)<`S`\>

Objet optionnel de getters.

#### Héritée de

Omit.getters

#### Défini dans

[packages/pinia/src/types.ts:645](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L645)

## Méthodes

### hydrate

▸ `Optional` **hydrate**(`storeState`, `initialState`): `void`

Permet d'hydrater le store pendant le SSR lorsque des états complexes (comme des références côté client uniquement) sont utilisés dans la définition du store et que copier la valeur de `pinia.state` ne suffit pas.
et que copier la valeur de `pinia.state` n'est pas suffisant.

**`exemple`**
Si dans votre `state`, vous utilisez des `customRef`s, des `computed`s, ou des `ref`s qui ont une valeur différente sur le
serveur et le client, vous devez les hydrater manuellement. Par exemple, une référence personnalisée stockée dans le stockage local
local :

```ts
const useStore = defineStore('main', {
  state: () => ({
    n: useLocalStorage('key', 0)
  }),
  hydrate(storeState, initialState) {
    // @ts-expect-error: https://github.com/microsoft/TypeScript/issues/43826
    storeState.n = useLocalStorage('key', 0)
  }
})
```

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `storeState` | `UnwrapRef`<`S`\> | l'état actuel dans le store |
| `initialState` | `UnwrapRef`<`S`\> | initialState |

#### Renvoie

`void`

#### Héritée de

Omit.hydrate

#### Defined in

[packages/pinia/src/types.ts:685](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L685)

___

### state

▸ `Optional` **state**(): `S`

Fonction permettant de créer un nouvel état. **Il doit s'agir d'une fonction flèche** pour garantir
des typages corrects !

#### Renvoie

`S`

#### Héritée de

Omit.state

#### Défini dans

[packages/pinia/src/types.ts:640](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L640)
