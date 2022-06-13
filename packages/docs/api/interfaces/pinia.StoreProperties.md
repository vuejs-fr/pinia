---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / StoreProperties

# Interface: StoreProperties<Id\>

[pinia](../modules/pinia.md).StoreProperties

Propriétés d'un store.

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |

## Hiérarchie

- **`StoreProperties`**

  ↳ [`_StoreWithState`](pinia._StoreWithState.md)

## Propriétés

### $id

• **$id**: `Id`

Identifiant unique du store

#### Défini dans

[packages/pinia/src/types.ts:265](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L265)

___

### \_customProperties

• **\_customProperties**: `Set`<`string`\>

Utilisé par le plugin devtools pour récupérer les propriétés ajoutées avec les plugins. Supprimé
en production. Peut être utilisé par l'utilisateur pour ajouter des clés de propriétés du store
qui doivent être affichées dans devtools.

#### Défini dans

[packages/pinia/src/types.ts:293](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L293)
