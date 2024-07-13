## 【不專業筆記分享 46】Branch 命名規則

每間公司的 Branch 的命名規則雖然會因為不同的工作流程而不一樣，但內部大多數都還是會有一定的邏輯~

整理了一些常見的命名規則分享：

### 1. 開發新功能
用於開發新功能的分支。
```plaintext
feature/功能名稱
```
範例：
```plaintext
feature/user-login
```

### 2. 修復 Bug
用於修復 Bug 的分支。
```plaintext
bugfix/問題描述
```
範例：
```plaintext
bugfix/fix-login-error
```

### 3. 準備 release 的版本
用於準備發佈的代碼。
```plaintext
release/版本號
```
範例：
```plaintext
release/Sprint200
release/1.0.0
```

### 4. 用於緊急修復
用於緊急修復的分支。
```plaintext
hotfix/問題描述
```
範例：
```plaintext
hotfix/fix-critical-bug
```

### 5. 測試用
用於測試的分支。
```plaintext
test/測試名稱
```
範例：
```plaintext
test/integration-tests
```

### 6. 更改配置
用於更改配置的分支。
```plaintext
config/配置描述
```
範例：
```plaintext
config/update-database-setup
```