---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [@pinia/testing](../modules/pinia_testing.md) / TestingPinia

# Interface: TestingPinia

[@pinia/testing](../modules/pinia_testing.md).TestingPinia

Instance Pinia spécialement conçue pour les tests. Extension d'une instance régulière
[Pinia](pinia.Pinia.md) ordinaire avec des propriétés spécifiques au test.

## Hiérarchie

- [`Pinia`](pinia.Pinia.md)

  ↳ **`TestingPinia`**

## Propriétés

### app

• **app**: `App`<`any`\>

Application utilisée par Pinia

#### Défini

[packages/testing/src/testing.ts:72](https://github.com/vuejs/pinia/blob/2b998ee/packages/testing/src/testing.ts#L72)

___

### state

• **state**: `Ref`<`Record`<`string`, [`StateTree`](../modules/pinia.md#statetree)\>\>

root state

#### Héritée de

[Pinia](pinia.Pinia.md).[state](pinia.Pinia.md#state)

#### Défini

[packages/pinia/src/rootStore.ts:51](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L51)

## Méthodes

### installer

▸ **install**(`app`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `app` | `App`<`any`\> |

#### Renvoie

`void`

#### Héritée de

[Pinia](pinia.Pinia.md).[install](pinia.Pinia.md#install)

#### Défini

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

#### Héritée de

[Pinia](pinia.Pinia.md).[use](pinia.Pinia.md#use)

#### Défini

[packages/pinia/src/rootStore.ts:58](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/rootStore.ts#L58)
