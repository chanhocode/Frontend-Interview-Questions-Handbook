# 브라우저 렌더링 원리

> 브라우저는 레ㄴ더링을 위해 웹킷(Webkit) 또는 게코(Gecko)와 같은 렌더링 엔진을 사용한다. 렌더링 엔진이 HTML, CSS, Javascript로 렌더링할 때 CRP(Critical Rendering Path) 프로세서를 사용한다.

1. `문서 요청과 로딩(DOM Loading)`

- [ HTML 파싱 후, DOM Tree 구축 ]
- 사용자가 URL을 입력하면, 브라우저는 해당 주소의 서버에 HTTP 요청을 보낸다.
- 서버는 요청받은 HTML 문서를 응답으로 보낸다.
- 브라우저는 HTML문서를 받아 DOM Tree를 구축한다.

2. `CSS 파싱 후, CSSOM(CSS Object Model)트리 구축`

- HTML과 함께 로드된 CSS파일은 파싱되어 CSSOM 트리를 생성한다.
- CSSOM은 HTML요소의 스타일을 결정하는데 사용된다.

3. `Javascript 실행, 이때 HTML 중간에 스크립트가 있다면 HTML 파싱이 중단된다.`

4. `DOM과 CSSOM을 조합하여 렌더트리(Render Tree) 구축`

- 렌더 트리는 화면에 실제로 보여질 요소들과 그 스타일 정보를 포함한다.

5. `뷰포트 기반으로 렌더트리의 각 노드가 가지는 정확한 위치와 크기를 계산한다.(Layout 과정)`

- 이 과정을 통해 각 요소가 화면의 어디에 위치해야 할지 결정된다.

6. `계산한 위치/크기를 기반으로 화면에 그린다.(Paint 과정)`

- 레이아웃이 완료된 후, 실제로 요소를 화면에 그리는 과정

7. `합성(Compositing 과정)`

- 여러 레이어를 합쳐 최종적인 화면을 사용자에게 보여주는 과정이다.
- 이 과정은 복잡한 애니메이션과 효과가 적용된 페이지에서 더 중요해진다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./Storage.md)

</div>
