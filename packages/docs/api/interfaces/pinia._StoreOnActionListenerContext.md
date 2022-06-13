---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / \_StoreOnActionListenerContext

# Interface: \_StoreOnActionListenerContext<Store, ActionName, A\>

[pinia](../modules/pinia.md)._StoreOnActionListenerContext

Type réel pour [StoreOnActionListenerContext](../modules/pinia.md#storeonactionlistenercontext). Existe à des fins de refactoring. Pour un usage interne uniquement.
Pour un usage interne **seulement**.

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Store` | `Store` |
| `ActionName` | extends `string` |
| `A` | `A` |

## Propriétés

### arguments

• **args**: `A` extends `Record`<`ActionName`, [`_Method`](../modules/pinia.md#_method)\> ? `Parameters`<`A`[`ActionName`]\> : `unknown`[]

Paramètres transmis à l'action

#### Défini dans

[packages/pinia/src/types.ts:195](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L195)

___

### name

• **name**: `ActionName`

Nom de l'action

#### Défini dans

[packages/pinia/src/types.ts:185](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L185)

___

### store

• **store**: `Store`

Store qui invoque l'action

#### Défini dans

[packages/pinia/src/types.ts:190](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L190)

## Méthodes

### after

▸ **after**(`callback`): `void`

Met en place un crochet une fois que l'action est terminée. Il reçoit la valeur de retour
de l'action, si c'est une Promise, elle sera déballée. Il peut retourner une
(autre que `undefined`) pour **surpasser** la valeur retournée.

#### Paramètres

| Name | Type |
| :------ | :------ |
| `callback` | `A` extends `Record`<`ActionName`, [`_Method`](../modules/pinia.md#_method)\> ? (`resolvedReturn`: [`_Awaited`](../modules/pinia.md#_awaited)<`ReturnType`<`A`[`ActionName`]\>\>) => `void` \| `ReturnType`<`A`[`ActionName`]\> \| [`_Awaited`](../modules/pinia.md#_awaited)<`ReturnType`<`A`[`ActionName`]\>\> : () => `void` |

#### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:204](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L204)

___

### onError

▸ **onError**(`callback`): `void`

Met en place un hook si l'action échoue. Retournez `false` pour attraper l'erreur et empêcher la
l'erreur et l'empêcher de se propager.

#### Paramètres

| Name | Type |
| :------ | :------ |
| `callback` | (`error`: `unknown`) => `unknown` |

#### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:220](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L220)
