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
const idb = new InlineDB(idbName);
```

| Param | Required | Type | Default | Description |
|:---|:---:|:---:|:---:|:---|
| idbName | Yes | _String_ | _None_ | Name of the database to create |

#### Throws

 - When `idbName` is not provided.
 - When `idbName` is not a string.
 - When `idbName` does not match `[a-zA-Z0-9]+([-_][a-zA-Z0-9]+)*` pattern.
    - see [naming conventions](./naming-conventions.md) for examples.
    
#### Returns

An instance of [`Database`](#).

## Create table

```js
idb.createTable(tableName);
```

| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| tableName | Yes | _String_ | _None_ | Name of the table to create |

#### Throws

 - When `tableName` is not provided.
 - When `tableName` is not a string.
 - When `tableName` does not match `[a-zA-Z0-9]+([-_][a-zA-Z0-9]+)*` pattern.
    - see [naming conventions](./naming-conventions.md) for examples.
    
#### Returns
 
An instance of [`Table`](./table.md).
    
## List tables

```js
idb.listTables();
```
    
#### Returns

An array of table names (`Array<String>`).

## Drop table

```js
idb.dropTable(tableName);
```
    
| Param | Required | Type | Default | Description |
|:---|:---|:---|:---|:---|
| tableName | Yes | _String_ | _None_ | Name of the table to drop |

#### Returns 

Current instance of [`Database`](#).

## Drop database

```js
idb.drop();
```

#### Returns 

Nothing (`undefined`).
