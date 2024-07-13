## 【不專業筆記分享 44】IDP > Token > Client-Session > Authorization

### 定義：
- **IDP (Identity Provider)** : 驗證身份類別。
- **Token** : 基於 IDP 產生當前相對應的身份憑證（細節）。
- **Client-Session** : 基於 Token 產生當前相對應的臨時身分證。
- **Authorization** : 基於 Token 和 Client-Session 產生當前相對應的身份授權範圍。

### 比喻：如果你要進去一棟大樓....
- **IDP** : 出示證件給櫃檯檢查你是誰。
- **Token** : 櫃檯根據證件，給你一張包含你身份和權限的說明書。
- **Client-Session** : 根據說明書的內容，給你一張臨時識別證，代表你被允許進入大樓。
- **Authorization** : 根據說明書的內容和識別證，決定你可以進入哪些區域和執行哪些操作。

### 特性：
1. **Token & Client-Session** 通常都有一個有效期。
2. **同一個 IDP** 在不同時間可能產生不同的 Token 和 Client-Session。