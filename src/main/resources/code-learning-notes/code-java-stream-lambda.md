### Java - Stream & Lambda

Java 中 Stream 和 Lambda 的基本介紹及常見用法。

#### Stream簡介

Stream 就像是一個自動化流程，可以將不同的數據結構的數據（List、Set、Array等）放到stream中進行處理。

**程式碼示例：**
```java
List<String> languages = Arrays.asList("java", "ruby", "ruby", "python", "javascript");
List<String> processedLanguages = languages.stream()
    .filter(language -> "ruby".equals(language))
    .map(String::toUpperCase)
    .collect(Collectors.toList());
System.out.println(processedLanguages); // 輸出：[RUBY, RUBY]
```

#### Filter的其他常見用法

1. **字串過濾**
    - `endsWith(String)`
    - `contains(String)`
    - `matches(String)`

   **範例：** `stream.filter(s -> s.endsWith("txt"))`

2. **數值比較：`>`, `<`, `>=`, `<=`**

   **範例：** `stream.filter(x -> x > 10)`

3. **多個判斷條件：`&&`, `||`, `!`**

   **範例：** `stream.filter(x -> x > 10 && x < 20)`

4. **檢查屬性**

   **範例：** `stream.filter(obj -> "value".equals(obj.getProperty()))`