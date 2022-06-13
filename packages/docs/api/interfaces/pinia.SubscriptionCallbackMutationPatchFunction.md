---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / SubscriptionCallbackMutationPatchFunction

# Interface: SubscriptionCallbackMutationPatchFunction

[pinia](../modules/pinia.md).SubscriptionCallbackMutationPatchFunction

Contexte transmis à un callback d'abonnement lorsque `store.$patch()` est appelé
avec une fonction.

## Hierarchy

- [`_SubscriptionCallbackMutationBase`](pinia._SubscriptionCallbackMutationBase.md)

  ↳ **`SubscriptionCallbackMutationPatchFunction`**

## Propriétés

### événements

• **events**: `DebuggerEvent`[]

DEV ONLY. Tableau de toutes les mutations effectuées à l'intérieur du callback.

#### Défini dans

[packages/pinia/src/types.ts:129](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L129)

___

### storeId

• **storeId**: `string`

`id` du store qui effectue la mutation.

#### Inherited from

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[storeId](pinia._SubscriptionCallbackMutationBase.md#storeid)

#### Défini dans

[packages/pinia/src/types.ts:81](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L81)

___

### type

• **type**: [`patchFunction`](../enums/pinia.MutationType.md#patchfunction)

Type de la mutation

#### Remplacement de

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[type](pinia._SubscriptionCallbackMutationBase.md#type)

#### Défini dans

[packages/pinia/src/types.ts:124](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L124)
