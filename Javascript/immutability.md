# 자바스크립트에서 불변성 관련 메서드

> `Object.preventExtensions`, `Object.seal`, `Object.freeze`는 자바스크립트에서 객체의 불변성을 다루는데 사용되는 메서드이다.

1. Object.preventExtensions(obj)

- 이 메서드는 객체에 새로운 속성을 추가하는 것을 방지한다.
- 이미 존재하는 속성의 삭제나 수정은 가능하다.

```javascript
const obj = { a: 1 };
Object.preventExtensions(obj);
obj.b = 2; // 추가 불가능
console.log(obj); // { a: 1 }
```

2. Object.seal(obj)

- 새로운 속성 추가를 방지하면서 기존 속성의 삭제 또는 설명자의 변경도 방지한다.
- 속성의 값 변경은 허용한다.

```javascript
const obj = { a: 1 };
Object.seal(obj);
obj.a = 2; // 변경 가능
delete obj.a; // 삭제 불가능
console.log(obj); // { a: 2 }
```

3. Object.freeze(obj)

- 객체를 완전히 불변하게 만든다.
- 새로운 속성 추가, 기존 속성 수정, 속성 삭제가 모두 불가능해집니다.
- 객체가 생성된 이후에는 어떠한 변경도 허용하지 않습니다.

```javascript
const obj = { a: 1 };
Object.freeze(obj);
obj.a = 2; // 변경 불가능
obj.b = 3; // 추가 불가능
delete obj.a; // 삭제 불가능
console.log(obj); // { a: 1 }
```

이러한 메서드들을 사용하면 객체의 불변성을 강화할 수 있습니다. 하지만, 'Object.freeze'를 사용한 객체의 내부 객체 까지 불변하게 만들지 않기 때문에 이런 경우 불변성 라이브러리인 Immutable.js, Immer.js 같은 라이브러리를 사용하여 불변성을 보다 쉽게 관리할 수 있습니다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./es6.md)

</div>
