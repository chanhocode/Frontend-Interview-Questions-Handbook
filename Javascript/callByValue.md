# Call By Value

: Javascript는 함수의 매개변수를 넘길 때 어떤 값들, 참조형, 기본형으로 넘기든 무조건 Call By Value로 넘긴다.

> 참조형을 넘긴 경우 주소값이 복사되어 객체 속성값 변경시 함수 밖 변수도 변경된다.

⚙️ 추가

- `참조형: 객체, 배열, 함수, 날짜, 정규표현식`
- `기본형: 숫자, 문자열, 불린값, null, undefined, 심볼`

- 데이터 타입에 대한 설명
  자바스크립트의 타입은 원시값과 객체로 나뉜다. 원시값은 불변 값을 의미하며 이에는 number, biging, string,boolean, symbol, null, undefined 타입이 있다. 객체는 키와 값 사이의 매핑이며, 키는 문자열 또는 심볼 이다. 값은 어떤 것이든 가능하다. 함수는 호출이 가능하다는 점을 제외하면 일반적인 객체이다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./undefined_null_undeclared.md)

</div>
