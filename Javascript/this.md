# Javascript에서의 this

> 자바스크립트에서 'this'키워드는 함수나 메서드 현재 실행컨텍스트를 참조한다. this의 값은 함수가 어떻게 호출되었는지에 따라 달라진다.

1. 전역 컨텍스트 에서의 'this'

   > 전역스코프나 전역함수에서 'this'를 사용하면, 전역객체를 가리킨다. 브라우저에서는 'window' 객체가 되며, Node.js에서는 'global'객체가 된다.

2. 함수에서의 'this'

   > 일반 함수에서 'this'는 기본적으로 전역 객체를 참조합니다. 하지만 `엄격모드('use strict')` 에서는 this가 undefined로 설정 된다.

3. 화살표 함수에서의 'this'

   > 화살표 함수는 this가 없기 때문에 생성된 시점에서 주변 스코프(상위 스코프)의 this 값을 받는다.

4. 메서드에서의 'this'

   > 객체의 메서드에서 'this'는 메서드를 호출한 객체를 가리킨다. 이를 통해 객체 내부의 속성이나 다른 메서드에 접근할 수 있다.

5. 생성자 함수에서의 'this'

   > 생성자 함수에서의 this는 새롭게 생성되는 인스턴스를 가리킨다. 'new'키워드를 사용하여 생성자를 호출하면, 'this'는 새 객체에 바인딩 된다.

6. 이벤트 핸들러에서의 'this'

   > HTML요소에 할당 된 이벤트 핸들러 내에서 this는 해당 HTML 요소를 가리킨다.

7. 명시적 'this' 바인딩
   `call`, `apply`, `bind`함수를 사용하여 함수 호출시 'this'값을 명시적으로 설정할 수 있다. 해당 함수가 함수의 호출/생성에 사용되는 경우, 함수내의 this는 인수로 전달된 객체이다.

- `call` 함수
  > 해당함수는 첫 번째 인자로 'this'의 값을, 그 후의 인자들로 호출할 함수의 인자들을 전달합니다.

```javascript
function greet() {
  console.log(this.name + '님, 안녕하세요!');
}

const person = {
  name: '홍길동',
};

greet.call(person); // 출력: 홍길동님, 안녕하세요!
```

- `apply` 함수
  > call함수와 비슷하지만, 함수의 인자들을 배열로 전달한다.

```javascript
function introduce(job, hobby) {
  console.log(
    `제 이름은 ${this.name}이고, 직업은 ${job}이며, 취미는 ${hobby}입니다.`
  );
}

const person = {
  name: '김철수',
};

introduce.apply(person, ['개발자', '등산']); // 출력: 제 이름은 김철수이고, 직업은 개발자이며, 취미는 등산입니다.
```

- `bind` 함수
  > 새로운 함수를 반환하며, 반환된 함수의 'this'값이 'bind'함수의 첫 번째 인자로 고정 된다. 'bind'는 함수를 실행하지 않고 this를 바꾸고 난 후의 bound함수를 리턴한다.

```javascript
function sayHello() {
  console.log('안녕하세요, ' + this.name);
}

const person = {
  name: '이영희',
};

const sayHelloToPerson = sayHello.bind(person);
sayHelloToPerson(); // 출력: 안녕하세요, 이영희
```

⚙️ 추가

- 생성자란?
  : 생성자 함수란 `new` 키워드와 함께 호출하여 객체를 생성하는 함수를 의미한다. 추가적으로 생성자 함수에 의해 생성된 객체를 인스턴스라 한다.

- 엄격 모드란? <br>
  : 엄격 모드(`"use strict";`를 스크립트 최상단에 작성)는 ES5에서 기존 스펙을 변경하여 하위 호환성 문제가 발생하여 도입된 문법으로, 엄격 모드를 활성화 했을 때에만 변경사항이 적용되도록 해두었다. 코드를 클래스와 모듈을 사용해 구성한다면 기본적으로 엄격모드가 활성화 된다.

[처음으로](../README.md)
