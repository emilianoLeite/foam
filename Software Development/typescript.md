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

- [Flavoring and Branding](https://spin.atomicobject.com/2018/01/15/typescript-flexible-nominal-typing/)
  - Related topic: [shadow types](https://dev.to/busypeoples/notes-on-typescript-phantom-types-kg9)
