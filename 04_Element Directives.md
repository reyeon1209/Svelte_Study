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
```bind:this``` 요소 바로 참조 가능

```html
	<input bind:value={value} />
	<input bind:value />
	<input type="checkbox" bind:checked={checked} />
	<input type="file" accept="img/png, img/jpeg" bind:files id="avatar" name="avatar" />
	<textarea bind:value={text}></textarea>
```

```html
<div contenteditable="true" bind:innerHTML={html}></div>
```

```html
<details bind:open={isOpen}></details>
```