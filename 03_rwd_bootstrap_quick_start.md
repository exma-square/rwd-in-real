# 快速使用 Bootstrap

首先進行安裝 `bower`

```
npm install -g bower
```

透過 bower 安裝最新的 bootstrap

```
bower install bootstrap
```

安裝後資料儲存架構如下

```
└── bower_components
    ├── bootstrap
    │   ├── CHANGELOG.md
    │   ├── Gemfile
    │   ├── Gemfile.lock
    │   ├── Gruntfile.js
    │   ├── ISSUE_TEMPLATE.md
    │   ├── LICENSE
    │   ├── README.md
    │   ├── bower.json
    │   ├── dist
    │   │   ├── css
    │   │   │   ├── bootstrap-theme.css
    │   │   │   ├── bootstrap-theme.css.map
    │   │   │   ├── bootstrap-theme.min.css
    │   │   │   ├── bootstrap-theme.min.css.map
    │   │   │   ├── bootstrap.css
    │   │   │   ├── bootstrap.css.map
    │   │   │   ├── bootstrap.min.css
```

資料夾中如果有以上架構，表示安裝完成，接著可以新增 `index.html` 網頁，讓 bootstrap 可以生動活潑進行載入。

index.html
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
```

### Step01

因為我們頁面上會需要 container 還有接下來 menu 的加入，因此需要設定自己的 css 檔案將 bootstrap 的預設樣式進行調整，所以會需要進行設定引入 css 檔案方式。

請在 `link` bootstrap 連結底下增加引入 `starter-template.css`

```
<link rel="stylesheet" type="text/css" href="./assert/css/starter-template.css">
```

### Step02

在頁面中試著加入 `Bootstrap menu` ，將底下這段 nav 的部分加入到 body 開頭之後，設定網站的 menu 內容。

```
    <nav class="navbar navbar-inverse navbar-fixed-top">
      <div class="container">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="#">Project name</a>
        </div>
        <div id="navbar" class="collapse navbar-collapse">
          <ul class="nav navbar-nav">
            <li class="active"><a href="#">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>
        </div>
      </div>
    </nav>
```

### Step03

此時會發現 h1 的內容被 menu 蓋住了，因此需要 container 的協助，透過容器將 h1 包起來。

```
    <div class="container">
      <div class="starter-template">
        <!-- Step03-1. 將 h1 貼上到此方下方處 -->
        <h1>Hello, world!</h1>
      </div>
    </div>
```

### Final

透過 web server 我們測試一下，內容結果應該符合如下的畫面，就表示我們使用 bootstap 框架正式成功，這也是我們第一個完美的 starter bootstrap page.

![](https://cldup.com/XY36IbmXD4.png)

同時我們也可以透過手機螢幕測試，或者透過 chrome 模擬手機瀏覽狀態，會看到 RWD menu 的樣式立即呈現在各位面前。

![](https://cldup.com/UBxGS6rY-L.png)