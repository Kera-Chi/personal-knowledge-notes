### 計算每個值的出現次數

如何從一個 SQL 資料表中，計算儲存在指定列中每個相同值的出現次數。

```sql
SELECT column_name, COUNT(*) AS count
FROM table_name
GROUP BY column_name;
```

- **COUNT(*)：** 用來計算表中指定列中相同值的個別出現次數。
- **AS count：** 給予 COUNT(*) 的結果一個 count 的名稱。
- **GROUP BY：** 按照不同的值分組，且 COUNT(*) 會分別對每個組別的出現計算行數。