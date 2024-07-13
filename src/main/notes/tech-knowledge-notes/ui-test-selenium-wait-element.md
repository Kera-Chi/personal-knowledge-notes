### UI Test - Selenium: 等待元素出現


1. 使用 `isDisplayed` 方法檢查元素是否在 UI 上可見。
2. 如果元素不在當前視窗範圍內，使用 Selenium 的 `scrollIntoView` 滾動至可見範圍。
3. 如果元素需要時間加載，可以用 `WebDriverWait` 搭配 `ExpectedConditions` 來等待元素出現。
4. 盡可能避免使用 `Thread.sleep` 方法去等待固定時間。
5. 選擇一個一定會出現在頁面上，且它載完表示其他元素也差不多都載完的元素當等待條件。要避免自身等待，這樣有時候會錯誤（迴圈等到天荒地老）。
```java
waitVisible(button);
isDisplayed(button);
// 錯誤示範
```
6. 如果元素在頁面中的其他 iframe 中，用 `switchTo().frame()` 切換。
7. 用 `isPresent` 檢查元素是否在 DOM 中，所以即使在 UI 上看不到也可以驗證。

