## Assignments are 'reactive'

```
Svelte의 반응성은 할당을 기반으로 함. .push() 와 .splice()는 자동으로 업데이트를 trigger하지 않음. -> 후속 할당 필요
```
```js
let arr = [0, 1];

function handleClick() {
    arr.push(2);
    arr = arr;  // subsequent assignment
}
```

```
Svelte의 <script> 블록은 component가 create 될 때만 실행. prop가 업데이트될 때 자동으로 다시 실행되지 않음
```

### $

```
statement를 반응형으로 만드는 JS label syntax
값이 변경될 때 compoment markup이 render되기 전에 실행
```
```js
export let title;
$: document.title = title;
```

