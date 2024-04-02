### Java - 使用 StringBuilder

在Java中，`StringBuilder` 用於處理字串，它可以在創建字串後對其進行修改，而不需要每次都重新創建一個新的字串。這種特性對於需要頻繁修改字串的情況很適合，因為直接修改字串比創建新的字串要更有效率。

舉例來說，當你需要在一個已有的字串後面添加內容，或者刪除特定範圍的字元時，`StringBuilder` 就是一個很棒的選擇。

### 範例

#### 1. 追加字元
使用 `append` 方法在字串的末尾添加不同資料類型的內容。

#### 2. 刪除字元
使用 `delete` 方法刪除指定範圍內的字元，包含起始位置但不包含結束位置。

```java
StringBuilder sb = new StringBuilder("Hello world!");
sb.append(" !!!!!"); // 在末尾添加內容
sb.delete(6, 11); // 刪除 'world' 
System.out.println(sb.toString()); // 輸出：Hello !!!!!
```

在上面的範例中，建了一個 `StringBuilder`，並進行了追加和刪除操作。最後輸出的字串為 `"Hello !!!!!"`，原來的 `"world"` 被刪除了。

### 補充 - delete 的索引範圍
- 起始索引（start）是包含在刪除範圍內的。
- 結束索引（end）是不包含在刪除範圍內的，所以結束位置的元素不會被刪除。

例如，如果有一個`StringBuilder`對象的內容是"Hello World"，我們想要從索引2（包含）開始刪除到索引5（不包含）的範圍，那麼使用`delete`方法是：

```java
StringBuilder sb = new StringBuilder("Hello World");
sb.delete(2, 5);
```

這會刪除從索引2（包含，對應到字母"l"）到索引5（不包含，對應到空格" "）之間的字元，最後內容將會變成"Hel World"。