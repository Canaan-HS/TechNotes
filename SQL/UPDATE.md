## UPDATE 是更新/變更 原有資料的數值

### UPDATE 在使用時如果省略了 WHERE 將會變更所有資料 !

**更新顧客資料**
>將顧客資料中 第一筆資料,顧客姓名,城市 作變更

```
UPDATE Customers
SET ContactName='TW', City='Kaohsiung'
WHERE CustomerID=1;
```

**同時變更多筆資料**
>將顧客姓名為 Juan 的 國家都改成 TW

```
UPDATE Customers
SET ContactName='Juan'
WHERE Country='TW';
```