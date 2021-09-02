# Transition

- [transition-property](#1)
- [transition-duration](#2)
- [transition-timing-function](#3)
- [transition-delay](#4)
- [transition](#5)

<Br>

프로퍼티 값의 변경이 표시의 변화에 즉시 영향을 미치게 하는 대신 그 프로퍼티 값의 변화가 **일정 시간(duration)** 에 걸쳐 일어나도록 하는 것  
즉, transition은 상태 변화에 동반하여 변경되는 CSS 프로퍼티 값에 의한 표시의 변화를 부드럽게 하기 위해 애니메이션 속도를 조절함  
자동으로 발동되지 않음

- 가상 클래스 선택자(Pseudo-Classes) 또는 JavaScript의 부수적인 액션에 의해 발동
- 자동 발동하도록 하고 싶다면 CSS 애니메이션을 사용해야함

### transition의 프로퍼티

| 프로퍼티                   | 설명                                                                                                                 | 기본값 |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------- | :----: |
| transition-property        | 트랜지션의 대상이 되는 CSS 프로퍼티를 지정함                                                                         |  all   |
| transition-duration        | 트랜지션이 일어나는 지속시간(duration)을 초 단위(s) 또는 밀리 초 단위(ms)로 지정함                                   |   0s   |
| transition-timing-function | 트랜지션 효과를 위한 수치 함수를 지정함                                                                              |  ease  |
| transition-delay           | 프로퍼티가 변화한 시점과 트랜지션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정함 |   0s   |
| transition                 | 모든 트랜지션 프로퍼티를 한번에 지정함 (shorthand syntax)                                                            |

## transition-property <a id="1"></a>

transition의 대상이 되는 CSS 프로퍼티명을 지정함  
지정하지 않는 경우 모든 프로퍼티가 transition의 대상이 됨  
쉼표로 구분하여 복수 지정 가능  
주의) 모든 CSS 프로퍼티가 transition의 대상이 될 수 없음

- display 프로퍼티는 하나의 범주 안에서 값이 변화하지 않음

### transition 대상이 될 수 있는 CSS 프로퍼티

| 프로퍼티   | 설명                                                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------------------------------------ |
| Box model  | width height max-width max-height min-width min-height <br> padding margin <br> border-color border-width border-spacing |
| Background | background-color background-position                                                                                     |
| 좌표       | top left right bottom                                                                                                    |
| 텍스트     | color font-size font-weight letter-spacing line-height <Br> text-indent text-shadow vertical-align word-spacing          |
| 기타       | opacity outline-color outline-offset outline-width visibility z-index                                                    |

요소의 프로퍼티 값이 변화하면 브라우저는 프로퍼티 값의 변화에 영향을 받는 모든 요소의 기하값(위치와 크기)을 계산하여 layout 작업을 수행함  
심지어 다수의 자식 요소를 가지고 있는 요소가 변경되면 모든 자식 요소의 기하값이 재계산될 수도 있음  
성능 저하의 요인이므로 layout에 영향을 주는 transition 효과는 회피하도록 노력해야함

- layout에 영향을 주는 프로퍼티

  ```css
  width height padding margin border
  display position float overflow
  top left right bottom
  font-size font-family font-weight
  text-align vertical-align line-height
  clear white-space
  ```

## transition-duration <a id="2"></a>

transition에 일어나는 지속시간(duration)을 초 단위(s) 또는 밀리 초 단위(ms)로 지정함  
**프로퍼티값을 지정하지 않을 경우 기본값 0s이 적용되어 어떠한 트랜지션 효과도 볼 수 없음**  
transition-duration 프로퍼티값은 transition-property 프로퍼티값과 1:1 대응함

- transition-property 프로퍼티값을 복수 지정한 경우 마찬가지로 쉼표로 구분하여 복수 지정

## transition-timing-function <a id="3"></a>

일종의 변화 리듬(transition 효과의 변화 흐름, 시간에 빠른 변화 속도)을 지정함  
대부분의 타이밍 함수는 cubic bezier를 정의하는 네 점에 의해 정의되므로 상응하는 함수의 그래프로 제공해서 명시할 수 있음

- ease (기본값)  
  느리게 시작하여 점점 빨라졌다가 느리지면서 종료

  <img src="https://poiemaweb.com/img/cubic-bezier-ease.png" width="22%" height="20%"/>

- linear  
  시작부터 종료까지 등속 운동

   <img src="https://poiemaweb.com/img/cubic-bezier-linear.png" width="22%" height="20%"/>

- ease-in  
  느리게 시작한 후 일정한 속도에 다다르면 그 상태로 등속 운동

  <img src="https://poiemaweb.com/img/cubic-bezier-ease-in.png" width="22%" height="20%"/>

- ease-out  
  일정한 속도의 등속으로 시작해서 점점 느려지면서 종료

  <img src="https://poiemaweb.com/img/cubic-bezier-ease-out.png" width="22%" height="20%"/>

- ease-in-out  
  느리게 시작하여(ease와 비슷) 느리지면서 종료

  <img src="https://poiemaweb.com/img/cubic-bezier-ease-in-out.png" width="22%" height="20%"/>

## transition-delay <a id="4"></a>

프로퍼티가 변화한 시점과 transition이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정  
즉시 트랜지션이 실행되지 않고, 일정 시간 대기한 후 transition이 실행되도록 함

## transition <a id="5"></a>

모든 transition 프로퍼티를 한번에 지정할 수 있는 shorthand  
값을 지정하지 않은 프로퍼티에는 기본값이 지정됨

```css
transition: property duration function delay;
/*기본값: all 0 ease 0*/
```

## 참고

> [CSS3 Transition | PoiemaWeb](https://poiemaweb.com/css3-transition)  
> [CSS Transitions | W3C](https://www.w3.org/TR/css3-transitions/#transition-shorthand-property)
