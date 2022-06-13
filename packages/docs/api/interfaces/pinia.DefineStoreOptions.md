---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / DefineStoreOptions

# Interface: DefineStoreOptions<Id, S, G, A\>

[pinia](../modules/pinia.md).DefineStoreOptions

Paramètre d'options de `defineStore()` pour les stores d'options. Peut être étendu pour
stores avec l'API des plugins. @Voir [DefineStoreOptionsBase](pinia.DefineStoreOptionsBase.md).

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](../modules/pinia.md#statetree) |
| `G` | `G` |
| `A` | `A` |

## Hiérarchie

- [`DefineStoreOptionsBase`](pinia.DefineStoreOptionsBase.md)<`S`, [`Store`](../modules/pinia.md#store)<`Id`, `S`, `G`, `A`\>\>

  ↳ **`DefineStoreOptions`**

## Propriétés

### actions

• `Optional` **actions**: `A` & `ThisType`<`A` & `UnwrapRef`<`S`\> & [`_StoreWithState`](pinia._StoreWithState.md)<`Id`, `S`, `G`, `A`\> & [`_StoreWithGetters`](../modules/pinia.md#_storewithgetters)<`G`\> & [`PiniaCustomProperties`](pinia.PiniaCustomProperties.md)<`string`, [`StateTree`](../modules/pinia.md#statetree), [`_GettersTree`](../modules/pinia.md#_getterstree)<[`StateTree`](../modules/pinia.md#statetree)\>, [`_ActionsTree`](../modules/pinia.md#_actionstree)\>\>

Objet facultatif des actions.

#### Défini dans

[packages/pinia/src/types.ts:652](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L652)

___

### getters

• `Optional` **getters**: `G` & `ThisType`<`UnwrapRef`<`S`\> & [`_StoreWithGetters`](../modules/pinia.md#_storewithgetters)<`G`\> & [`PiniaCustomProperties`](pinia.PiniaCustomProperties.md)<`string`, [`StateTree`](../modules/pinia.md#statetree), [`_GettersTree`](../modules/pinia.md#_getterstree)<[`StateTree`](../modules/pinia.md#statetree)\>, [`_ActionsTree`](../modules/pinia.md#_actionstree)\>\> & [`_GettersTree`](../modules/pinia.md#_getterstree)<`S`\>

Objet optionnel de getters.

#### Défini dans

[packages/pinia/src/types.ts:645](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L645)

___

### id

• **id**: `Id`

Clé de chaîne unique permettant d'identifier le store dans l'application.

#### Défini dans

[packages/pinia/src/types.ts:634](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L634)

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

#### Défini dans

[packages/pinia/src/types.ts:685](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L685)

___

### state

▸ `Optional` **state**(): `S`

Fonction permettant de créer un nouvel état. **Il doit s'agir d'une fonction flèche** pour garantir
des typages corrects !

#### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:640](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L640)
