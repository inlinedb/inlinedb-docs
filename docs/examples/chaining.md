# Chaining operations

Since its all `Promise` and `this`, all the operations can be easily chained.

```js
import InlineDB from 'inlinedb';

const table = new InlineDB('my-database')
  .createTable('my-table')
  .insert(
    {column: 'column 1'},
    {column: 'column 2'},
    {column: 'column 3'}
  )
  .update(
    row => ({
      ...row,
      column: 'updated column'
    }),
    row => row.$idbID < 3
  )
  .delete(1);

table.save()
  .then(() => table.query())
  .then(rows => console.log(rows));

// [
//   {
//     $idbID: 2,
//     column: 'updated column'
//   },
//   {
//     $idbID: 3,
//     column: 'column 3'
//   }
// ]
```
