---
title:  "Magnific popup 사용하기"
excerpt: "Magnific popup 사용하기"
categories:
  - Develop
tags:
  - javascript
  - jquery
---

레이어 팝업으로 이미지 원본 사이즈를 출력해야하는데  
개발자 및 퍼블리셔가 바빳던 관계로 라이브러리를 사용하였다.  

[magnific-popup 공식사이트](http://dimsemenov.com/plugins/magnific-popup/ )

```html
<link rel="stylesheet" href="/css/magnific-popup.css" /> 
<script src="/js/jquery.magnific-popup.js"> 

function goPicZoom() { 
    $.magnificPopup.open({ 
        items: { 
            src: 이미지주소, 
        }, 
        type: 'image', 
        closeOnContentClick : true, 
        tClose : tooltip.TOOLTIP_CLOSE 
    }); 
}
```