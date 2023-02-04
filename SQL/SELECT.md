**想要搜尋所有顧客的資料:**
```
SELECT * FROM Customers;
```

<br><hr><br>


**選擇顧客資料表內 特定的列:**
>例如: 顧客名 和 城市

```
SELECT CustomerName, City FROM Customers;
```

**查看顧客列表中的 國家(包含重複):**
```
SELECT Country FROM Customers;
```

**不重複的國家 (選擇不同的):**
```
SELECT DISTINCT Country FROM Customers;
```

**再查看不同的國家的數量:**
```
SELECT COUNT(DISTINCT Country) FROM Customers;
```

**當某些瀏覽器不支援此語法時可以使用:**
```
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

<br><hr><br>

**使用過濾語WHERE法找出指定的資料:**
>例如: 找到所有資料表內國家為英國的

```
SELECT * FROM Customers
WHERE Country='UK';
```

>或找顧客編號為10的

```
SELECT * FROM Customers
WHERE CustomerID=10;
```

**除了使用 = 找到特定的也能使用:**
```
某數據 > 100的

某數據 >= 100的

某數據 < 100的

某數據 <= 100的

某數據 <> 不等於100的

或

某數據 != 不等於100的

50~100之間: WHERE Price BETWEEN 50 AND 100;

搜索城市首字母為C的: WHERE City LIKE 'c%';

指定多個值: WHERE City IN ('Paris','London');
```

<br><hr><br>


**其他語法運算符:**
```
WHERE condition1 AND condition2 AND condition3 ...;

WHERE condition1 OR condition2 OR condition3 ...;

WHERE NOT condition;
```

**找尋空值或非空值(無法使用運算符):**
>例如: 我要找顧客中 沒有聯絡人 和 地址的

```
SELECT CustomerName, ContactName, Address FROM Customers
WHERE Address IS NULL;
```

>查找不是空的

```
SELECT CustomerName, ContactName, Address FROM Customers
WHERE Address IS NOT NULL;
```

**從"客戶"中選擇國家為"德國"且城市為"柏林"的所有字段：**
```
SELECT * FROM Customers
WHERE Country='Germany' and city='Berlin';
```

**從"客戶"中選擇國家為"德國"或為"柏林"的所有字段：**
```
SELECT * FROM Customers
WHERE Country='Germany' and Country='Berlin';
```

**從"客戶"中選擇國家不是"德國"的所有字段：**
```
SELECT * FROM Customers
WHERE NOT Country='Germany';
```
<br><hr><br>

**LIKE運算符:**
>找到顧客姓名為a開頭的

```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';
```

>名子不以a開頭的顧客

```
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'a%';
```

>a開頭且 字串長度最少為3

```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a__%';
```

>找到顧客姓名為a結尾的

```
SELECT * FROM Customers
WHERE CustomerName LIKE '%a';
```

>找到顧客姓名中包含a的

```
SELECT * FROM Customers
WHERE CustomerName LIKE '%a%';
```

>找到顧客姓名中第二個字是r

```
SELECT * FROM Customers
WHERE CustomerName LIKE '_r%';
```
>名子為a開頭o結尾的顧客

```
SELECT * FROM Customers
WHERE ContactName LIKE 'a%o';
```

<br><hr><br>

**使用 ORDER BY 升序 和 DESC 降序 對要搜尋的關鍵字排序:**
>例如: 對聯絡人姓名進行升序排列(由A~Z)

```
SELECT * FROM Customers
ORDER BY ContactName;
```

>要反過來排序就使用 DESC

```
SELECT * FROM Customers
ORDER BY ContactName DESC;
```

>按照 "國家" 和 "顧客名" 進行排序
>(如某些顧客有相同的國家 會依據顧客名牌序)

```
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```

>改成 國家升序 顧客名降序

```
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

<br><hr><br>

**搜尋前5筆資料:**

```
SELECT TOP 5 * FROM Customers;
```

>同樣的效果

```
SELECT * FROM Customers LIMIT 5;
```
>Oracle 的等效語法

```
SELECT * FROM Customers
FETCH FIRST 5 ROWS ONLY;
```

**搜尋百分比的資料:**
> 前30%資料(1~28)

```
SELECT TOP 30 PERCENT * FROM Customers;
```
>Oracle 的等效語法

```
SELECT * FROM Customers
FETCH FIRST 30 PERCENT ROWS ONLY;
```

**加上 WHERE 進行篩選:**
> 國家為德國的前3筆資料

```
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
```
>MySQL 的等效語法

```
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
```
> Oracle 的等效語法

```
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
```
<br><hr><br>

**MIN() 和 MAX() 函數:**

>找出 定價Price 中最低價 並將資料名取為 SmallestPrice 列出

```
SELECT MIN(Price) AS SmallestPrice FROM Products;
```
>找出 定價Price 中最高價 並將資料名取為 LargestPrice 列出

```
SELECT MAX(Price) AS LargestPrice FROM Products;
```
>如果未使用 AS ... 去指定名稱
>假設是找最低價產品就會以 MIN(Price) 最為顯示的項目名稱

<br><hr><br>

**使用數學函數 COUNT()、AVG()、SUM():**
>查找產品數量(不包含 NULL值)

```
SELECT COUNT(ProductID) FROM Products;
```

>查找產品平均價格(不包含 NULL值項目)

```
SELECT AVG(Price) FROM Products;
```

>查找所有產品的總價(不包含 NULL值)

```
SELECT SUM(Price) FROM Products;
```

<br><hr><br>



