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
Section: 콘텐츠 영역 (다시 Article 영역으로 구분할 수 있음)  
Aside: Navigation item이나 부가 정보 영역   
두 개의 영역은 float 프로퍼티를 사용하여 수평 정렬 하는 것이 일반적  
⇒ [float 프로퍼티가 선언된 자식 요소를 포함하는 부모 요소의 높이가 정상적으로 반영되지 않는 문제](https://github.com/chichoc/TIL/blob/main/CSS/%EC%9A%94%EC%86%8C%EC%A0%95%EB%A0%AC.md#3) 를 해결해야함  

header 요소를 상단에 고정시키기 위해 `fixed` 프로퍼티를 사용
- 부모 요소와 관계없이 브라우저의 viewport를 기준으로 좌표 프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킴
- 스크롤이 되더라도 화면에서 사라지지 않고 항상 같은 곳에 위치  

좌측 aside 영역도 고정시키기 위해 `position: fixed`  
> 이때 %로 지정했던 width를 왜 px (=고정폭?)으로 변경하는지 이해 안 감

[heading tag(h1)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)의 크기가 위치한 영역에 따라 다름에 주의  
> header내의 h1는 존재하지 않음,  section내의 h1이 article내의 h1보다 크다는 의미가 아닐까 싶음

이를 위한 Reset CSS를 추가 (크기는 적당히 조절)

```css
h1 { font-size: 1.8em; }
```

## Footer <a id="3"></a>

고정되어 있을 필요는 있지만 본문을 가려서는 안되므로 `absolute` 프로퍼티를 설정

몇 가지 문제를 해결하기 위해서는 Responsive Web Design


## 참고
> [CSS3 Layout | PoiemaWeb](https://poiemaweb.com/css3-layout)  
[position - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
