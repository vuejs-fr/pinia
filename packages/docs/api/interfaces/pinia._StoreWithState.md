---
sidebar: "auto"
editLinks: false
sidebarDepth: 3
---

[Documentation de l'API](../index.md) / [pinia](../modules/pinia.md) / \_StoreWithState

# Interface: \_StoreWithState<Id, S, G, A\>

[pinia](../modules/pinia.md)._StoreWithState

store de base avec état et fonctions. Ne doit pas être utilisé directement.

## Paramètres de type

| Name | Type |
| :------ | :------ |
| `Id` | extends `string` |
| `S` | extends [`StateTree`](../modules/pinia.md#statetree) |
| `G` | `G` |
| `A` | `A` |

## Hiérarchie

- [`StoreProperties`](pinia.StoreProperties.md)<`Id`\>

  ↳ **`_StoreWithState`**

## Propriétés

### $id

• **$id**: `Id`

Identifiant unique du store

#### Héritée de

[StoreProperties](pinia.StoreProperties.md).[$id](pinia.StoreProperties.md#$id)

#### Défini dans

[packages/pinia/src/types.ts:265](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L265)

___

### $state

• **$state**: `UnwrapRef`<`S`\> & `PiniaCustomStateProperties`<`S`\>

État du store. Si vous le définissez, vous remplacerez l'ensemble de l'état.

#### Défini dans

[packages/pinia/src/types.ts:335](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L335)

___

### \_customProperties

• **\_customProperties**: `Set`<`string`\>

Utilisé par le plugin devtools pour récupérer les propriétés ajoutées avec les plugins. Supprimé
en production. Peut être utilisé par l'utilisateur pour ajouter des clés de propriétés du store
qui doivent être affichées dans devtools.

#### Héritée de

[StoreProperties](pinia.StoreProperties.md).[_customProperties](pinia.StoreProperties.md#_customproperties)

#### Défini dans

[packages/pinia/src/types.ts:293](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L293)

## Méthodes

### $dispose

▸ **$dispose**(): `void`

Arrête la portée de l'effet associé du store et la supprime du registre du store.
registre. Les plugins peuvent surcharger cette méthode pour nettoyer tout effet ajouté.
Par exemple, le plugin devtools arrête l'affichage des stores disposés de devtools.

#### Retourne

`void`

#### Défini dans

[packages/pinia/src/types.ts:423](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L423)

___

### $onAction

▸ **$onAction**(`callback`, `detached?`): () => `void`

Configure un callback qui sera appelé chaque fois qu'une action est sur le point d'être
invoquée. Le callback reçoit un objet avec toutes les informations pertinentes
de l'action invoquée :
- `store` : le store sur lequel elle est invoquée
- `name` : Le nom de l'action
- `args` : Les paramètres passés à l'action

En plus de cela, il reçoit deux fonctions qui permettent de configurer un callback
lorsque l'action se termine ou lorsqu'elle échoue.

Elle renvoie également une fonction permettant de supprimer le callback. Notez que lorsque vous appelez
`store.$onAction()` à l'intérieur d'un composant, elle sera automatiquement nettoyée
automatiquement nettoyé lorsque le composant sera démonté, à moins que `detached` ne soit défini à true.

**`example`**

```js
store.$onAction(({ after, onError }) => {
 // Ici vous pouvez partager des variables entre tous les hooks ainsi que
 // mettre en place des watchers et les nettoyer
 after((resolvedValue) => {
   // peut être utilisé pour nettoyer les effets secondaires
.  // `resolvedValue` est la valeur retournée par l'action, si c'est un
.  // Promise, ce sera la valeur résolue au lieu de la Promise.
 })
 onError((error) => {
   // peut être utilisé pour transmettre les erreurs
 })
})
```

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `callback` | [`StoreOnActionListener`](../modules/pinia.md#storeonactionlistener)<`Id`, `S`, `G`, `A`\> | callback appelé avant chaque action |
| `detached?` | `boolean` | détache l'abonnement du contexte à partir duquel il est appelé |

#### Renvoie

`fn`

fonction qui supprime l'observateur

▸ (): `void`

Configure un callback qui sera appelé chaque fois qu'une action est sur le point d'être
invoquée. Le callback reçoit un objet avec toutes les informations pertinentes
de l'action invoquée :
- `store` : le store sur lequel elle est invoquée
- `name` : Le nom de l'action
- `args` : Les paramètres passés à l'action

En plus de cela, il reçoit deux fonctions qui permettent de configurer un callback
lorsque l'action se termine ou lorsqu'elle échoue.

Elle renvoie également une fonction permettant de supprimer le callback. Notez que lorsque vous appelez
`store.$onAction()` à l'intérieur d'un composant, elle sera automatiquement nettoyée
automatiquement nettoyé lorsque le composant sera démonté, à moins que `detached` ne soit défini à true.

**`example`**

```js
store.$onAction(({ after, onError }) => {
 // Ici vous pouvez partager des variables entre tous les hooks ainsi que
 // mettre en place des watchers et les nettoyer
 after((resolvedValue) => {
   // peut être utilisé pour nettoyer les effets secondaires
.  // `resolvedValue` est la valeur retournée par l'action, si c'est un
.  // Promise, ce sera la valeur résolue au lieu de la Promise.
 })
 onError((error) => {
   // peut être utilisé pour transmettre les erreurs
 })
})
```

##### Renvoie

`void`

fonction qui supprime l'observateur

#### Défini dans

[packages/pinia/src/types.ts:413](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L413)

___

### $patch

▸ **$patch**(`partialState`): `void`

Applique un patch d'état à l'état actuel. Permet de passer des valeurs imbriquées

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `partialState` | [`_DeepPartial`](../modules/pinia.md#_deeppartial)<`UnwrapRef`<`S`\>\> | patch à appliquer à l'état |

##### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:342](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L342)

▸ **$patch**<`F`\>(`stateMutator`): `void`

Regroupe plusieurs modifications dans une seule fonction. Utile lorsque la mutation d'objets tels que
des ensembles ou des tableaux et que l'application d'un patch d'objet n'est pas pratique, par exemple l'ajout de
à un tableau. La fonction passée à `$patch()` **doit être synchrone**.

#### Paramètres de type

| Name | Type |
| :------ | :------ |
| `F` | extends (`state`: `UnwrapRef`<`S`\>) => `any` |

#### Paramètres


| Name | Type | Description |
| :------ | :------ | :------ |
| `stateMutator` | `ReturnType`<`F`\> extends `Promise`<`any`\> ? `never` : `F` | fonction qui modifie l’`état`, ne peut pas être asynchrone. |

##### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:351](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L351)

___

### $reset

▸ **$reset**(): `void`

Réinitialise le store à son état initial en construisant un nouvel objet d'état.
TODO : faire cette option seulement

##### Renvoie

`void`

#### Défini dans

[packages/pinia/src/types.ts:360](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L360)

___

### $subscribe

▸ **$subscribe**(`callback`, `options?`): () => `void`

Configure un callback qui sera appelé à chaque fois que l'état change. Elle renvoie également une fonction permettant de supprimer la fonction de rappel. Remarque :
que lorsque vous appelez `store.$subscribe()` à l'intérieur d'un composant, il sera automatiquement nettoyé lorsque le
composant est démonté, à moins que `detached` ne soit défini à true.

#### Paramètres

| Name | Type | Description |
| :------ | :------ | :------ |
| `callback` | [`SubscriptionCallback`](../modules/pinia.md#subscriptioncallback)<`S`\> | callback passé au watcher |
| `options?` | { `detached?`: `boolean`  } & `WatchOptions`<`boolean`\> | Options `watch` + `detached` pour détacher l'abonnement du contexte (généralement un composant) à partir duquel il est appelé. Notez que l'option `flush` n'affecte pas les appels à `store.$patch()`. |

#### Renvoie

`fn`

fonction qui supprime l'observateur

▸ (): `void`

Configure un callback qui sera appelé à chaque fois que l'état change. Elle renvoie également une fonction permettant de supprimer la fonction de rappel. Remarque :
que lorsque vous appelez `store.$subscribe()` à l'intérieur d'un composant, il sera automatiquement nettoyé lorsque le
composant est démonté, à moins que `detached` ne soit défini à true.

##### Renvoie

`void`

fonction qui supprime l'observateur

#### Défini dans

[packages/pinia/src/types.ts:372](https://github.com/vuejs/pinia/blob/2b998ee/packages/pinia/src/types.ts#L372)
