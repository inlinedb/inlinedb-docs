# Getting Started

## Installation

Install using npm:

```bash
npm install inlinedb
```

## Basic Usage

Up and running in no time:

```js
import InlindeDB from 'inlinedb';

// create a new database
const idbName = 'my-database';
const idb = new InlindeDB(idbName);

// and create a new table
const tableName = 'my-table';
idb.createTable(tableName);
```

View [API](../api) for more options
