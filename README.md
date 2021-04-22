# @ev-fns/object-fns

Object functions

- pickKeys `<T>(obj: T, key: (keyof T)[]) => Partial<T>`
- removeKeys `<T>(obj: T, key: (keyof T)[]) => Partial<T>`
- removeUndefined `<T>(obj: T) => Partial<T>`
- toCamel `(obj: Record<string, any>) => Record<string, any>`
- toSnake `(obj: Record<string, any>) => Record<string, any>`

## Install

```sh
yarn add @ev-fns/object-fns
```

## Usage

```js
const {
  pickKeys,
  removeKeys,
  removeUndefined,
  toCamel,
  toSnake,
} = require("@ev-fns/object-fns");

const obj = { key: "1", snake_key: "2", camelKey: "3", undef: undefined };

console.log(pickKeys(obj, ["key"]));
// { key: "1" }

console.log(removeKeys(obj, ["snake_key", "camelKey", "undef"]));
// { key: "1" }

console.log(removeUndefined(obj));
// { key: "1", snake_key: "2", camelKey: "3" }

console.log(toCamel(obj));
// { key: "1", snakeKey: "2", camelKey: "3", undef: undefined }

console.log(toSnake(obj));
// { key: "1", snake_key: "2", camel_key: "3", undef: undefined }
```
