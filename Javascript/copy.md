# 얕은 복사 와 깊은 복사

## 얕은 복사

> `객체의 최상위 프로퍼티 만을 복사`, 얕은 복사를 사용하면 중첩된 객체나 배열은 원본과 복사본이 동일한 참조를 공유하며 변경시 원본과 복사본 모두에 영향을 미친다.

```javascript
const original {
  a:1,
  b: { c:2 }
};

// 스프레드 구문을 이용한 얕은 복사
const copy1 = {...original};

// Object.assign을 이용한 얕은 복사
const copy2 = Object.assign({}, original);
```

## 깊은 복사

> `객체의 모든 레벨의 프로퍼티를 복사한다.`

```javascript
const original {
  a:1,
  b: { c:2 }
};
// JSON 이용
const DeepCopy = JSON.parse(JSON.stringify(original));
```

: 하지만, 해당 방법은 순환 참조, Date, RegEXP등 특별한 객체를 정확히 복사하지 못할 수 있다. 이러한 경우 재귀함수나 외부 라이브러리(loDash, cloneDeep)를 통해 깊은 복사를 수행한다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./eventBubbling.md)

</div>
