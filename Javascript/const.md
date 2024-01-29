# Const의 immutable

## const

> `const변수는 일정한 상수 값을 유지`한다. const는 `업데이트 및 재선언이 불가하다.(메모리 주소의 참조를 변경할 수 없다.)` 하지만, 변수가 가리키는 객체의 내부 속성에 대한 변경은 금지하지 않았다.

## const의 immutable

> 'const'로 선언된 변수는 재할당이 불가하고 이는 const가 가리키는 값의 `불변성`을 의미한다. 'const'로 선언된 배열에 새로운 요소를 추가하거나 객체의 속성을 변경하는 것이 가능하다. 이는 const가 메모리 주소의 불변성을 보장하고, 그 주소가 가리키는 데이터 주소는 불변하지 않기 때문이다. 즉, `const의 불변성은 변수에 할당된 값의 재할당을 막는 것에 한정되며, 참조 타입의 경우 내부요소에 대해서는 불변성을 보장하지 않는다.`

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./function.md)

</div>
