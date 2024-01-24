# 이터러블과 이터레이터에 대해서

## 이터러블 (Iterable)

- 이터러블은 'Symbol.iterator'속성을 가진 객체로, 이 속성은 이터레이터를 반환하는 함수이다.
- 이터러블 객체는 'for...of', 'spreed'연산자, 'destructuring assignment'등과 함께 사용할 수 있습니다.
- 자바스크립트 내장 이터러블 객체에는 배열, 문자열, Map, Set 등이 포함됩니다.

## 이터레이터 (Iterator)

- 이터레이터 프로토콜은 'next()'메서드를 제공하는 객체를 말합니다. 'next()'메서드는 `value`와 `done` 속성을 가진 객체를 반환합니다.
- `value`는 현재 위치의 값이며, `done`은 순회가 끝났는지의 여부를 나타냅니다.
- 이터레이터는 순회 가능한 데이터 컬렉션의 요소들을 한 번에 하나씩 접근하는 방법을 제공합니다.

```javascript
const iterable = [1, 2, 3];
const iterator = iterable[Symbol.iterator]();

console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: 3, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

[처음으로](../README.md)
