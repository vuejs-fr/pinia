---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / SubscriptionCallbackMutationPatchObject

# Interface: SubscriptionCallbackMutationPatchObject<S\>

[pinia](../modules/pinia.md).SubscriptionCallbackMutationPatchObject

Contexte passé à un callback de souscription lorsque `store.$patch()` est appelé
avec un objet.

## Paramètres de type

| Name |
| :------ |
| `S` |

## Hiérarchie

- [`_SubscriptionCallbackMutationBase`](pinia._SubscriptionCallbackMutationBase.md)

  ↳ **`SubscriptionCallbackMutationPatchObject`**

### Propriétés

### événements

• **events**: `DebuggerEvent`[]

DEV UNIQUEMENT. Array pour les appels de patch.

#### Défini dans

[packages/pinia/src/types.ts:110](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L110)

___

### payload

• **payload**: [`_DeepPartial`](../modules/pinia.md#_deeppartial)<`S`\>

Objet passé à `store.$patch()`.

#### Défini dans

[packages/pinia/src/types.ts:115](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L115)

___

### storeId

• **storeId**: `string`

`id' du store qui effectue la mutation.

#### Hérité de

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[storeId](pinia._SubscriptionCallbackMutationBase.md#storeid)

#### Défini dans

[packages/pinia/src/types.ts:81](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L81)

___

### type

• **type**: [`patchObject`](../enums/pinia.MutationType.md#patchobject)

Type de mutation.

#### Remplacements

[_SubscriptionCallbackMutationBase](pinia._SubscriptionCallbackMutationBase.md).[type](pinia._SubscriptionCallbackMutationBase.md#type)

#### Défini dans

[packages/pinia/src/types.ts:105](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L105)
