# Javascript Class & Prototype

## Class

> 자바스크립트의 클래스는 ES6에 도입되어 객체 지향 프로그래밍을 더욱 쉽고 명확하게 구현할 수 있게 한 구문이다. `클래스는 자바스크립의 기존 프로토타입 기반 상속을 보다 간결하고 이해하기 쉬운 문법으로 감싼 '문법적 설탕(Syntactic Sugar)'`이라 하기도 한다.

```javascript
// 정의: class 키워드를 사용해 정의 되며 내부에는 생성자와 메서드들을 정의할 수 있습니다.
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`안녕하세요, 제 이름은 ${this.name}입니다.`);
  }
}

const person = new Person('홍길동');
person.greet(); // 출력: 안녕하세요, 제 이름은 홍길동입니다.

// 상속: extends 키워드를 사용해 상속 받을 수 있습니다.
class Employee extends Person {
  constructor(name, job) {
    super(name);
    this.job = job;
  }

  work() {
    console.log(`${this.name}이(가) 일을 합니다.`);
  }
}
```

## 프로토타입(Prototype)

> 프로토타입은 객체지향 프로그래밍의 핵심 개념 중 하나로, `객체 간에 속성과 메서드를 상속하기 위해 사용`됩니다. 프로토타입은 `모든 자바스크립트 객체가 가지고 있는 내부 속성`으로, 다른 객체를 참조하는 숨겨진 링크입니다. 이 링크는 객체가 생성될 때 다른 객체로부터 상속받은 속성과 메서드를 찾는 데 사용됩니다.

- 상속 <br>
  한 객체가 다른 객체의 프로토타입을 상속받으면, 상속받은 객체는 부모 객체의 속성과 메서드에 접근할 수 있습니다. 이는 코드의 재사용성을 높이고 메모리를 절약하는 효과가 있습니다.
- 프로토타입 체인 <br>
  객체의 속성이나 메서드에 접근하려 할 때, 해당 객체에 해당 속성이나 메서드가 없으면 자바스크립트는 프로토타입 체인을 따라 상위 프로토타입에서 해당 속성을 찾습니다. 이 체인은 'Object.prototype'에 도달할 때까지 계속됩니다.

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function () {
  console.log('안녕하세요, ' + this.name + '입니다.');
};

const person1 = new Person('홍길동');
person1.greet(); // 출력: 안녕하세요, 홍길동입니다.
```

> 위 예시에서, 'Person'함수의 프로토타입에 'greet'메서드를 추가했습니다. 이후 'Person'을 통해 생성된 모든 객체는 'greet'메서드에 접근할 수 있습니다.

- 결론<br>
  프로토 타입은 자바스크립트의 동적인 특성을 활용하여 객체 간에 속성과 메서드를 효율적으로 공유할 수 있게 해줍니다. 이는 특히 큰 규모의 어플리케이션 개발에서 메모리 사용을 최적화하고 코드의 재사용성을 높이는 데 큰 장점을 제공합니다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./closure.md)

</div>
