# Vendor Prefix

CSS3 표준으로 확장되기 이전 또는 브라우저 개발사가 실험적으로 제공하는 기능을 사용하기 위해서 사용하여야 함

브라우저별 CSS 지원 정보는 [Can I use](https://caniuse.com/) 에서 확인 가능

브라우저 버전이 올라감에 따라 사용하지 않아도 될 수 있지만, 구형 브라우저를 지원하기 위해서는 사용할 필요가 있음

- `-webkit-`

  Chrome, Safari, newer versions of Opera, almost all iOS browsers including Firefox for iOS; basically, any WebKit based browser

- `-moz-`

  Firefox

- `-o-`

  old pre-WebKit versions of Opera

- `-ms-`

  Internet Explorer and Microsoft Edge

<br>

많은 브라우저를 위해 vendor prefix를 사용하는 것은 코드의 양을 늘게 하고, 브라우저는 거의 매달 업데이트가 이루어지고 있어 불필요한 vendor prefix를 사용할 가능성이 큼

사용하지 않아도 되는 vendor prefix를 사용하는 것은 성능에도 영향을 주기 때문에 vendor prefix없이 모든 CSS를 사용할 수 있는 라이브러리를 사용하는 것이 유용

- 사용법: [Prefix 라이브러리](https://projects.verou.me/prefixfree/)를 다운로드하고 include

  ```html
  <script src="prefixfree.min.js"></script>
  ```

## 참고

> [CSS3 Vendor Prefix | PoiemaWeb](https://poiemaweb.com/css3-vendor-prefix)  
> [Vendor Prefix - Web Docs Glossary: Definitions of Web-related terms | MDN](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix)
