<div align="center">
    <h1>Html head標籤</h1>
</div>
<hr>

|**跳轉連結**|
|:--:|
|[Body章節](Html_Body.md)|

<hr>

### 網頁架構
```html
<!DOCTYPE html> [宣告文檔類型]
<html lang="zh-tw">
    <head>
        <meta [原數據]>
        <title>網頁標題</title>
        <link [外部CSS文件和字體文件]>
        <script [外部JS文件]></script>
        <base [指定網頁中相對路徑的基礎URL]>
        <style [css樣式設置]>
        <noscript [如果瀏覽器不支援JavaScript或JavaScript已禁用，則將顯示其中的內容]>
    </head>

    <body>
        [網頁顯示主體]
    </body>
</html>
```

<hr>

### meta 標籤常用設置
+ **詳細說明連結**
+ [爬蟲規範說明](replenish/爬蟲規範說明.md)
+ [Google 處理方式](replenish/Google內容處理.md)
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        [網頁顯示的編碼]
        <meta charset="utf-8">

        [會顯示在搜尋引擎的描述]
        <meta name="description" content="對於網站的描述">

        [網頁搜尋的關鍵字]
        <meta name="keywords" content="關鍵字1,關鍵字2">

        [瀏覽器顯示模式 RWD]
        <!--第一參數為寬度自動符合用戶端設備的寬度 , 第二參數為縮放的倍率)-->
        <meta name="viewport" content="width=device-width,initial-scale=1.0">

        [網頁自動刷新 , 刷新後網址]
        <meta http-equiv="refresh" content="秒數;URL=目標網址">

        [網頁的作者]
        <meta name="author" content="作者名稱">

        [爬蟲規範]
        <meta name="robots" content="index, follow">

        [Google 搜尋引擎的內容處理方式]
        <meta name="google" content="nositelinkssearchbox">
    </head>
</html>
```
<hr>

### link 標籤
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        <link href="favicon.ico" rel="icon" type="image/icon" sizes="16x16">
    </head>
</html>
```
+ **href** `指定要引入的資源的 URL / 文件路徑`
+ **rel** `指定引用的類型。常用值包括 stylesheet（引入 CSS 樣式表）、icon（引入圖標）等`
+ **type** `指定資源類型。例如 text/css 和 image/icon`
+ **sizes** `指定圖標尺寸。media: 指定樣式表適用的媒體類型`

**rel 參數**
+ `icon` : 指定一個圖標文件。
+ `tag` : 指定文檔的標籤或關鍵字。
+ `author` : 指定文檔作者的網址。
+ `search` : 指定一個搜索引擎的網址。
+ `stylesheet` : 指定一個外部CSS文件。
+ `prev , next` : 指定文檔的上一頁和下一頁鏈接。
+ `alternate` : 指定一個鏈接的替代版本，如舊版本或不同語言版本。

**type 參數**
+ `text/css` : css 類型文件
+ `application/json` : json 類型文件
+ `text/javascript` : javascript 類型文件
+ `application/rss+xml` : 證書類型文件

**sizes 參數**
+ `32x32` : 單位為像素
+ `16x16` : 單位為像素

<hr>

### base 標籤
+ **只能設置一個位置 , 作為根目錄**
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        <base href="[基礎 URL/檔案路徑]">
    </head>
</html>
```

<hr>

### script 標籤
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        [導入外部腳本]
        <!--defer 預設的導入 , 會等到載入完畢 , 才運行之後代碼-->
        <script type="text/javascript" src="script.js" defer></script>
        <!--async 異步載入 , 以非阻塞方式運行-->
        <script type="text/javascript" src="script.js" async></script>

        [直接撰寫](通常腳本引用會在 DOM 的最下方)
        <script>
            function showMessage() {
                alert("Hello, World!");
            }
        </script>
    </head>
</html>
```

<hr>

### noscript 標籤
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        <script>
            // 未成功載入或失效的js
        </script>

        <noscript>
            <p>看到這行代表你的script腳本載入失敗</p>
        </noscript>
    </head>
</html>
```

<hr>