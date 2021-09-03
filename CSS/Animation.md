# Animation

- [@keyframes](#1)
- [animation-name](#2)
- [animation-duration](#3)
- [animation-timing-function](#4)
- [animation-delay](#5)
- [animation-iteration-count](#6)
- [animation-direction](#7)
- [animation-fill-mode](#8)
- [animation-play-state](#9)
- [animation](#10)

<br>

HTML요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 변화시킴

애니메이션을 나타내는 CSS 스타일과 애니메이션의 sequence를 나타내는 복수의 키프레임(`@keyframes`) 들로 이루어짐

<details>
<summary>transition으로도 어느 정도의 애니메이션 효과를 표현할 수 있으나 animation보다는 제한적</summary>
<div markdown="1">

일반적으로 요소 프로퍼티값이 다른 값으로 변화할 때 주로 사용함  
요소의 로드와 함께 자동으로 발동되지 않고, [가상 클래스 선택자(Pseudo-Class Selector)](https://poiemaweb.com/css3-selector#7-%EA%B0%80%EC%83%81-%ED%81%B4%EB%9E%98%EC%8A%A4-%EC%85%80%EB%A0%89%ED%84%B0-pseudo-class-selector) 또는 자바스크립트의 이벤트와 같은 부수적 액션에 의해 발동됨

</div>
</details>

즉 transition 프로퍼티는 단순히 요소의 프로퍼티 변화에 주안점이 있다면  
animation 프로퍼티는 하나의 줄거리를 구성하여 줄거리 내에서 세부 움직임을 시간 흐름 단위로 제어할 수 있고 전체 줄거리의 재생과 정지, 반복까지 제어할 수 있음  
비교적 작은 효과나 CSS만으로 충분한 효과를 볼 수 있는 것은 CSS 사용 ex) width 변경  
세밀한 제어를 위해서는 JS 사용이 바람직 ex) 바운스, 중지, 일시중지, 되감기 또는 감속

가장 중요한 것은 브라우저에서 애니메이션 효과가 부드럽게 실행되는 것, 애니메이션 효과 작성에 소요되는 시간과 수고

### animation 프로퍼티

| 프로퍼티                  | 설명                                                                                                             | 기본값  |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------- | :-----: |
| animation-name            | @keyframes 애니메이션 이름을 지정                                                                                |         |
| animation-duration        | 한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정                                 |   0s    |
| animation-timing-function | 애니메이션 효과를 위한 타이밍 함수를 지정                                                                        |  ease   |
| animation-delay           | 요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정 |   0s    |
| animation-iteration-count | 애니메이션 재생 횟수를 지정                                                                                      |    1    |
| animation-direction       | 애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정                                                          | normal  |
| animation-fill-mode       | 애니메이션 미실행 시(종료 또는 대기) 요소의 스타일을 지정                                                        |         |
| animation-play-state      | 애니메이션 재생 상태(재생 또는 중지)를 지정                                                                      | running |
| animation                 | 모든 애니메이션 프로퍼티를 한번에 지정 (shorthand syntax)                                                        |         |

## @keyframes <a id="1"></a>

rule은 시간의 흐름에 따라 애니메이션을 정의

- 여러 개의 keyframe을 정의하거나 애니메이션 중에 특정 CSS 프로퍼티에 값을 지정하는 지점을 정의할 수 있음
- 애니메이션의 흐름(sequence) 중의 여러 시점(breakpoint)에서 CSS 프로퍼티값을 지정할 수 있음
- CSS 애니메이션과 transition 방식의 주된 차이

```css
/* @keyframes rule */
@keyframes move {
  /* 애니메이션 시작 시점 */
  from {
    left: 0;
  }
  /* 애니메이션 종료 시점 */
  to {
    left: 300px;
  }
}

@keyframes move {
  0% {
    left: 0;
  }
  50% {
    left: 100px;
  }
  100% {
    left: 300px;
  }
}
```

## animation-name <a id="2"></a>

`@keyframes` 뒤에 부여한 이름을 프로퍼티값으로 지정하여 사용하고자 하는 @keyframes rule을 선택  
하나 이상의 애니메이션 이름을 지정할 수 있음

## animation-duration <a id="3"></a>

한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정  
반드시 지정해야 함

- 지정하지 않는 경우 기본값 0s가 셋팅되어 어떠한 애니메이션도 실행되지 않음

## animation-timing-function <a id="4"></a>

애니메이션 효과를 위한 수치 함수를 지정

- 수치함수는 [transition-timing-function 프로퍼티](https://github.com/chichoc/TIL/blob/main/CSS/transition.md#3)와 동일

## animation-delay <a id="5"></a>

요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정

## animation-iteration-count <a id="6"></a>

애니메이션 주기의 재생 횟수를 지정  
기본값은 1이며 infinite로 무한반복 할 수 있음

## animation-direction <a id="7"></a>

애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정
| 프로퍼티 | 설명 |
| ---------- | ------------------------------------------------------------------------------------------------------------------------ |
normal | from(0%)에서 to(100%) 방향으로 진행 (기본값)|
reverse | to에서 from 방향으로 진행|
alternate | 홀수번째는 normal로, 짝수번째는 reverse로 진행|
alternate-reverse | 홀수번째는 reverse로, 짝수번째는 normal로 진행

## animation-fill-mode <a id="8"></a>

애니메이션 미실행 시(대기 또는 종료) 요소의 스타일을 지정

| 프로퍼티  | 상태 | 설명                                                                   |
| --------- | :--: | ---------------------------------------------------------------------- |
| none      | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기                 |
|           | 종료 | 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료 |
| forwards  | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기                 |
|           | 종료 | 종료 프레임(to)에 설정한 스타일을 적용하고 종료                        |
| backwards | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하고 대기                      |     |
|           | 종료 | 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료 |
| both      | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하고 대기                      |
|           | 종료 | 종료 프레임(to)에 설정한 스타일을 적용하고 종료                        |

## animation-play-state <a id="9"></a>

애니메이션 재생 상태(재생 또는 중지)를 지정

- `running`

  기본값, 애니메이션 계속 재생

- `paused`

  애니메이션 중지

## animation <a id="10"></a>

모든 애니메이션 프로퍼티를 한번에 지정  
값을 지정하지 않은 프로퍼티에는 기본값이 지정됨

- animation-duration은 반드시 지정해야 함  
  지정하지 않는 경우 기본값 0s가 셋팅되어 어떠한 애니메이션도 실행되지 않음

```css
animation: name duration timing-function delay iteration-count direction
  fill-mode play-state;
/*기본값: none 0 ease 0 1 normal none running*/
```

## 참고

> [CSS3 Animation | PoiemaWeb](https://poiemaweb.com/css3-animation)  
> [Using CSS animations | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)  
> [CSS Animations Level 1 | W3C](https://drafts.csswg.org/css-animations/#animation)
