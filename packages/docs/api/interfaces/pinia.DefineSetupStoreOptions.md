---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / DefineSetupStoreOptions

# Interface: DefineSetupStoreOptions<Id, S, G, A\>

[pinia](../modules/pinia.md).DefineSetupStoreOptions

Paramètre d'options de `defineStore()` pour les stores de configuration. Peut être étendu pour
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

  ↳ **`DefineSetupStoreOptions`**

## Propriétés

### actions

• `Optional` **actions**: `A`

Actions extraites. Ajoutées par useStore(). NE DOIT PAS être ajouté par l'utilisateur lors de la
l'utilisateur lors de la création du store. Peut être utilisé dans les plugins pour obtenir la liste des actions dans un
store défini avec une fonction d'installation. Notez que cette fonction est toujours définie

#### Défini dans

[packages/pinia/src/types.ts:704](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L704)
