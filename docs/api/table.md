# Table

A table is created from a database instance using [`Database`](./database.md)`::`[`createTable`](./database.md#create-table) method.
All data manipulation operations are transactional i.e until saved, none of the mutative queries are executed

#### Methods

 - [Insert rows](#insert-rows)
 - [Query rows](#query-rows)
 - [Update rows](#update-rows)
 - [Delete rows](#delete-rows)
 - [Save queries](#save-queries)
 - [Revert queries](#revert-queries)
 
## Insert rows

Adds a query to queue to insert the given rows.

```js
idb.insert(row[, row, ...rows]);
```

| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| ...rows | Yes | _Object_ list | _None_ | One or more objects to be inserted into the table |

#### Throws

 - When one or more `rows` is not provided.
 - When one of the `rows` is not an object.

#### Returns

The current instance of [`Table`](#).

#### Notes

 - Does not mutate the table until [`Table`](#)`::`[`save`](#save-queries) is called.
 - Can be reverted before saving using [`Table`](#)`::`[`revert`](#revert-queries).

## Query rows

Queries rows matched by the `filter`.

```js
idb.query([filter]);
```

| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| filter | No | one of _<ul><li>Number</li><li>Array<Number></li><li>Function</li></ul>_ | `[Function:`&nbsp;`()`&nbsp;`=>`&nbsp;`true]` | Takes in an `id` or an array of `ids` or a filter function that will be matched against row |

#### Returns

A `Promise` that resolves to a an array of rows that is matched by the given filter.

## Update rows

Adds a query to queue to update the rows that are matched by the given `filter`, and run given `update` on each of the filtered row to get the updated row.

```js
idb.update(update[, filter]);
```

| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| update | Yes | _Function_ | _None_ | A non mutative function that will be run on each row |
| filter | No | one of _<ul><li>Number</li><li>Array<Number></li><li>Function</li></ul>_ | `[Function:`&nbsp;`()`&nbsp;`=>`&nbsp;`true]` | Takes in an `id` or an array of `ids` or a filter function that will be matched against row |

#### Throws

 - When `udpate` is not a function.
 - When `udpate` might mutate the row.
 - When `udpate` might return a value other than an `Object`.

#### Returns

The current instance of [`Table`](#).

#### Notes

 - Does not mutate the table until [`Table`](#)`::`[`save`](#save-queries) is called.
 - Can be reverted before saving using [`Table`](#)`::`[`revert`](#revert-queries).

## Delete rows

Adds a query to queue to delete the rows that are matched by the given `filter`.

```js
idb.delete([filter]);
```

| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| filter | No | one of _<ul><li>Number</li><li>Array<Number></li><li>Function</li></ul>_ | `[Function:`&nbsp;`()`&nbsp;`=>`&nbsp;`true]` | Takes in an `id` or an array of `ids` or a filter function that will be matched against row |

#### Returns

The current instance of [`Table`](#).

#### Notes

 - Does not mutate the table until [`Table`](#)`::`[`save`](#save-queries) is called.
 - Can be reverted before saving using [`Table`](#)`::`[`revert`](#revert-queries).

## Save queries
## Revert queries
