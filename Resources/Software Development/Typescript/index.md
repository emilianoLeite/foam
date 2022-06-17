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
- [Official doc](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-func.html#discriminated-unions) about discriminated unions (aka tagged unions)

---

## [Type challenges](https://github.com/type-challenges/type-challenges)

---

## TS WTF
- [accept any string, but suggest some specific values on autocomplete.](https://twitter.com/diegohaz/status/1524257274012876801)
