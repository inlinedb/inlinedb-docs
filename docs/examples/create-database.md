# Create database

Import the InlineDB library to instantiate a new database.

```js
import InlindeDB from 'inlinedb';

// create a new database
const idbName = 'my-database';
const idb = new InlindeDB(idbName);
```

If the database is already exists, running `new InlineDB` will return an instance that runs on the existing database. 
Otherwise it will create a new database in the system and will return an instance for that.
