# Database

`Database` is the main interface in creating and manage a database for an application.

#### Methods:

 - [Create database](#create-database)
 - [Create table](#create-table)
 - [List tables](#list-tables)
 - [Drop table](#drop-table)
 - [Drop database](#drop-database)

## Create database

A database can be created using the `new` operator:

```js
const idb = new InlineDB('my-database');
```

| Param | Required | Default | Description |
|:--|---|---|:--|
| idbName | Yes | _None_ | Name of the database |

Throws error when `idbName`
 - is not provided.
 - is not a string.
 - does not match `[a-zA-Z0-9]+([-_][a-zA-Z0-9]+)*` pattern.
    - see [naming conventions](./naming-conventions.md) for examples.
    
Returns an instance of [`Database`](#).

## Create table

```js
idb.createTable('my-table');
```

| Param | Required | Default | Description |
|:--|---|---|:--|
| tableName | Yes | _None_ | Name of the table |

Throws error when `tableName`
 - is not provided
 - is not a string
 - does not match `[a-zA-Z0-9]+([-_][a-zA-Z0-9]+)*` pattern
    - see [naming conventions](./naming-conventions.md) for examples
    
Returns an instance of [`Table`](./table.md).
    
## List tables

```js
idb.listTables();
```
    
Returns an array of table names (`Array<String>`).

## Drop table

```js
idb.dropTable('my-table');
```
    
| Param | Required | Default | Description |
|:--|---|---|:--|
| tableName | Yes | _None_ | Name of the table |

Returns the current instance of [`Database`](#).

## Drop database
