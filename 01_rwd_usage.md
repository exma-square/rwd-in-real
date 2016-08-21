## RWD 規範

https://www.w3.org/TR/css3-mediaqueries/

RWD 大部分使用內容是根據 W3C 所規範的 media queries 進行實做，而這些規範並不是全新的系統架構，只是針對 HTML4 及 CSS2 本身之前的架構進行的延伸。

HTML4 及 CSS2 中就可以設定 `screen`， `print` 不同用途上有不同的設定，例如使用不同字型，使用不同的字體大小解析度。

所以對於 RWD 的使用方式，大多採用與 CSS2 CSS3 相同的描述方式，使用相同屬性給予方式進行網頁外觀的描述。

## RWD 起手式

RWD 主要是以 HTML 以及 CSS3 中 media queries 達成多重螢幕尺寸解析度的處理。

在 HTML5 的標準中，我們可以指定頁面的寬度可以依照裝置的檢視寬度來呈現，再利用 CSS 的media queries 設定不同螢幕解析度下使用不同的 CSS 結果來呈現頁面。

所以在專案一開始時，就需要進行螢幕尺寸進行規劃，以及設定條件限制，提供不同寬度畫面進行不同 CSS 的設定。

## 頁面解析度設定

手機裝置中除了上述的 media queries 描述條件之外，需要特別注意對於 `pixel` 此單位的描述。

對於不同螢幕解析度來說，pixel 並不代表同樣的單位，例如 iPhone 在 retina 解析度中，一個單位為 4 pixel ，在進行 media queries 通常都會不如預期。

因此需要透過 viewports 進行設定螢幕解析度，可以在 html 中的 head 之間加入 viewports，設定方式如下，

```
<html>
    <meta name="viewport" content="width=device-width, initial-scale=1">
</html>
```

## media queries 使用方法

首先在整個 html 架構裡面，我們可以透過以下方式進行引用，media queries 條件方式，

```
<link rel="stylesheet" type="text/css"
 media="screen and (max-device-width: 480px)"
 href="shetland.css">
```

又或者我們可以透過以下採用類似既有 CSS 的方式，但只是加上 `@media` 方式進行描述，

```
@media (query) {
  /* CSS Rules used when query matches */
}
```

以實際使用方式來看，如果需要設定尺寸與尺寸範圍之間，可以如下的設定方式，以下就是設定視窗寬度大於 400px 但小於 700px 時，套用某一段 selector 的屬性，此時屬性權重將會大於原本的設定，所以通常 media queries 如果都放置於同一個 css 檔案，通常都會置放於下方讓 css 描述權重提高。

```
@media screen and (min-width: 400px) and (max-width: 700px) {
    .selector {...}
}
```

如果視窗最小尺寸的時候，可以設定為500px，使用方式可以如下，

```
@media screen and (min-width:500px) {
    .selector {...}  
}
```

如果視窗為直立，採用方式如下

```
@media screen and  (orientation: portrait) {
    .selector {...}  
}
```

## 其他使用方法

除了上面的直述式 css 描述方式之外，也可以透過引用的方式來進行，條件及過濾方法同樣，僅會採用某段 css 檔案，

```
<link rel="stylesheet" media="not|only screen and (color)" href="example.css" />
```

某些舊版瀏覽器只能讀media type(screen,projector等等)，不會讀media feature，也不會讀not或only，因此也不會套用此media query後的CSS檔。

## RWD 直接套用

如果你跟我一樣不想知道原理，只想要快點使用，可以透過以下的範例直接套用在自己的 css 檔案中，開始進行瀏覽，透過 chrome 瀏覽器，可以透過 `開發者模式工具` 進行手持式裝置模擬，模擬視窗大小，以及點擊效果，看到實際的 css 編寫結果，

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

### 參考資料

 * [Use CSS media queries for responsiveness](https://developers.google.com/web/fundamentals/design-and-ui/responsive/fundamentals/use-media-queries?hl=en)
 * [Responsive design – harnessing the power of media queries](https://webmasters.googleblog.com/2012/04/responsive-design-harnessing-power-of.html)
 * [MEDIA QUERIES FOR COMMON DEVICE BREAKPOINTS](https://responsivedesign.is/develop/browser-feature-support/media-queries-for-common-device-breakpoints)

