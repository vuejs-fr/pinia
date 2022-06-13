---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / Pinia

# Interface: Pinia

[pinia](../modules/pinia.md).Pinia

Chaque application doit posséder son propre pinia pour pouvoir créer des stores

## Hiérarchie

- **`Pinia`**

  ↳ [`TestingPinia`](pinia_testing.TestingPinia.md)

## Propriétés

### state

• **state**: `Ref`<`Record`<`string`, [`StateTree`](../modules/pinia.md#statetree)\>\>

root state

#### Défini dans

[packages/pinia/src/rootStore.ts:51](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L51)

## Méthodes

### install

▸ **install**(`app`): `void`

#### Paramètres

| Name | Type |
| :------ | :------ |
| `app` | `App`<`any`\> |

#### Renvoie

`void`

#### Défini dans

[packages/pinia/src/rootStore.ts:46](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L46)

___

### utiliser

▸ **use**(`plugin`): [`Pinia`](pinia.Pinia.md)

Ajout d'un plugin de store pour étendre chaque store

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `plugin` | [`PiniaPlugin`](pinia.PiniaPlugin.md) | plugin de store à ajouter |

#### Renvoie

[`Pinia`](pinia.Pinia.md)

#### Défini dans

[packages/pinia/src/rootStore.ts:58](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L58)
