## Store

```
중앙에 저장소를 두고 부모-자식 관계 or 연관관계를 가지지 않은 컴포넌트에서 상태에 접근 & 공유
```

### writable
```js
import {writable} from 'svelte/store';

const storeObject = writable(value: any);

//
Object
set: ƒ (new_value)
subscribe: ƒ subscribe(run, invalidate = noop)
update: ƒ update(fn)
[[Prototype]]: Object
//
```

#### set
```js
import {writable} from 'svelte/store';

const count = writable(0);  // 0
count.set(1);   // 1
$count = 2; // 2
```

#### subscribe
```js
store = { subscribe: (subscription: (value: any) => void) => (() => void), set?: value: any) => void }
```

### readable
```
외부에서 변경할 수 없는 상태객체
```
```js
store = readable(value: any, (set: (value: any) => void) => () => void)
```
```js
import {readable} from 'svelte/store';

const name = readable('yeon');
const age = readable(26, (set) => {
    //
});
```

### derived
```
파생 스토어도 상태객체 반환
```
```js
store = derived(a, callback: (a: any) => any)
```
```js
import {writable, derived} from 'svelte/store';

const count = writable(100);    // 100
const doubleCount = derived(count, $count => $count*2); // 200
```

### get
```
상태객체에서 상태값을 가져옴
```
```js
import {writable, get} from 'svelte/store';

const count = writable(10);
const getCount = get(count);    // 10
// count값을 바꿔도 getCount값에는 이전 값
```