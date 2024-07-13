## 【不專業筆記分享 33】解決 SLF4J 警告訊息

有時候雖然 `pom.xml` 中沒有直接依賴 SLF4J，但還會看到警告訊息！這可能是因為其他的依賴間接引入了 SLF4J。（圖一）  
這些警告訊息雖然不會影響運作，但每次運行時看到它們真的很~~ 討厭（強迫症發作）🤦🏻‍♀️

### 解決步驟：

1. 用 Maven 的 `dependency:tree` 指令來檢查項目的依賴關係：
   ```bash
   mvn dependency:tree
   ```

2. 發現兇手！在 `sqlite-jdbc` 中間接包含了 SLF4J 啊

3. 根據 SLF4J 的官方文檔，添加其中一個 SLF4J 的依賴就可以解決！

4. 記得檢查加入的 SLF4J 版本要和子依賴的一樣！
    - 仔細看第二張圖，我原本加的版本是 `2.0.12`，但子依賴是 `1.7.36`，所以錯誤訊息還是一直跑出來Q_Q

### 錯誤訊息文字版：
```
SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder".
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See http://www.slf4j.org/codes.html for further details.
```

### 依賴資訊文字版：
```
[INFO] +- org.projectlombok:lombok:jar:1.18.32:provided
[INFO] +- org.xerial:sqlite-jdbc:jar:3.45.2.0:compile
[INFO] |  \- org.slf4j:slf4j-api:jar:1.7.36:compile
[INFO] \- org.slf4j:slf4j-nop:jar:2.0.12:compile
```
