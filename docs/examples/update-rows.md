# Update rows

Updating rows takes two parameters. An update function that is required and an optional filter. 

The filter function works just like the query filter. It can be an `$idbID`, an array of `$idbID`, or a custom function,
or nothing in which case it will update everything. 

The update function should not mutate the row, instead it should return a new updated row. Also it should return an
`Object` that can be serialized, just like when inserting rows. Returning anything else will result in an error.

```js
table.update(
  row => ({
    ...row,
    column: 'updated column'
  }),
  row => row.$idbID < 3
);

// [
//   {
//     $idbID: 1,
//     column: 'updated column'
//   },
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
