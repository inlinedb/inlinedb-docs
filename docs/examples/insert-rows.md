# Insert rows

Multiple rows can be inserted into the table, but at least one row must be provided. 

```js
table.insert(
    {column: 'column awesome'},
    {column: 'column match'},
    {column: 'column random'}
);
```

There is no rule on how the row
should look like, except that it should be an `Object` and should be serializable. So no `Date`, `Symbol`, or `Function`.
Some of these might be supported in future.
