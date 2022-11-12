## Svelte

```
Virtual DOM이 없고 Runtime에 load할 프레임워크 없음 -> 빌드 단계에서 구성요소를 컴파일하는 일종의 컴파일러 (CND 제공 X)
페이지에 단일 bundle을 load하여 App을 rendering
```

### Write less code
```
React, Vue에 비해 더 적은 코드로 작성
```

### No virtual DOM
```
Virtual DOM을 사용 X
새로운 Virtual DOM을 이전 Snapshot이랑 비교하는 Diffing 등의 과정을 생략
Runtime이 아닌 빌드 단계에 앱에서 어떤 변경사항이 발생하는지 알고 있음
```

### Trult reactive
```
별도의 Setter없이 assignments만으로 업데이트 trigger 가능 -> 변경된 값이 DOM에 자동으로 반영
```