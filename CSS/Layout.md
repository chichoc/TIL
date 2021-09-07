# Layout

- [Header & Navigation Bar](#1)
- [Section & Aside](#2)
- [Footer](#3)

<Br>

Layout: 웹사이트를 구성하는 요소들을 배치할 공간을 분할하고 정렬하는 것  
핵심은 블록 레벨 요소들을 원하는 위치에 배열하는 것  
table을 사용하면 반응형 웹 페이지 작성이 곤란하고, 코드의 양이 많아져 거의 사용하지 않음  
자주 사용되는 핵심 기술은 `float`

## Header & Navigation Bar <a id="1"></a>

Navigation Bar: 기본적인 링크들의 리스트  
ul, li tag를 이용하여 작성하는 것이 일반적  
- a tag는 inline요소이므로 margin을 정의하기 위해서 `display: inline-block`을 설정
- li tag는 block요소이므로 가로 정렬을 위해 `display: inline-block`을 설정  

실제 웹사이트를 구축할 시에는 Reset CSS를 정교하게 초기화할 필요가 있음

## Section & Aside <a id="2"></a>
Section: 콘텐츠 영역 > Article 영역으로 구분할 수 있음  
Aside: Navigation item이나 부가 정보 영역   
두 개의 영역은 float 프로퍼티를 사용하여 수평 정렬 하는 것이 일반적  
⇒ [float 프로퍼티가 선언된 자식 요소를 포함하는 부모 요소의 높이가 정상적으로 반영되지 않는 문제](https://github.com/chichoc/TIL/blob/main/CSS/%EC%9A%94%EC%86%8C%EC%A0%95%EB%A0%AC.md#3) 를 해결해야함  

header 요소를 상단에 고정시키기 위해 `fixed` 프로퍼티를 사용
- 부모 요소와 관계없이 브라우저의 viewport를 기준으로 좌표 프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킴
- 스크롤이 되더라도 화면에서 사라지지 않고 항상 같은 곳에 위치

## Footer <a id="3"></a>

## 참고
> [CSS3 Layout | PoiemaWeb](https://poiemaweb.com/css3-layout)
