# Gradient

- [linear-gradient](#1)
- [radial-gradient](#2)
- [conic-gradient](#3)

<Br>

2가지 이상의 색상을 혼합하여 부드러운 색감의 배경 등을 생성하는 것

- 색상은 최소 2가지, 그 이상은 제한없이 추가할 수 있음

배경처럼 [image](https://developer.mozilla.org/ko/docs/Web/CSS/image)를 사용하는 곳에는 어디에나 적용 가능

동적으로 직접 생성하므로 확대했을 때 래스터 이미지보다 좋은 품질 & 크기 조절도 가능

<br>

## `linear-gradient` <a id="1"></a>

선형, 위에서 아래로 진행 (방향 또는 각도를 지정하여 회전 가능)

- `0deg` 아래쪽에서 위쪽
- `90edg` 왼쪽에서 오른쪽
- 음의 각도는 시계 반대 방향으로 회전

color stop의 위치를 조정할 수 있음

- 백분율로 지정한다면 `0%` 시작점, `100%` 끝점을 나타냄
- 지정하지 않는 경우 자동으로 첫번째 color stop `0%`, 마지막 color stop `100%`
- 인접한 color stop을 동일한 위치로 설정하면 선을 만들 수 있음

기본적으로 한 색상에서 다음 색상으로 고르게 전환됨

- colot-hint로 midpoint의 transition value를 특정점으로 이동할 수 있음

## `radial-gradient` <a id="2"></a>

방사형, 중심점 위치를 지정할 수 있음

## `conic-gradient` <a id="3"></a>

각진 원형

시계 방향으로 전환

<br>

각각의 프로퍼티 앞에 `repeating-`을 붙이면 계속해서 반복

<Br>

CSS3가 비교적 최근부터 제공하는 기술

⇒ 대부분의 브라우저에 벤더프리픽스를 사용하여야 함

또한 브라우저에 따라 조금씩 문법이 상이하여 다루기가 수월하지 않음

따라서 직접 작성하는 것보다 작성 툴을 이용하는 것이 보편적

- [Gradient Generator](https://cssgradient.io/)

<Br>

## 참고

> [CSS3 Gradient | PoiemaWeb](https://poiemaweb.com/css3-gradient)  
> [Using CSS gradients - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Images/Using_CSS_gradients)
