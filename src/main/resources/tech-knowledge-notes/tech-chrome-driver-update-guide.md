### ChromeDriver 更新指南

整理了更新 ChromeDriver 環境的步驟，以應對當 Chrome 瀏覽器和 ChromeDriver 版本不相符時出現的問題。

若在運行 UI 測試時遭遇以下問題：
```
Could not start a new session. Response code 500. Message: session not created: This version of ChromeDriver only supports Chrome version XXX
```
這表示 Chrome 瀏覽器和 ChromeDriver 版本不相容。

**解決步驟：**
1. 確認當前 ChromeDriver 版本：`chromedriver --version`
2. 前往 [Google Chrome Labs](https://googlechromelabs.github.io/) 下載正確版本（Apple M2 需下載 mac-arm64 版本）。
3. 切換至 ChromeDriver 下載目錄。
4. 賦予執行權限：`chmod +x chromedriver`
5. 確認 ChromeDriver 的安裝路徑：`which chromedriver`（例如 `/opt/homebrew/bin/chromedriver`）。
6. 將下載的檔案移到指定路徑：`mv chromedriver /opt/homebrew/bin/chromedriver`。
7. 再次確認版本以確保更新成功：`chromedriver --version`

若在步驟 7 遇到權限問題，可能是由於 MacOS 的安全限制。

**解決方法：**
1. 進入「系統偏好設定」>「安全性與隱私」。
2. 在安全性區塊中找到被封鎖的 chromedriver 訊息。
3. 點擊「仍要允許」。