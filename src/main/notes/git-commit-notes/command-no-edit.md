### 修正 Commit

有時候在 commit 完成後才發現自己又做了一些小的修改，但不想再次編輯 commit message 或者創建一個新的 commit 再 squash commit 時...

解決方法如下：

```bash
git add .
git commit --amend --no-edit
```

這樣它就會將新的更改直接添加到上一個 commit 中，而無需再次處理 commit message 的問題。 🎉