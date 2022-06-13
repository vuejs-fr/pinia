---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / pinia

# Module: pinia

## Enumérations

- [MutationType](../enums/pinia.MutationType.md)

## Interfaces

- [DefineSetupStoreOptions](../interfaces/pinia.DefineSetupStoreOptions.md)
- [DefineStoreOptions](../interfaces/pinia.DefineStoreOptions.md)
- [DefineStoreOptionsBase](../interfaces/pinia.DefineStoreOptionsBase.md)
- [DefineStoreOptionsInPlugin](../interfaces/pinia.DefineStoreOptionsInPlugin.md)
- [MapStoresCustomization](../interfaces/pinia.MapStoresCustomization.md)
- [Pinia](../interfaces/pinia.Pinia.md)
- [PiniaCustomProperties](../interfaces/pinia.PiniaCustomProperties.md)
- [PiniaCustomStateProperties](../interfaces/pinia.PiniaCustomStateProperties.md)
- [PiniaPlugin](../interfaces/pinia.PiniaPlugin.md)
- [PiniaPluginContext](../interfaces/pinia.PiniaPluginContext.md)
- [StoreDefinition](../interfaces/pinia.StoreDefinition.md)
- [StoreProperties](../interfaces/pinia.StoreProperties.md)
- [SubscriptionCallbackMutationDirect](../interfaces/pinia.SubscriptionCallbackMutationDirect.md)
- [SubscriptionCallbackMutationPatchFunction](../interfaces/pinia.SubscriptionCallbackMutationPatchFunction.md)
- [SubscriptionCallbackMutationPatchObject](../interfaces/pinia.SubscriptionCallbackMutationPatchObject.md)
- [\_StoreOnActionListenerContext](../interfaces/pinia._StoreOnActionListenerContext.md)
- [\_StoreWithState](../interfaces/pinia._StoreWithState.md)
- [\_SubscriptionCallbackMutationBase](../interfaces/pinia._SubscriptionCallbackMutationBase.md)

## Type d'alias

### PiniaStorePlugin

Ƭ **PiniaStorePlugin**: [`PiniaPlugin`](../interfaces/pinia.PiniaPlugin.md)

Plugin pour étendre chaque store.

**`déprécié`** utilisez plutôt PiniaPlugin

#### Défini dans

[packages/pinia/src/rootStore.ts:149](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L149)

___

### StateTree

Ƭ **StateTree**: `Record`<`string` \| `number` \| `symbol`, `any`\>

État générique d'un store

#### Défini dans

[packages/pinia/src/types.ts:13](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L13)

___

### Store

Ƭ **Store**<`Id`, `S`, `G`, `A`\>: [`_StoreWithState`](../interfaces/pinia._StoreWithState.md)<`Id`, `S`, `G`, `A`\> & `UnwrapRef`<`S`\> & [`_StoreWithGetters`](pinia.md#_storewithgetters)<`G`\> & [`_ActionsTree`](pinia.md#_actionstree) extends `A` ? {} : `A` & [`PiniaCustomProperties`](../interfaces/pinia.PiniaCustomProperties.md)<`Id`, `S`, `G`, `A`\> & `PiniaCustomStateProperties`<`S`\>

Type de store pour construire un store.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` = `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) = {} |
| `G` | {} |
| `A` | {} |

#### Défini dans

[packages/pinia/src/types.ts:470](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L470)

___

### StoreActions

