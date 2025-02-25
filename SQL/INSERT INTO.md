## INSERT INTO 是插入一筆新資料 並非對原有資料更改

**直接給予項目和要插入的值**
>設置要插入的項目 顧客姓名,地址,城市,郵政號,國家
>在將要插入的值,依序輸入

```
INSERT INTO Customers (CustomerName, Address, City, PostalCode, Country)
VALUES ('Cardinal','Skagen 21','Stavanger','4006','Norway');
```

**也可以只設置想插入的項目**
> 例如: 我只想插入 名子,城市

```
INSERT INTO Customers (CustomerName, City)
VALUES ('Cardinal', 'Stavanger');
```