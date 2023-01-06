## Element Directives

### on:eventname

```js
let count = 0;

function handleClick(event) {
	count += 1;
}
```
```html
<button on:click={handleClick}>count: {count}</button>
```
#### modifiers
```
preventDefault - handdler를 실행하기 전에 event.preventDefault() 호출
stopPropagation - 다음 요소에 도달하는 이벤트를 방지하는 event.stopPropagation() 호출
passive - 터치/휠 이벤트에 대한 스크롤 성능 향상
nonpassive - passive: false
capture - bubbling 대신 capture에서 handler 실행
once - handler가 처음 실행된 후 제거
self - event.target가 요소 자체인 경우에만 trigger handler
trusted: event.isTrusted가 true인 경우에만 trigger handler
```

### bind:property
flows data from child to parent (ordinarily flows parent to child)

```html
<input bind:value={value} />
<input bind:value />
<input type="checkbox" bind:checked={checked} />
<input type="file" accept="img/png, img/jpeg" bind:files id="avatar" name="avatar" />
<textarea bind:value={text}></textarea>
```

#### select
```html
<select bind:value={selected}>
	<option value={a}>a</option>
	<option value={b}>b</option>
</select>
```

```html
<select multiple bind:value={fillings}>
	<option value="Rice">Rice</option>
	<option value="Beans">Beans</option>
</select>
```

```html
<div contenteditable="true" bind:innerHTML={html}></div>
<div contenteditable="true" bind:textContent={text}></div>
```

```html
<details bind:open={isOpen}></details>
```
### bind:group
```js
let tortilla = 'Plain';
```
```html
<input type="radio" bind:group={tortilla} value="Plain">
<input type="radio" bind:group={tortilla} value="Spinach">
```

### bind:this
요소 바로 참조 가능

```js
import { tick, onMount } from 'svelte';

let isShow = false;
let inputEl;

async function toggle() {
	isShow = !isShow;
	await tick();
	console.log(inputEl);
	inputEl && inputEl.focus();
}
```
```html
<button on:click={toggle}>Edit!</button>
{#if isShow}
	<input bind:this={inputEl}>
{/if}
```

### class:name
```js
let active = false;
```

```html
<button on:click={() => {active = !active}}>Toggle!</button>
<div class:active={active}>Hello</div>
<style>
	div {
		width: 50px;
		background: blue;
	}
	.active {
		width: 150px;
		background: yellow;
	}
</style>
```

### style:property
```html
<div style:property={value} >...</div>
<div style:property="value" >...</div>
```

### use:action
연결된 요소가 생성될 때 호출할 함수(action) 지정
```js
function foo() {
	// mount
	return {
		destroy() {
			// return object after unmount
		}
	}
}
```
```html
<div use:foo></div>
```

### transition:fn

### in:fn / out:fn

### animate:fn
