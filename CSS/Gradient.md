# Gradient

- [linear-gradient](#1)
- [radial-gradient](#2)
- [conic-gradient](#3)
- [repeating-](#4)

<Br>

2가지 이상의 색상을 혼합하여 부드러운 색감의 배경 등을 생성하는 것

- 색상은 최소 2가지, 그 이상은 제한없이 추가할 수 있음

배경처럼 [image](https://developer.mozilla.org/ko/docs/Web/CSS/image)를 사용하는 곳에는 어디에나 적용 가능  
동적으로 직접 생성하므로 확대했을 때 래스터 이미지보다 좋은 품질 & 크기 조절도 가능

## `linear-gradient` <a id="1"></a>

선형, 위에서 아래로 진행

- 방향 또는 각도를 지정하여 회전 가능 (모서리를 지정하여 대각선도 가능)
- 양의 각도는 시계방향 (`0deg` 아래쪽에서 위쪽, `90edg` 왼쪽에서 오른쪽)
- 음의 각도는 시계 반대 방향으로 회전

color stop의 위치를 조정할 수 있음

- 백분율로 지정한다면 `0%` 시작점, `100%` 끝점 (범위를 벗어난 값도 가능)
- 지정하지 않는 경우 자동으로 첫번째 color stop `0%`, 마지막 color stop은 `100%`
- 인접한 color stop을 동일한 위치로 설정하면 선 그어짐  
  color stop은 두 위치를 가질 수 있음  
  이를 통해 CSS Images Level 3 방법과 CSS Images Level 4 다중 color stop 방법을 구현함

기본적으로 한 색상에서 다음 색상으로 고르게 전환됨

- colot-hint로 그라데이션의 중간 지점을 특정 점으로 이동하여 그라데이션의 진행을 제어할 수 있음

투명도를 지원하므로 여러 배경 또는 그라데이션을 쌓을 수 있음

- 위에서 아래로 쌓임 (첫번째 배경이 맨 위)

## `radial-gradient` <a id="2"></a>

방사형, 중심점에서 퍼진다는 점을 제외하고 선형과 유사  
중심점 위치를 지정할 수 있고, 원형 또는 타원형으로 만들 수 있음

- default: 중심은 50% 50%, 가로, 세로 비율이 일치하는 타원형

color stop과 중심점의 위치를 지정할 수 있음  
반지름의 크기를 지정할 수 있음

- `closest-corner`, `closest-side`, `farthest-corner`(기본값), `farthest-side` 중에서 선택

그라데이션을 쌓을 수 있음

- 위에서 아래로 쌓임 (첫번째 지정한 것이 맨 위)

## `conic-gradient` <a id="3"></a>

중심점을 기준으로 색상 전환이 회전함  
color stop은 호 주위에 배치 (절대 길이 지정 불가능)  
원 중심의 위쪽에서 시계 방향으로 색상이 전환  
중심과 각도를 지정할 수 있음 (`radial`/ `linear` 특성)

## `repeating-` <a id="4"></a>

각각의 프로퍼티 앞에 `repeating-`을 붙이면 계속해서 반복  
이를 이용하여 다양한 패턴을 만들 수 있음

<Br>

CSS3가 비교적 최근부터 제공하는 기술로 대부분의 브라우저에 벤더프리픽스를 사용하여야 함  
또한 브라우저에 따라 조금씩 문법이 상이하여 다루기가 수월하지 않음  
따라서 직접 작성하는 것보다 작성 툴을 이용하는 것이 보편적

- [Gradient Generator](https://cssgradient.io/)  
  <Br>

## 참고

> [CSS3 Gradient | PoiemaWeb](https://poiemaweb.com/css3-gradient)  
> [Using CSS gradients - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Images/Using_CSS_gradients)