Ƭ **StoreActions**<`SS`\>: `SS` extends [`Store`](pinia.md#store)<`string`, [`StateTree`](pinia.md#statetree), [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, infer A\> ? `A` : [`_ExtractActionsFromSetupStore`](pinia.md#_extractactionsfromsetupstore)<`SS`\>

Extrayez les actions d'un type de store. Fonctionne avec un store de configuration ou un
store d'options.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/store.ts:729](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L729)

___

### StoreGeneric

Ƭ **StoreGeneric**: [`Store`](pinia.md#store)<`string`, [`StateTree`](pinia.md#statetree), [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, [`_ActionsTree`](pinia.md#_actionstree)\>

Version générique et non sécurisée de Store. N'échoue pas lors d'accès avec des
chaînes de caractères, ce qui facilite grandement l'écriture de fonctions génériques qui ne se
du type de store transmis.

#### Défini dans

[packages/pinia/src/types.ts:489](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L489)

___

### StoreGetters

Ƭ **StoreGetters**<`SS`\>: `SS` extends [`Store`](pinia.md#store)<`string`, [`StateTree`](pinia.md#statetree), infer G, [`_ActionsTree`](pinia.md#_actionstree)\> ? [`_StoreWithGetters`](pinia.md#_storewithgetters)<`G`\> : [`_ExtractGettersFromSetupStore`](pinia.md#_extractgettersfromsetupstore)<`SS`\>

Extrait les getters d'un type de store. Fonctionne à la fois avec un store de configuration et un store d'options.
store d'options.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/store.ts:742](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L742)

___

### StoreOnActionListener

Ƭ **StoreOnActionListener**<`Id`, `S`, `G`, `A`\>: (`context`: [`StoreOnActionListenerContext`](pinia.md#storeonactionlistenercontext)<`Id`, `S`, `G`, {} extends `A` ? [`_ActionsTree`](pinia.md#_actionstree) : `A`\>) => `void`

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | `G` |
| `A` | `A` |

#### Type declaration

▸ (`context`): `void`

Argument of `store.$onAction()`

##### Paramètres

| Name | Type |
| :------ | :------ |
| `context` | [`StoreOnActionListenerContext`](pinia.md#storeonactionlistenercontext)<`Id`, `S`, `G`, {} extends `A` ? [`_ActionsTree`](pinia.md#_actionstree) : `A`\> |

##### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:243](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L243)

___

### StoreOnActionListenerContext

Ƭ **StoreOnActionListenerContext**<`Id`, `S`, `G`, `A`\>: [`_ActionsTree`](pinia.md#_actionstree) extends `A` ? [`_StoreOnActionListenerContext`](../interfaces/pinia._StoreOnActionListenerContext.md)<[`StoreGeneric`](pinia.md#storegeneric), `string`, [`_ActionsTree`](pinia.md#_actionstree)\> : { [Name in keyof A]: Name extends string ? \_StoreOnActionListenerContext<Store<Id, S, G, A\>, Name, A\> : never }[keyof `A`]

Objet contextuel passé aux callbacks de `store.$onAction(context => {})`
TODO: doit avoir seulement l'Id, le Store et les Actions pour générer l'objet approprié.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | `G` |
| `A` | `A` |

#### Défini dans

[packages/pinia/src/types.ts:227](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L227)

___

### StoreState

Ƭ **StoreState**<`SS`\>: `SS` extends [`Store`](pinia.md#store)<`string`, infer S, [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, [`_ActionsTree`](pinia.md#_actionstree)\> ? `UnwrapRef`<`S`\> : [`_ExtractStateFromSetupStore`](pinia.md#_extractstatefromsetupstore)<`SS`\>

Extrait l'état d'un type de store. Fonctionne à la fois avec un store de configuration et un store d'options.
store d'options. Notez que cela déballe les refs.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/store.ts:755](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L755)

___

### SubscriptionCallback

Ƭ **SubscriptionCallback**<`S`\>: (`mutation`: [`SubscriptionCallbackMutation`](pinia.md#subscriptioncallbackmutation)<`S`\>, `state`: `UnwrapRef`<`S`\>) => `void`

#### Paramètres du type

| Name |
| :------ |
| `S` |

#### Type declaration

▸ (`mutation`, `state`): `void`

Rappel d'un abonnement

##### Paramètres

| Name | Type |
| :------ | :------ |
| `mutation` | [`SubscriptionCallbackMutation`](pinia.md#subscriptioncallbackmutation)<`S`\> |
| `state` | `UnwrapRef`<`S`\> |

##### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:148](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L148)

___

### SubscriptionCallbackMutation

Ƭ **SubscriptionCallbackMutation**<`S`\>: [`SubscriptionCallbackMutationDirect`](../interfaces/pinia.SubscriptionCallbackMutationDirect.md) \| [`SubscriptionCallbackMutationPatchObject`](../interfaces/pinia.SubscriptionCallbackMutationPatchObject.md)<`S`\> \| [`SubscriptionCallbackMutationPatchFunction`](../interfaces/pinia.SubscriptionCallbackMutationPatchFunction.md)

Objet de contexte transmis à un appel d'abonnement.

#### Paramètres du type

| Name |
| :------ |
| `S` |

#### Défini dans

[packages/pinia/src/types.ts:140](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L140)

___

### \_ActionsTree

Ƭ **\_ActionsTree**: `Record`<`string`, [`_Method`](pinia.md#_method)\>

Type d'un objet d'actions. Pour usage interne uniquement.
Pour usage interne **seulement**

#### Défini dans

[packages/pinia/src/types.ts:555](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L555)

___

### \_Awaited

Ƭ **\_Awaited**<`T`\>: `T` extends ``null`` \| `undefined` ? `T` : `T` extends `object` & { `then`: (`onfulfilled`: `F`) => `any`  } ? `F` extends (`value`: infer V, ...`args`: `any`) => `any` ? [`_Awaited`](pinia.md#_awaited)<`V`\> : `never` : `T`

#### Paramètres du type

| Name |
| :------ |
| `T` |

#### Défini dans

[packages/pinia/src/types.ts:164](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L164)

___

### \_DeepPartial

Ƭ **\_DeepPartial**<`T`\>: { [K in keyof T]?: \_DeepPartial<T[K]\> }

`Partiel<T>` récursif. Utilisé par {@link Store.$patch}.

Pour un usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `T` |

#### Défini dans

[packages/pinia/src/types.ts:35](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L35)

___

### \_ExtractActionsFromSetupStore

Ƭ **\_ExtractActionsFromSetupStore**<`SS`\>: `SS` extends `undefined` \| `void` ? {} : [`_ExtractActionsFromSetupStore_Keys`](pinia.md#_extractactionsfromsetupstore_keys)<`SS`\> extends keyof `SS` ? `Pick`<`SS`, [`_ExtractActionsFromSetupStore_Keys`](pinia.md#_extractactionsfromsetupstore_keys)<`SS`\>\> : `never`

Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:599](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L599)

___

### \_ExtractActionsFromSetupStore\_Keys

Ƭ **\_ExtractActionsFromSetupStore\_Keys**<`SS`\>: keyof { [K in keyof SS as SS[K] extends \_Method ? K : never]: any }

Type qui permet le refactoring à travers l'IDE.
Pour un usage interne **seulement**.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:569](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L569)

___

### \_ExtractGettersFromSetupStore

Ƭ **\_ExtractGettersFromSetupStore**<`SS`\>: `SS` extends `undefined` \| `void` ? {} : [`_ExtractGettersFromSetupStore_Keys`](pinia.md#_extractgettersfromsetupstore_keys)<`SS`\> extends keyof `SS` ? [`_UnwrapAll`](pinia.md#_unwrapall)<`Pick`<`SS`, [`_ExtractGettersFromSetupStore_Keys`](pinia.md#_extractgettersfromsetupstore_keys)<`SS`\>\>\> : `never`

Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:608](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L608)

___

### \_ExtractGettersFromSetupStore\_Keys

Ƭ **\_ExtractGettersFromSetupStore\_Keys**<`SS`\>: keyof { [K in keyof SS as SS[K] extends ComputedRef ? K : never]: any }

Type qui permet le refactoring à travers l'IDE.
Pour un usage interne **seulement**.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:577](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L577)

___

### \_ExtractStateFromSetupStore

Ƭ **\_ExtractStateFromSetupStore**<`SS`\>: `SS` extends `undefined` \| `void` ? {} : [`_ExtractStateFromSetupStore_Keys`](pinia.md#_extractstatefromsetupstore_keys)<`SS`\> extends keyof `SS` ? [`_UnwrapAll`](pinia.md#_unwrapall)<`Pick`<`SS`, [`_ExtractStateFromSetupStore_Keys`](pinia.md#_extractstatefromsetupstore_keys)<`SS`\>\>\> : `never`

Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:590](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L590)

___

### \_ExtractStateFromSetupStore\_Keys

Ƭ **\_ExtractStateFromSetupStore\_Keys**<`SS`\>: keyof { [K in keyof SS as SS[K] extends \_Method \| ComputedRef ? never : K]: any }

Type qui permet le refactoring à travers l'IDE.
Pour un usage interne **seulement**.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:561](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L561)

___

### \_GettersTree

Ƭ **\_GettersTree**<`S`\>: `Record`<`string`, (`state`: `UnwrapRef`<`S`\> & `UnwrapRef`<`PiniaCustomStateProperties`<`S`\>\>) => `any` \| () => `any`\>

Type d'un objet de Getters qui déduit l'argument.
Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `S` | extends [`StateTree`](pinia.md#statetree) |

#### Défini dans

[packages/pinia/src/types.ts:545](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L545)

___

### \_MapActionsObjectReturn

Ƭ **\_MapActionsObjectReturn**<`A`, `T`\>: { [key in keyof T]: A[T[key]] }

Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `A` | `A` |
| `T` | extends `Record`<`string`, keyof `A`\> |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:297](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L297)

___

### \_MapActionsReturn

Ƭ **\_MapActionsReturn**<`A`\>: { [key in keyof A]: A[key] }

Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `A` |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:290](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L290)

___

### \_MapStateObjectReturn

Ƭ **\_MapStateObjectReturn**<`Id`, `S`, `G`, `A`, `T`\>: { [key in keyof T]: Function }

Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `T` | extends `Record`<`string`, keyof `S` \| keyof `G` \| (`store`: [`Store`](pinia.md#store)<`Id`, `S`, `G`, `A`\>) => `any`\> = {} |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:141](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L141)

___

### \_MapStateReturn

Ƭ **\_MapStateReturn**<`S`, `G`, `Keys`\>: { [key in Keys]: Function }

Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `Keys` | extends keyof `S` \| keyof `G` = keyof `S` \| keyof `G` |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:125](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L125)

___

### \_MapWritableStateObjectReturn

Ƭ **\_MapWritableStateObjectReturn**<`S`, `T`\>: { [key in keyof T]: Object }

Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `T` | extends `Record`<`string`, keyof `S`\> |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:422](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L422)

___

### \_MapWritableStateReturn

Ƭ **\_MapWritableStateReturn**<`S`\>: { [key in keyof S]: Object }

Pour usage interne **seulement**

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `S` | extends [`StateTree`](pinia.md#statetree) |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:412](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L412)

___

### \_Method

Ƭ **\_Method**: (...`args`: `any`[]) => `any`

#### Type declaration

▸ (...`args`): `any`

Generic type for a function that can infer arguments and return type

Pour usage interne **seulement**

##### Paramètres

| Name | Type |
| :------ | :------ |
| `...args` | `any`[] |

##### Renvoie

`any`

#### Défini dans

[packages/pinia/src/types.ts:439](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L439)

___

### \_Spread

Ƭ **\_Spread**<`A`\>: `A` extends [infer L, ...infer R] ? [`_StoreObject`](pinia.md#_storeobject)<`L`\> & [`_Spread`](pinia.md#_spread)<`R`\> : `unknown`

Pour usage interne **seulement**.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `A` | extends readonly `any`[] |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:53](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L53)

___

### \_StoreObject

Ƭ **\_StoreObject**<`S`\>: `S` extends [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<infer Ids, infer State, infer Getters, infer Actions\> ? { [Id in \`${Ids}${MapStoresCustomization extends Record<"suffix", string\> ? MapStoresCustomization["suffix"] : "Store"}\`]: Function } : {}

Pour usage interne **seulement**.

#### Paramètres du type

| Name |
| :------ |
| `S` |

#### Défini dans

[packages/pinia/src/mapHelpers.ts:25](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L25)

___

### \_StoreWithActions

Ƭ **\_StoreWithActions**<`A`\>: { [k in keyof A]: A[k] extends Function ? Function : never }

Store augmented for actions. For internal usage only.
Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `A` |

#### Défini dans

[packages/pinia/src/types.ts:451](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L451)

___

### \_StoreWithGetters

Ƭ **\_StoreWithGetters**<`G`\>: { readonly [k in keyof G]: G[k] extends Function ? R : UnwrapRef<G[k]\> }

Store augmented with getters. For internal usage only.
Pour usage interne **seulement**

#### Paramètres du type

| Name |
| :------ |
| `G` |

#### Défini dans

[packages/pinia/src/types.ts:461](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L461)

___

### \_UnwrapAll

Ƭ **\_UnwrapAll**<`SS`\>: { [K in keyof SS]: UnwrapRef<SS[K]\> }

Type qui permet le refactoring à travers l'IDE.
Pour un usage interne **seulement**.

#### Paramètres du type

| Name |
| :------ |
| `SS` |

#### Défini dans

[packages/pinia/src/types.ts:585](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L585)

## Variables

### PiniaVuePlugin

• `Const` **PiniaVuePlugin**: `Plugin`

Plugin Vue 2 qui doit être installé pour que pinia fonctionne. Remarque **vous n'avez pas besoin de
ce plugin si vous utilisez Nuxt.js**. Utilisez le `buildModule` à la place :
https://pinia.vuejs.org/ssr/nuxt.html.

**`example`**
```js
import Vue from 'vue'
import { PiniaVuePlugin, createPinia } from 'pinia'

Vue.use(PiniaVuePlugin)
const pinia = createPinia()

new Vue({
  el: '#app',
  // ...
  pinia,
})
```

**`param`** `Vue` imported from 'vue'.

#### Défini dans

[packages/pinia/src/vue2-plugin.ts:28](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/vue2-plugin.ts#L28)

## FOnctions

### acceptHMRUpdate

▸ **acceptHMRUpdate**(`initialUseStore`, `hot`): (`newModule`: `any`) => `any`

Crée une fonction _accept_ à passer à `import.meta.hot` dans les applications Vite.

**`example`**
```js
const useUser = defineStore(...)
if (import.meta.hot) {
  import.meta.hot.accept(acceptHMRUpdate(useUser, import.meta.hot))
}
```

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `initialUseStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`string`, [`StateTree`](pinia.md#statetree), [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, [`_ActionsTree`](pinia.md#_actionstree)\> | return of the defineStore to hot update |
| `hot` | `any` | `import.meta.hot` |

#### Renvoie

`fn`

▸ (`newModule`): `any`

##### Paramètres

| Name | Type |
| :------ | :------ |
| `newModule` | `any` |

##### Renvoie

`any`

#### Défini dans

[packages/pinia/src/hmr.ts:73](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/hmr.ts#L73)

___

### createPinia

▸ **createPinia**(): [`Pinia`](../interfaces/pinia.Pinia.md)

Creates a Pinia instance to be used by the application

#### Renvoie

[`Pinia`](../interfaces/pinia.Pinia.md)

#### Défini dans

[packages/pinia/src/createPinia.ts:10](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/createPinia.ts#L10)

___

### defineStore

▸ **defineStore**<`Id`, `S`, `G`, `A`\>(`id`, `options`): [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\>

Crée une fonction `useStore` qui récupère l'instance du store.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) = {} |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> = {} |
| `A` | {} |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `Id` | id of the store (must be unique) |
| `options` | `Omit`<[`DefineStoreOptions`](../interfaces/pinia.DefineStoreOptions.md)<`Id`, `S`, `G`, `A`\>, ``"id"``\> | options to define the store |

#### Renvoie

[`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\>

#### Défini dans

[packages/pinia/src/store.ts:778](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L778)

▸ **defineStore**<`Id`, `S`, `G`, `A`\>(`options`): [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\>

Crée une fonction `useStore` qui récupère l'instance du store.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) = {} |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> = {} |
| `A` | {} |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [`DefineStoreOptions`](../interfaces/pinia.DefineStoreOptions.md)<`Id`, `S`, `G`, `A`\> | options to define the store |

#### Renvoie

[`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\>

#### Défini dans

[packages/pinia/src/store.ts:794](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L794)

▸ **defineStore**<`Id`, `SS`\>(`id`, `storeSetup`, `options?`): [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, [`_ExtractStateFromSetupStore`](pinia.md#_extractstatefromsetupstore)<`SS`\>, [`_ExtractGettersFromSetupStore`](pinia.md#_extractgettersfromsetupstore)<`SS`\>, [`_ExtractActionsFromSetupStore`](pinia.md#_extractactionsfromsetupstore)<`SS`\>\>

Crée une fonction `useStore` qui récupère l'instance du store.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `SS` | `SS` |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `Id` | id of the store (must be unique) |
| `storeSetup` | () => `SS` | function that defines the store |
| `options?` | [`DefineSetupStoreOptions`](../interfaces/pinia.DefineSetupStoreOptions.md)<`Id`, [`_ExtractStateFromSetupStore`](pinia.md#_extractstatefromsetupstore)<`SS`\>, [`_ExtractGettersFromSetupStore`](pinia.md#_extractgettersfromsetupstore)<`SS`\>, [`_ExtractActionsFromSetupStore`](pinia.md#_extractactionsfromsetupstore)<`SS`\>\> | extra options |

#### Renvoie

[`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, [`_ExtractStateFromSetupStore`](pinia.md#_extractstatefromsetupstore)<`SS`\>, [`_ExtractGettersFromSetupStore`](pinia.md#_extractgettersfromsetupstore)<`SS`\>, [`_ExtractActionsFromSetupStore`](pinia.md#_extractactionsfromsetupstore)<`SS`\>\>

#### Défini dans

[packages/pinia/src/store.ts:809](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L809)

___

### getActivePinia

▸ **getActivePinia**(): `undefined` \| [`Pinia`](../interfaces/pinia.Pinia.md)

Récupère la pinia actuellement active, s'il y en a une.

#### Renvoie

`undefined` \| [`Pinia`](../interfaces/pinia.Pinia.md)

#### Défini dans

[packages/pinia/src/rootStore.ts:39](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L39)

___

### mapActions

▸ **mapActions**<`Id`, `S`, `G`, `A`, `KeyMapper`\>(`useStore`, `keyMapper`): [`_MapActionsObjectReturn`](pinia.md#_mapactionsobjectreturn)<`A`, `KeyMapper`\>

Permet d'utiliser directement les actions de votre store sans utiliser l'API de composition (`setup()`).
(`setup()`) en générant un objet à diffuser dans le champ `methods` du composant.
d'un composant. Les valeurs de l'objet sont les actions tandis que les clés sont
les noms des méthodes résultantes.

**`example`**
```js
export default {
  methods: {
    // autres propriétés des méthodes
    // useCounterStore possède deux actions nommées `increment` et `setCount`.
    ...mapActions(useCounterStore, { moar: 'increment', setIt: 'setCount' })
  },

  created() {
    this.moar()
    this.setIt(2)
  }
}
```

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `KeyMapper` | extends `Record`<`string`, keyof `A`\> |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keyMapper` | `KeyMapper` | object to define new names for the actions |

#### Renvoie

[`_MapActionsObjectReturn`](pinia.md#_mapactionsobjectreturn)<`A`, `KeyMapper`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:326](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L326)

▸ **mapActions**<`Id`, `S`, `G`, `A`\>(`useStore`, `keys`): [`_MapActionsReturn`](pinia.md#_mapactionsreturn)<`A`\>

Allows directly using actions from your store without using the composition
API (`setup()`) by generating an object to be spread in the `methods` field
of a component.

**`example`**
```js
export default {
  methods: {
    // autres méthodes propriétés
    ...mapActions(useCounterStore, ['increment', 'setCount'])
  },

  created() {
    this.increment()
    this.setCount(2) // passer les arguments comme d'habitude
  }
}
```

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keys` | keyof `A`[] | array of action names to map |

#### Renvoie

[`_MapActionsReturn`](pinia.md#_mapactionsreturn)<`A`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:359](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L359)

___

### mapGetters

▸ **mapGetters**<`Id`, `S`, `G`, `A`, `KeyMapper`\>(`useStore`, `keyMapper`): [`_MapStateObjectReturn`](pinia.md#_mapstateobjectreturn)<`Id`, `S`, `G`, `A`, `KeyMapper`\>

Alias pour `mapState()`. Vous devriez utiliser `mapState()` à la place.

**`déprécié`** utilisez plutôt `mapState()`.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `KeyMapper` | extends `Record`<`string`, keyof `S` \| keyof `G` \| (`store`: [`Store`](pinia.md#store)<`Id`, `S`, `G`, `A`\>) => `any`\> |

#### Paramètres

| Name | Type |
| :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> |
| `keyMapper` | `KeyMapper` |

#### Renvoie

[`_MapStateObjectReturn`](pinia.md#_mapstateobjectreturn)<`Id`, `S`, `G`, `A`, `KeyMapper`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:285](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L285)

▸ **mapGetters**<`Id`, `S`, `G`, `A`, `Keys`\>(`useStore`, `keys`): [`_MapStateReturn`](pinia.md#_mapstatereturn)<`S`, `G`, `Keys`\>

Alias pour `mapState()`. Vous devriez utiliser `mapState()` à la place.

**`déprécié`** utilisez plutôt `mapState()`.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `Keys` | extends `string` \| `number` \| `symbol` |

#### Paramètres

| Name | Type |
| :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> |
| `keys` | readonly `Keys`[] |

#### Renvoie

[`_MapStateReturn`](pinia.md#_mapstatereturn)<`S`, `G`, `Keys`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:285](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L285)

___

### mapState

▸ **mapState**<`Id`, `S`, `G`, `A`, `KeyMapper`\>(`useStore`, `keyMapper`): [`_MapStateObjectReturn`](pinia.md#_mapstateobjectreturn)<`Id`, `S`, `G`, `A`, `KeyMapper`\>

Permet d'utiliser l'état et les getters d'un store sans utiliser l'API de composition (`setup()`).
L’API (`setup()`) en générant un objet à diffuser dans le champ `computed`.
d'un composant. Les valeurs de l'objet sont les propriétés/getters de l'état
tandis que les clés sont les noms des propriétés calculées résultantes.
Optionnellement, vous pouvez aussi passer une fonction personnalisée qui recevra le store
comme premier argument. Notez que même si elle a accès à l'instance du composant
via `this`, elle ne sera pas typée.

**`example`**
```js
export default {
  computed: {
    // autres propriétés calculées
    // useCounterStore a une propriété d'état nommée `count` et un getter `double`.
    ...mapState(useCounterStore, {
      n: 'count',
      triple: store => store.n * 3,
      // notez que nous ne pouvons pas utiliser une fonction flèche si nous voulons utiliser `this`.
      custom(store) {
        return this.someComponentValue + store.n
      },
      doubleN: 'double'
    })
  },

  created() {
    this.n // 2
    this.doubleN // 4
  }
}
```

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `KeyMapper` | extends `Record`<`string`, keyof `S` \| keyof `G` \| (`store`: [`Store`](pinia.md#store)<`Id`, `S`, `G`, `A`\>) => `any`\> |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keyMapper` | `KeyMapper` | object of state properties or getters |

#### Renvoie

[`_MapStateObjectReturn`](pinia.md#_mapstateobjectreturn)<`Id`, `S`, `G`, `A`, `KeyMapper`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:194](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L194)

▸ **mapState**<`Id`, `S`, `G`, `A`, `Keys`\>(`useStore`, `keys`): [`_MapStateReturn`](pinia.md#_mapstatereturn)<`S`, `G`, `Keys`\>

Permet d'utiliser l'état et les getters d'un store sans utiliser l'API de composition (`setup()`).
(`setup()`) en générant un objet à diffuser dans le champ `computed`.
d'un composant.

**`example`**
```js
export default {
  computed: {
    // autres propriétés calculées
    ...mapState(useCounterStore, ['count', 'double'])
  },

  created() {
    this.count // 2
    this.double // 4
  }
}
```

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `Keys` | extends `string` \| `number` \| `symbol` |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keys` | readonly `Keys`[] | array of state properties or getters |

#### Renvoie

[`_MapStateReturn`](pinia.md#_mapstatereturn)<`S`, `G`, `Keys`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:231](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L231)

___

### mapStores

▸ **mapStores**<`Stores`\>(...`stores`): [`_Spread`](pinia.md#_spread)<`Stores`\>

Permet d'utiliser les stores sans l'API de composition (`setup()`) en générant un
qui sera étalé dans le champ `computed` d'un composant. Il accepte une liste
de définitions de stores.

**`example`**
```js
export default {
  computed: {
    // autres propriétés calculées
    ...mapStores(useUserStore, useCartStore)
  },

  created() {
    this.userStore // store with id "user"
    this.cartStore // store with id "cart"
  }
}
```

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Stores` | extends `any`[] |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `...stores` | [...Stores[]] | list of stores to map to an object |

#### Renvoie

[`_Spread`](pinia.md#_spread)<`Stores`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:96](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L96)

___

### mapWritableState

▸ **mapWritableState**<`Id`, `S`, `G`, `A`, `KeyMapper`\>(`useStore`, `keyMapper`): [`_MapWritableStateObjectReturn`](pinia.md#_mapwritablestateobjectreturn)<`S`, `KeyMapper`\>

Identique à `mapState()` mais crée également des computed setters afin que l'état puisse être
être modifié. A la différence de `mapState()`, seules les propriétés `state` peuvent être
être ajoutées.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |
| `KeyMapper` | extends `Record`<`string`, keyof `S`\> |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keyMapper` | `KeyMapper` | object of state properties |

#### Renvoie

[`_MapWritableStateObjectReturn`](pinia.md#_mapwritablestateobjectreturn)<`S`, `KeyMapper`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:440](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L440)

▸ **mapWritableState**<`Id`, `S`, `G`, `A`\>(`useStore`, `keys`): [`_MapWritableStateReturn`](pinia.md#_mapwritablestatereturn)<`S`\>

Permet d'utiliser l'état et les getters d'un store sans utiliser l'API de composition (`setup()`).
L’API (`setup()`) en générant un objet à diffuser dans le champ `computed`.
d'un composant.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](pinia.md#statetree) |
| `G` | extends [`_GettersTree`](pinia.md#_getterstree)<`S`\> |
| `A` | `A` |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `useStore` | [`StoreDefinition`](../interfaces/pinia.StoreDefinition.md)<`Id`, `S`, `G`, `A`\> | store to map from |
| `keys` | keyof `S`[] | array of state properties |

#### Renvoie

[`_MapWritableStateReturn`](pinia.md#_mapwritablestatereturn)<`S`\>

#### Défini dans

[packages/pinia/src/mapHelpers.ts:458](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L458)

___

### setActivePinia

▸ **setActivePinia**(`pinia`): `undefined` \| [`Pinia`](../interfaces/pinia.Pinia.md)

Active ou désactive la pinia active. Utilisé dans SSR et en interne lors de l'appel des
actions et getters

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `pinia` | `undefined` \| [`Pinia`](../interfaces/pinia.Pinia.md) | Pinia instance |

#### Renvoie

`undefined` \| [`Pinia`](../interfaces/pinia.Pinia.md)

#### Défini dans

[packages/pinia/src/rootStore.ts:33](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L33)

___

### setMapStoreSuffix

▸ **setMapStoreSuffix**(`suffix`): `void`

Change le suffixe ajouté par `mapStores()`. Peut être défini comme une chaîne vide.
La valeur par défaut est `"Store"`. Assurez-vous d'étendre l'interface MapStoresCustomization
si vous utilisez TypeScript.

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `suffix` | `string` | new suffix |

#### Renvoie

`void`

#### Défini dans

[packages/pinia/src/mapHelpers.ts:66](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/mapHelpers.ts#L66)

___

### skipHydrate

▸ **skipHydrate**<`T`\>(`obj`): `T`

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `T` | `any` |

#### Paramètres

| Name | Type |
| :------ | :------ |
| `obj` | `T` |

#### Renvoie

`T`

#### Défini dans

[packages/pinia/src/store.ts:87](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/store.ts#L87)

___

### storeToRefs

▸ **storeToRefs**<`SS`\>(`store`): `ToRefs`<[`StoreState`](pinia.md#storestate)<`SS`\> & [`StoreGetters`](pinia.md#storegetters)<`SS`\> & [`PiniaCustomStateProperties`](../interfaces/pinia.PiniaCustomStateProperties.md)<[`StoreState`](pinia.md#storestate)<`SS`\>\>\>

Crée un objet de références avec tous les états, getters et propriétés d'état ajoutés par les plugins du store.
du store. Semblable à `toRefs()` mais spécifiquement
spécifiquement conçu pour les stores Pinia, les méthodes et les propriétés non
sont complètement ignorées.

#### Paramètres du type

| Name | Type |
| :------ | :------ |
| `SS` | extends [`_StoreWithState`](../interfaces/pinia._StoreWithState.md)<`string`, [`StateTree`](pinia.md#statetree), [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, [`_ActionsTree`](pinia.md#_actionstree), `SS`\> & {} & [`_StoreWithGetters`](pinia.md#_storewithgetters)<[`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>\> & [`PiniaCustomProperties`](../interfaces/pinia.PiniaCustomProperties.md)<`string`, [`StateTree`](pinia.md#statetree), [`_GettersTree`](pinia.md#_getterstree)<[`StateTree`](pinia.md#statetree)\>, [`_ActionsTree`](pinia.md#_actionstree), `SS`\> & `PiniaCustomStateProperties`<[`StateTree`](pinia.md#statetree), `SS`\> |

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `store` | `SS` | store to extract the refs from |

#### Renvoie

`ToRefs`<[`StoreState`](pinia.md#storestate)<`SS`\> & [`StoreGetters`](pinia.md#storegetters)<`SS`\> & [`PiniaCustomStateProperties`](../interfaces/pinia.PiniaCustomStateProperties.md)<[`StoreState`](pinia.md#storestate)<`SS`\>\>\>

#### Défini dans

[packages/pinia/src/storeToRefs.ts:21](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/storeToRefs.ts#L21)
