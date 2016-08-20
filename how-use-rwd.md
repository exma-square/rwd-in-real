RWD(Responsive Web Design)可稱為自適應網頁設計、響應式網頁設計、回應式網頁設計等等，是一種可以讓網頁的內容可以隨著不同的裝置的寬度來調整畫面呈現的技術，讓使用者可以不需要透過縮放的方式來瀏覽網頁，大大的提昇畫面的可瀏覽性及使用介面的親和度；然而這對於行動商務越來越受到重視的現今來說，隨之也越來越倍受重視。

近幾年，隨著行動裝置(智慧型手機、平板)的普及，以及行動上網服務的使用率越來越高，傳統網頁的標準已經無法符合這些裝置的需求來呈現了，尤其是以flash製作的動畫，受限於行動裝置運算力不足的限制之下，已經沒有行動裝置可以直接瀏覽flash製作的網頁了。雖然可透過一些特殊的瀏器APP軟體來觀看，但方便性卻大大的降低。
     
而RWD又是如何達到的呢? 主要是以HTML5的標準及CSS3中的media queries來達到的。

在HTML5的標準中，我們可以指定頁面的寬度可以依照裝置的檢視寬度來呈現，再利用CSS3的media queries 來設定不同寬度下使用不同的CSS來呈現頁面。因此設計師在設計網頁時，就必須要針對不同的寬度下的畫面編寫不同的CSS檔案供瀏覽器來讀取。

https://www.w3.org/TR/css3-mediaqueries/

HTML4 and CSS2 currently support media-dependent style sheets tailored for different media types. For example, a document may use sans-serif fonts when displayed on a screen and serif fonts when printed. ‘screen’ and ‘print’ are two media types that have been defined. Media queries extend the functionality of media types by allowing more precise labeling of style sheets.

A media query consists of a media type and zero or more expressions that check for the conditions of particular media features. Among the media features that can be used in media queries are ‘width’, ‘height’, and ‘color’. By using media queries, presentations can be tailored to a specific range of output devices without changing the content itself.

Responsive Styling
● CSS media queries
– Use in HTML link element to reference different style sheets according
to context of use, e.g.

```:html
<link rel="stylesheet" type="text/css"
 media="screen and (max-device-width: 480px)"
 href="shetland.css">
```

● W3C Recommendation 19 June 2012
– http://www.w3.org/TR/css3-mediaqueries/
– Widely supported by most modern browsers
– Ethan Marcotte's article 25 May 2010
● "Rather than quarantining our content into disparate, device-specific
experiences, we can use media queries to progressively enhance our work
within different viewing contexts."
– http://alistapart.com/article/responsive-web-design

http:\/\/webdesign.tutsplus.com\/tutorials\/a-simple-responsive-grid-made-even-better-with-sass--cms-21540



RWD media query

https:\/\/www.toptal.com\/designers\/responsive\/introduction-to-responsive-web-design-pseudo-elements-media-queries


```
@media (query) {
  /* CSS Rules used when query matches */
}
```


ref,

 * [Use CSS media queries for responsiveness](https://developers.google.com/web/fundamentals/design-and-ui/responsive/fundamentals/use-media-queries?hl=en)

