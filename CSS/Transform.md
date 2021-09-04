# Tranform

- [2D Transform](#1)
- [3D Transform ](#2)

요소에 translate(이동), rotate(회전), scale(확대축소), skew(비틀기) 효과를 부여하기 위한 함수를 제공  
단, 애니메이션 효과를 제공하지는 않기 때문에 정의돈 프로퍼티가 바로 적용되어 화면에 표시됨 <details>

<summary>애니메이션 효과를 부여할 필요가 있다면 transition이나 animation과 함께 사용</summary>
<div markdown="1">

- transition: CSS 스타일 변경을 부드럽게 표현하기 위해 duration(지속시간)을 부여하여 속도 조절
- animation: 구성한 하나의 @keyframes (줄거리) 내에서 세부 움직임을 시간 흐름 단위로 제어하여 요소의 움직임을 표현
</div>
</details>

## 2D Transform <a id="1"></a>

프로퍼티값으로 transform function를 사용

### trnasform function

| 프로퍼티              | 설명                                                  |     단위      |
| --------------------- | ----------------------------------------------------- | :-----------: |
| translate(x,y)        | 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동       | px, %, em 등  |
| translateX(n)         | 요소의 위치를 X축으로 x만큼 이동                      | px, %, em 등  |
| translateY(n)         | 요소의 위치를 Y축으로 y만큼 이동                      | px, %, em 등  |
| scale(x,y)            | 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 |   0과 양수    |
| scaleX(n)             | 요소의 크기를 X축으로 x배 확대 또는 축소              |   0과 양수    |
| scaleY(n)             | 요소의 크기를 Y축으로 y배 확대 또는 축소              |   0과 양수    |
| skew(x-angle,y-angle) | 요소를 X축으로 x 각도만큼, Y축으로 y 각도만큼 기울임  | +/- 각도(deg) |
| skewX(x-angle)        | 요소를 X축으로 x 각도만큼 기울임                      | +/- 각도(deg) |
| skewY(y-angle)        | 요소를 Y축으로 y 각도만큼 기울임                      | +/- 각도(deg) |
| rotate(angle)         | 요소를 angle만큼 회전시킴                             | +/- 각도(deg) |

### transform

프로퍼티값으로 transform function을 나열함

- 복수 개를 나열할 경우 공백으로 구분 (쉼표 없음)

나열순서에 따라 차례대로 효과가 적용됨

> 16.1.1.html에서 original box와 달리 child box에서는 margin을 지정안했는데도 둘의 위치가 같은 점이 이해가 안감 (margin은 상속되지 않는 프로퍼티)

### transform-origin

요소의 기본기준점을 설정할 때 사용

- 기본기준점: 요소의 정중앙(50%, 50%)

설정값으로 %, px, top left, bottom right을 사용할 수 있음

- 0, 0은 top left, 100% 100%는 bottom right과 같은 값
- 이동은 기준점을 변경하여도 일정 거리만큼 이동하므로 의미가 없음

## 3D Transform <a id="2"></a>

프로퍼티값으로 transform function을 사용

### trnasform function
**굵은 글씨** 프로퍼티는 2D Transform function에 없던 새로운 함수
| 프로퍼티               | 설명                                                               |     단위      |
| ---------------------- | ------------------------------------------------------------------ | :-----------: |
| **translate3d(x,y,z)** | 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 Z축으로 z만큼 이동      | px, %, em 등  |
| translateX(n)          | 요소의 위치를 X축으로 x만큼 이동                                   | px, %, em 등  |
| translateY(n)          | 요소의 위치를 Y축으로 y만큼 이동                                   | px, %, em 등  |
| **translateZ(n)**      | 요소의 위치를 Z축으로 z만큼 이동                                   | px, %, em 등  |
| **scale3d(x,y)**       | 요소의 크기를 X축으로 x배, Y축으로 y배, Z축으로 z배 확대 또는 축소 |   0과 양수    |
| scaleX(n)              | 요소의 크기를 X축으로 x배 확대 또는 축소                           |   0과 양수    |
| scaleY(n)              | 요소의 크기를 Y축으로 y배 확대 또는 축소                           |   0과 양수    |
| **scaleZ(n)**          | 요소의 크기를 Z축으로 z배 확대 또는 축소                           |   0과 양수    |
| **rotate3d(x,y,z)**    | 요소를 X축으로 x각도, Y축으로 y각도, Z축으로 z각도 회전            | +/- 각도(deg) |
| **rotateX(x)**         | 요소를 X축으로 x각도 회전                                          | +/- 각도(deg) |
| **rotateY(y)**         | 요소를 Y축으로 y각도 회전                                          | +/- 각도(deg) |
| **rotateZ(z)**         | 요소를 Z축으로 z각도 회전                                          | +/- 각도(deg) |

## 참고

> [CSS3 Transform | PoiemaWeb](https://poiemaweb.com/css3-transform)  
> [cursor - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/cursor)  
> [transform - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/transform)
