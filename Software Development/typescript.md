### How to convert a tuple type to union

```typescript
type UnionFromTuple = [3, 1, 2][number] // => 3 | 1 | 2
```

### Non-empty array
```typescript
type NonEmptyArray<T> = [T, ...T[]];
```

---

- [TypeScript type system (TSts) as a fully flavored language](https://dev.to/macsikora/typescript-is-more-than-you-think-2nbf)

