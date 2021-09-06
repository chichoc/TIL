# Typography

- [CDN (Content Delivery Neowork) 링크 방식](#1)
- [서버 폰트 로딩 방식](#2)

<br>

웹폰트는 사용자가 웹페이지를 요청한 순간 CSS에 기술된 필요 폰트가 서버에서 클라이언트로 전송됨

- 매번 다운로드되는 것은 아니고 클라이언트에 해당 폰트가 존재하지 않을 경우 전송

## CDN (Content Delivery Neowork) 링크 방식 <a id="1"></a>

웹폰트를 사용하는 가장 간단한 방법  
[Google Font](https://fonts.google.com/)에서 사용하고자 하는 웹폰트를 선택하여, 아래 구문을 CSS 파일에 추가

```css
/*나눔고딕 글꼴을 예시로 함*/
@import url(http://fonts.googleapis.com/earlyaccess/nanumgothic.css);

* { font-family: 'Nanum Gothic', sans-serif; }
```

@import rule의 `url` 함수는 서버에서 혹은 지정된 url에서 파일을 찾아 다운로드 함

### 단점

로컬 폰트를 사용하는 것에 비해 로딩 속도가 느림

CDN 링크를 제공하지 않는 폰트는 사용할 방법이 없음

## 서버 폰트 로딩 방식 <a id="2"></a>

CDN의 단점을 보완한 방법  
폰트 파일을 서버에 두고 요청이 오면 클라이언트로 전송하는 방식  
`@font-face` 규칙으로 폰트를 등록하고 `font-family` 프로퍼티로 폰트를 선택하여 사용할 수 있음

### 단점

브라우저에 따라 지원하는 폰트 파일 형식이 다름 [지원여부는 여기서 확인](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face#browser_compatibility)  
그래서 아래와 같이 브라우저에 따라 필요한 폰트만을 다운로드할 수 있음  
영문과 한글을 혼용하는 경우 영문폰트 다음에 한글 폰트를 지정하여야 함

- 한글 폰트부터 지정하면 영문에도 한글 폰트가 지정됨

```css
@font-face {
  font-family:"Nanum Gothic";
  src:url("NanumGothic.eot"); /* IE 9 호환성 보기 모드 대응 */
  src:local("☺"),             /* local font 사용 방지. 생략 가능 */
      url("NanumGothic.eot?#iefix") format('embedded-opentype'), /* IE 6~8 */
      url("NanumGothic.woff") format('woff'); /* 표준 브라우저 */
}

* { font-family: "Nanum Gothic", sans-serif; }
```

## 참고
>[CSS3 Web Font | PoiemaWeb](https://poiemaweb.com/css3-webfont)  
[@font-face - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face#browser_compatibility)
