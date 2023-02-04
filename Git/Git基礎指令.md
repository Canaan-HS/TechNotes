<div align=center>

# **Git指令筆記** #

</div>

***
> **Git是什麼?**

<pre>
Git是一個版本控製系統,幫助您跟蹤代碼更改,可用於協作或編寫代碼
</pre>

> **Git的下載點**

```
https://www.git-scm.com/
```

> **Git的基本指令**

## **小技巧: Git任何查詢紀錄的指令 最後只要按下Q就可以退出**

---

<span align=center>

# **基本查詢**

</span>

**`查詢Git版本:`**
```
git --version
```
**`查詢基礎用選項:`**
```
git -help
```
**`查詢所有可用選項:`**
```
git help --all
```

---

<span align=center>

# **日誌與配置查詢**

</span>

**`查詢提交日誌:`**
```
git log --oneline
```

**`查看配置狀態:`**
```
git remote -v
```
**`查看配置檔案內容:`**
```
git config --list
```
**`查看暫存區內容:`**
```
git ls-files
```
**`查看修改前後差異:`**
```
git diff

(比較兩版本之間差異)
git diff <版本號> <版本號>
或
git diff HEAD~ HEAD

(加上數字,比對當前與,提交前5次的版本)
git diff HEAD~5 HEAD

(再加上文件名,就只會顯示該文件差異)
git diff HEAD~5 HEAD test.txt
```
**`查看修改狀態:`**
```
git status --short
```
<pre>
？？ - 未跟蹤的文件
A - 添加的文件
M - 修改文件
D - 刪除的文件
</pre>

**`查詢分支:`**
```
git branch
git branch -a
```

---

<span align=center>

# **基本配置**

</span>

**`克隆項目:`**
```
git clone [項目網址].git
```
**`配置設定 (GitHub ID & Mail):`**

`--global是全局變數 , --system個別系統配置`
```
git config --global user.name "YourName"
git config --global user.email "Your@Mail"
```

`設置認證輔助工具`
```
git config --global credential.helper <參數>

參數:
store：將認證信息以明文形式存儲在磁盤上。
cache：在一段時間內（預設為 15 分鐘）將認證信息存儲在內存中。
osxkeychain：使用 macOS 鑰匙串來存儲認證信息。
wincred：使用 Windows 認證存儲來存儲認證信息。
gnome-keyring：使用 GNOME Keyring 來存儲認證信息。
libsecret：使用 freedesktop.org Secret Service API 來存儲認證信息
```

`查看配置訊息`
```
git config --global --list
```

**`Git初始化 (在要連結的資料夾內,使用CMD輸入):`**
```
git init
```
**`專案建立:`**
```
git commit -m "你要創建的專案名稱"
```
**`添加存儲庫:`**
```
git remote add origin [新的存儲庫地址].git
```
**`創建分支:`**
```
git branch "分支名"
```
**`合併分支(在主分支下輸入,要合併的分支):`**
```
git merge "要合併的分支"
```
**`狀態添加 (擇一使用):`**
```
git add 任意檔案

git add --all

git add -A

git add .
```
**`提交所有變更:`**
```
git commit -a -m "註解"
```
**`憑證配置:`**
```
git config --global credential.helper "store --file=~/.git-credentials"
```
**`上傳提交:`**
```
git push
```

---

<span align=center>

# **刪除與重設**

</span>

**`刪除配置:`**
```
git remote rm origin
```
**`刪除文件:`**
```
(需另外更新暫存區)
除了刪除本地文件後 , 再進行提交 , 也能使用以下命令

(可直接刪除 , 暫存區和本地的檔案 , 在進行提交)
git rm test.txt
```
**`切換分支:`**
```
git checkout "分支名"
```
**`刪除分支:`**
```
git branch -d "要刪除的分支"
```
**`重製版本:`**
```
(保留本地 與 暫存區 文件)
git reset --soft "版本號"

(刪除本地 與 暫存區 文件)
git reset --hard "版本號"

(保留本地 刪除 暫存區 文件)
git reset --mixed "版本號"
```
<pre>
使用方法:

查詢版本號(前面的數字就是) : git log --oneline 
查完按<Kbd>Q</Kbd>退出

git reset --soft 重製版本

然後使用上面的指令
</pre>

<hr>