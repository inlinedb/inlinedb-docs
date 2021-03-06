# Save queries to a table

All the mutative queries, `::`[`insert`](../api/table.md#query-rows), `::`[`update`](../api/table.md#update-rows) and
`::`[`delete`](../api/table.md#delete-rows) are not executed immediately, until saved. This gives the ability to
`::`[`revert`](../api/table.md#revert-queries) the queries and a transactional feeling.

Note that after creating a new table, only on saving the data will be written to the system.

```js
table.query()
  .then(rows =>
    console.log(rows)
    // []
  )
  .then(() => {
    table.insert(
      {column: 'column 1'},
      {column: 'column 2'}
    );
        
    return table.save()
  })
  .then(() => table.query())
  .then(rows =>
    console.log(rows)
    // [
    //   {
    //     $idbID: 1,
    //     column: 'column 1'
    //   },
    //   {
    //     $idbID: 2,
    //     column: 'column 2'
    //   }
    // ]
  );
```
