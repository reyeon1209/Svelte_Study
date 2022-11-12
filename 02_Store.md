## Store

```
중앙에 저장소를 두고 부모-자식 관계 or 연관관계를 가지지 않은 컴포넌트에서 상태에 접근 & 공유
```

```js
import {writable, readable, derived, get} from 'svelte/store';
```

### writable
```js
export const storeObject = writable(value: any)

console.log(storeObject);
//
Object
set: ƒ (new_value)
subscribe: ƒ subscribe(run, invalidate = noop)
update: ƒ update(fn)
[[Prototype]]: Object
//
```