## How to convert a tuple type to union

```typescript
type UnionFromTuple = [3, 1, 2][number] // => 3 | 1 | 2
```
