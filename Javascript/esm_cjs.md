# ESM & CJS 모듈화 방법

## ESM(ECMAScript Module)

> ESM은 자바스크립트 표준에서 정의된 모듈 시스템이다. 이는 `import`와 `export`문을 사용하여 모듈을 불러오고 내보낸다. `ESM은 정적 모듈 구조를 가지고 있어, 컴파일 타임에 모듈 구조가 결정된다.`

## CJS(CommonJS Module)

> CJS는 Node.js에서 사용되는 모듈 시스템이다. `require()`함수를 사용해서 모듈을 불러오고 `module.exports`를 사용하여 내보낸다. CJS는 동적 모듈 구조를 가지고 있어, 런타임에 모듈이 로드되고 해석된다.

## 혼합 사용

- ESM파일에서 CJS 모듈 불러오기

```javascript
import cjsModule from 'module-name';
// or
(async () => {
  const cjsModule = await import('module-name');
})();
```

> import() 함수는 프로미스를 반환하므로, async/await 구문을 사용하여 처리할 수 있다.

- CJS 파일에서 ESM모듈 불러오기

```javascript
(async () => {
  const esModule = await import('./module.mjs');
})();
```

[처음으로](../README.md)
