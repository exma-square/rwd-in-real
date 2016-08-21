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

Viewports
When is a pixel not a pixel? When it’s on a smartphone. By default, smartphone browsers pretend to be high-resolution desktop browsers, and lay out a page as if you were viewing it on a desktop monitor. This is why you get a tiny-text “overview mode” that’s impossible to read before zooming in. The default viewport width for the default Android browser is 800px, and 980px for iOS, regardless of the number of actual physical pixels on the screen.
In order to trigger the browser to render your page at a more readable scale, you need to use the viewport meta element:

```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

RWD media query

https:\/\/www.toptal.com\/designers\/responsive\/introduction-to-responsive-web-design-pseudo-elements-media-queries


```
@media (query) {
  /* CSS Rules used when query matches */
}
```

```
@media screen and (min-width: 400px) and (max-width: 700px) {
    .selector1{...}
    .selector2{...}
}
```

意思就是在視窗寬度大於400px但小於700px時，套用example.css這個CSS檔。

CSS檔中，@media後面列的條件就是對應HTML<link media=“…..”> 引號內的東西。在@media{}大括號之內，就如往常一樣撰寫此media條件下的CSS設定。

單一條件

例：如果視窗最小寬度為500px，就套用這些CSS

@media screen and (min-width:500px) {.....}
例：如果視窗為直立，就套用這些CSS

@media screen and  (orientation: portrait) {.....}
兩者需同時符合

例：如果視窗在400px和700px之間，就套用這些CSS

@media screen and (min-width: 400px) and (max-width: 700px)
兩者符合一種即可

例：如果是彩色螢幕或彩色投影機兩者之一，就套用這些CSS

@media screen and (color), projection and (color) {.....}
以not/only 迴避或強制舊版瀏覽器執行

<link rel="stylesheet" media="not|only screen and (color)" href="example.css" />
某些舊版瀏覽器只能讀media type(screen,projector等等)，不會讀media feature，也不會讀not或only，因此也不會套用此media query後的CSS檔。

《屬性和值》

media type 有以下幾種： 
all | aural | braille | handheld | print | projection | screen | tty | tv | embossed
media features 
* (max-或min-)width:[數字] 
* (max-或min-)height:[數字] 
* (max-或min-)device-width:[數字] 
* (max-或min-)device-height:[數字] 
* orientation:portrait 或 landscape 
* aspect-ratio:[比值] 
* (max-或min-)device-aspect-ratio:[比值] 
* color 
* color-index 
* monochrome 
* (max-或min-)resolution:[數字]dpi 
* scan(只對tv) 
* grid
這方面W3C文件也還在W3C Recommandation的階段，也不算進入Standard

很多人關心handheld這個media type，但事實上它已無法有效偵測是否為手機browser。前一代智慧型手機很多用Opera上網，Opera確定是可以辨認這個media type的。

會讀handheld的手機瀏覽器有:
OpenWave, Nokia lite-web browsers, Netfront, Digia, BlackBerry browser, Opera Mini until v4, Opera Mobile until v9,Palm’s Blazer, Nokia S40 browser, IEMobile 6.x and 8.x

(http://www.alistapart.com/articles/putyourcontentinmypocket/)

CSS支援度

目前大部分手機瀏覽器與桌機瀏覽器支援的CSS相差不大，但有需要慎用的的CSS屬性

overflow
position:fixed(iphone safari確定不支援)
font-family:手機上的字型比桌機少
font-size: 用small, medium, large，最好不要用px設死
margin與padding的算法可能有個別差異
box model的處理

手機版網頁在自動適應畫面寬度時，目前標準的padding算法會是個困擾，因為如果width:100%，加上padding可能就破版了，但不使用width:100%又很難估計內容的實際寬度。這時可考慮回復到IE6模式，把border和padding的移到box內部，如此一來宣告width為100%就能保證不破版。

div{
     -webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
     -moz-box-sizing: border-box;    /* Firefox, other Gecko */
     box-sizing: border-box;
}
*註:border-box是IE6的模式，content-box是目前的標準模式

```
/* Smartphones (portrait and landscape) ----------- */
@media only screen and (min-device-width : 320px) and (max-device-width : 480px) {
/* Styles */
}

/* Smartphones (landscape) ----------- */
@media only screen and (min-width : 321px) {
/* Styles */
}

/* Smartphones (portrait) ----------- */
@media only screen and (max-width : 320px) {
/* Styles */
}

/* iPads (portrait and landscape) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) {
/* Styles */
}

/* iPads (landscape) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape) {
/* Styles */
}

/* iPads (portrait) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait) {
/* Styles */
}
/**********
iPad 3
**********/
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}
/* Desktops and laptops ----------- */
@media only screen  and (min-width : 1224px) {
/* Styles */
}

/* Large screens ----------- */
@media only screen  and (min-width : 1824px) {
/* Styles */
}

/* iPhone 4 ----------- */
@media only screen and (min-device-width : 320px) and (max-device-width : 480px) and (orientation : landscape) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

@media only screen and (min-device-width : 320px) and (max-device-width : 480px) and (orientation : portrait) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

/* iPhone 5 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 568px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 568px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* iPhone 6 ----------- */
@media only screen and (min-device-width: 375px) and (max-device-height: 667px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 375px) and (max-device-height: 667px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* iPhone 6+ ----------- */
@media only screen and (min-device-width: 414px) and (max-device-height: 736px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 414px) and (max-device-height: 736px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* Samsung Galaxy S3 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* Samsung Galaxy S4 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

/* Samsung Galaxy S5 ----------- */
@media only screen and (min-device-width: 360px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

@media only screen and (min-device-width: 360px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}
```

ref,

 * [Use CSS media queries for responsiveness](https://developers.google.com/web/fundamentals/design-and-ui/responsive/fundamentals/use-media-queries?hl=en)
 * [Responsive design – harnessing the power of media queries](https://webmasters.googleblog.com/2012/04/responsive-design-harnessing-power-of.html)
 * [MEDIA QUERIES FOR COMMON DEVICE BREAKPOINTS](https://responsivedesign.is/develop/browser-feature-support/media-queries-for-common-device-breakpoints)

