# Table

A table is created from a database instance using [`Database`](./database.md)`::`[`createTable`](./database.md#create-table) method.

#### Methods

 - [Insert rows](#insert-rows)
 - [Query rows](#query-rows)
 - [Update rows](#update-rows)
 - [Delete rows](#delete-rows)
 - [Save queries](#save-queries)
 - [Revert queries](#revert-queries)
 
## Insert rows

```js
idb.insert(row, [, row, ...rows]);
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
## Update rows
## Delete rows
## Save queries
## Revert queries
