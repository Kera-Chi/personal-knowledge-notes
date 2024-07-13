## 【不專業筆記分享 34】SQL：Bulk Update

當需要根據不同條件來對資料庫中的多筆資料進行修改時，這個語法非常有用！

### 語法範例

```sql
UPDATE questions
SET difficulty = 
CASE
    WHEN difficulty = 'easy' THEN 1
    WHEN difficulty = 'medium' THEN 2
    WHEN difficulty = 'hard' THEN 3
    ELSE difficulty
END;
```

### 執行結果
- 所有 `difficulty` 為 `'easy'` 的都會被改成 `1`。
- 所有 `difficulty` 為 `'medium'` 的都會被改成 `2`。
- 所有 `difficulty` 為 `'hard'` 的都會被改成 `3`。
- 如果 `difficulty` 不是上述指定的任何一個值，則該值保持不變。