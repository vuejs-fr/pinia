---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / SubscriptionCallbackMutationDirect

# Interface: SubscriptionCallbackMutationDirect

[pinia](../modules/pinia.md).SubscriptionCallbackMutationDirect

Contexte transmis à une callback d'abonnement lors de la mutation directe de l'état 
d'un magasin avec `store.someState = newValue` ou `store.$state.someState =
nouvelleValeur`.

## Hiérarchie

- [`_SubscriptionCallbackMutationBase`](pinia._SubscriptionCallbackMutationBase.md)

  ↳ **`SubscriptionCallbackMutationDirect`**

## Propriété

### événements

• **events**: `DebuggerEvent`

DEV SEULEMENT. Différents appels de mutation.

#### Défini dans

[packages/pinia/src/types.ts:96](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L96)

___

### storeId

• **storeId**: `string`

`id` du store qui effectue la mutation.

#### Hérité de

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[storeId](pinia._SubscriptionCallbackMutationBase.md#storeid)

#### Défini dans

[packages/pinia/src/types.ts:81](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L81)

___

### type

• **type**: [`direct`](../enums/pinia.MutationType.md#direct)

Type de la mutation.

#### Remplacement de

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[type](pinia._SubscriptionCallbackMutationBase.md#type)

#### Défini dans

[packages/pinia/src/types.ts:91](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L91)
