# Delete rows

Deleting rows takes an optional [`filter`](./query-rows.md) similar to
[`Table`](../api/table.md)`::`[`query`](../api/table.md#query-rows). It can be an `$idbID`, an array of `$idbID`, or a
custom function, or nothing in which case it will delete everything.

```js
table.delete(1);

// [
//   {
//     $idbID: 2,
//     column: 'updated column'
//   },
//   {
//     $idbID: 3,
//     column: 'column match'
//   }
// ]
```
