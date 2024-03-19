# Tuples

- Get the length of a tuple
- Create a tuple of a specific length

```ts

// All 3 types copied from StackOverflow
type Length<Type extends readonly unknown[]> = Type['length']
type _TupleOf<
  T,
  TupleSize extends number,
  Rest extends unknown[]
> = Rest['length'] extends TupleSize ? Rest : _TupleOf<T, TupleSize, [T, ...Rest]>
type Tuple<T, TupleSize extends number> = TupleSize extends TupleSize
  ? number extends TupleSize
    ? T[]
    : _TupleOf<T, TupleSize, []>
  : never

/**
 * Receives tuple `header` of unknown length
 * Returns function that accepts a string tuple of the same length as `header`
*/
function csvWritter<T extends readonly unknown[]>({header}: {
  header: T
}) {
  // ...

  const writeRow = (row: Tuple<string, Length<T>>) => {
    // fs.appendFileSync(absolutePath, `${row.join(',')}\n`)
  }

  return { writeRow }
}
```
