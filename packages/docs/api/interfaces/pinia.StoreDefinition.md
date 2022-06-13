---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / StoreDefinition

# Interface: StoreDefinition<Id, S, G, A\>

[pinia](../modules/pinia.md).StoreDefinition

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` = `string` |
| `S` | extends [`StateTree`](../modules/pinia.md#statetree) = [`StateTree`](../modules/pinia.md#statetree) |
| `G` | [`_GettersTree`](../modules/pinia.md#_getterstree)<`S`\> |
| `A` | [`_ActionsTree`](../modules/pinia.md#_actionstree) |

## Appelable

### StoreDefinition

▸ **StoreDefinition**(`pinia?`, `hot?`): [`Store`](../modules/pinia.md#store)<`Id`, `S`, `G`, `A`\>

Renvoie un store, le crée si nécessaire.

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `pinia?` | ``null`` \| [`Pinia`](pinia.Pinia.md) | Instance Pinia pour récupérer le store |
| `hot?` | [`StoreGeneric`](../modules/pinia.md#storegeneric) | dev only hot module replacement |

#### Renvoie

[`Store`](../modules/pinia.md#store)<`Id`, `S`, `G`, `A`\>

#### Défini dans

[packages/pinia/src/types.ts:511](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L511)

## Propriété

### $id

• **$id**: `Id`

Id du magasin. Utilisé par les aides de la carte.

#### Défini dans

[packages/pinia/src/types.ts:516](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L516)
