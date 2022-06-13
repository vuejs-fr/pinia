---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / PiniaCustomPropriétés

# Interface: PiniaCustomPropriétés<Id, S, G, A\>

[pinia](../modules/pinia.md).PiniaCustomPropriétés

Interface to be extended by the user when they add Propriétés through plugins.

## Type parameters

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` = `string` |
| `S` | extends [`StateTree`](../modules/pinia.md#statetree) = [`StateTree`](../modules/pinia.md#statetree) |
| `G` | [`_GettersTree`](../modules/pinia.md#_getterstree)<`S`\> |
| `A` | [`_ActionsTree`](../modules/pinia.md#_actionstree) |

## Propriétés

### $nuxt

• **$nuxt**: `Context`

Le context de Nuxt

#### Défini dans

[packages/nuxt/src/module.ts:68](https://github.com/vuejs/pinia/blob/2b998ee/packages/nuxt/src/module.ts#L68)

___

### double

• **double**: `number`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:14](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L14)

___

### globalA

• **globalA**: `string`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:11](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L11)

___

### globalB

• **globalB**: `string`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:12](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L12)

___

### hasApp

• **hasApp**: `boolean`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:9](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L9)

___

### idFromPlugin

• **idFromPlugin**: `Id`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:10](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L10)

___

### pluginN

• **pluginN**: `number`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:7](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L7)

___

### shared

• **shared**: `number`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:13](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L13)

___

### uid

• **uid**: `number`

#### Défini dans

[packages/pinia/__tests__/storePlugins.spec.ts:8](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/__tests__/storePlugins.spec.ts#L8)

## Accesseurs

### route

• `get` **route**(): `RouteLocationNormalized`

#### Returns

`RouteLocationNormalized`

#### Défini dans

[packages/playground/src/main.ts:17](https://github.com/vuejs/pinia/blob/2b998ee/packages/playground/src/main.ts#L17)

• `set` **route**(`value`): `void`

#### Paramètres

| Name | Type |
| :------ | :------ |
| `value` | `RouteLocationNormalizedLoaded` \| `Ref`<`RouteLocationNormalizedLoaded`\> |

#### Renvoie

`void`

#### Défini dans

[packages/playground/src/main.ts:14](https://github.com/vuejs/pinia/blob/2b998ee/packages/playground/src/main.ts#L14)
