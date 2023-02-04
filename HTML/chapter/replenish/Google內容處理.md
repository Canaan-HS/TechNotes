# Google 搜索引擎處理方式 <a href="../Html_Head.md"><img src="../img/back.png" width="30"></a>
---
```html
<!DOCTYPE html>
<html lang="zh-tw">
    <head>
        [告知 Google 搜尋引擎網頁內容可以被抓取和索引](name 參數)
        <meta name="googlebot" content="">

        [指定網頁為新聞網頁，告知 Google News 可以抓取並索引](name 參數)
        <meta name="googlebot-news" content="">

        [指定網頁為圖片網頁，告知 Google Images 可以抓取並索引](name 參數)
        <meta name="googlebot-image" content="">
        
        [告知 Google 搜尋引擎網頁內容可以被索引](content 參數)
        <meta name="googlebot" content="index">

        [告知 Google 搜尋引擎不要索引網頁內容](content 參數)
        <meta name="googlebot" content="noindex">

        [告知 Google 搜尋引擎可以跟隨網頁上的鏈接](content 參數)
        <meta name="googlebot" content="follow">

        [告知 Google 搜尋引擎不要跟隨網頁上的鏈接](content 參數)
        <meta name="googlebot" content="nofollow">
    </head>
</html>
```
---