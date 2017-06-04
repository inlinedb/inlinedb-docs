# Query rows

Consider the following table:

```json
[
  {
    "$idbID": 1,
    "column": "column 1"
  },
  {
    "$idbID": 2,
    "column": "column 2"
  },
  {
    "$idbID": 3,
    "column": "column match"
  }
]
```

Querying can be achieved using an `$idbID`, an array of `$idbID`, or a custom function, or nothing in which case it will 
return everything. Querying is done asynchronously, so it will return a promise that will resolve to queried data.

#### Using no filter 

```js
table.query()
  .then(rows => console.log(rows));

// [
//   {
//     $idbID: 1,
//     column: 'column 1'
//   },
//   {
//     $idbID: 2,
//     column: 'column 2'
//   },
//   {
//     $idbID: 3,
//     column: 'column match'
//   }
// ]
```

#### Using id

```js
table.query(1)
  .then(rows => console.log(rows));

// [
//   {
//     $idbID: 1,
//     column: 'column 1'
//   }
// ]
```

#### Using ids

```js
table.query([1, 2])
  .then(rows => console.log(rows));

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
```

#### Using a function

```js
table.query(row => row.column === 'column match')
  .then(rows => console.log(rows));

// [
//   {
//     $idbID: 3,
//     column: 'column match'
//   }
// ]
```
