# Store Pattern

```typescript
// /src/common/fooStore/fooStore.ts
...
export const fooStore = ...;
```

```typescript
// /src/common/fooStore/bar.ts
import { FooStore } from './types.ts';

export function doSomething(fooStore: FooStore) {
  ...
}

export function doAnotherThing(fooStore: FooStore) {
  ...
}
```
