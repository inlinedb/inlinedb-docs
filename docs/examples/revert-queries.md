# Revert queries

All the queued queries can reverted to the last `::`[`save`](../api/table.md#save-queries).

```js
table.query()
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
  )
  .then(() => {
    table.update(
      () => ({column: 'updated column'})
    );
    
    table.revert();
        
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
