# 함수(Function)

## 함수 선언문과 함수 표현식의 차이는?

```javascript
// 함수 선언문
function Hi() {}

// 함수 표현식
const Hello = function () {};
```

- 함수 선언식 <br>
  : 함수 선언식은 `function` 키워드로 시작하며, 함수 이름을 명시적으로 선언 합니다. 주요특징은 호이스팅(자바스크립트 엔진이 스크립트를 실행하기 전에 함수 선언을 메모리에 저장하는 것)으로 함수 선언식은 함수가 정의 된 위치와 관계없이 코드 내 어디서든 호출할 수 있다.
- 함수 표현식 <br>
  : 변수에 함수를 할당하는 방식으로 정의 된다. 함수 표현식은 호이스팅이 되지 않아, 정의된 이후에만 사용할 수 있다. 함수표현식은 익명함수를 사용할 수 있다.
- 차이 정리 <br>
  : 함수 표현식과 함수 선언식의 주된 차이는 호이스팅 여부와 정의 방식에 있다. 함수 선언식은 코드의 어느 위치에서든 호출할 수 있지만, 함수 표현식은 선언된 후에만 호출할 수 있다.

## Function & Arrow Function

```javascript
function sum(a, b) {
  return a + b;
}
```

> `function`키워드를 사용하여 정의시 `자신만의 'this'값`을 가진다. 이는 'function'이 정의된 객체의 컨텍스트에 따라 달라진다.

```javascript
const sum = (a, b) => a + b;
```

> `화살표(=>)`를 사용해 간결하게 정의된 함수는 `자신만의 'this'값을 가지지 않는다.` 대신, `'arrow function' 이 정의된 스코프의 'this'값을 사용`한다. 이는 'arrow function'이 주변의 컨텍스트를 `상속` 받는다고 할 수 있다.

### 차이점 정리

- `this 값의 바인딩`: function은 실행 컨텍스트에 따라 'this'값이 바뀔 수 있지만, 'arrow function'은 항상 상위 스코프의 'this' 값을 사용한다.
- `생성자로의 사용`: 일반 function은 생성자 함수로 사용될 수 있지만, 'arrow function'은 생성자 함수로 사용될 수 없다.
- `arguments`객체: 일반 'function'에서는 'arguments'객체를 사용할 수 있지만, 'arrow function'에서는 사용할 수 없다.

## 즉시 실행 함수 (IIFE)란?

> 즉시 실행함수는 `정의되자마자 즉시 실행하는 자바스크립트 함수 패턴` 입니다. 소괄호로 함수를 감싼 후, 이어서 또다른 한 쌍의 괄호를 사용하여 함수를 호출합니다. 이는 함수를 익명 함수 표현식으로 만들고, 바로 실행되도록 하는 구문입니다.

```javascript
(function () {
  var localVar = '지역 변수';
  console.log(localVar); // '지역 변수'
})();
// localVar는 IIFE 외부에서 접근할 수 없습니다.

console.log(typeof localVar); // 'undefined'
```

IIFE는 주로 함수를 한 번만 실행하고 결과를 즉시 얻고자 할 때 사용됩니다. 이 패턴은 변수와 함수를 전역 스코프로부터 분리하여, 코드 충돌을 방지하고 데이터를 숨기는 데 유용합니다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./class.md)

</div>
