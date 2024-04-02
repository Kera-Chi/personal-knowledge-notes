### 刪除已同步但不需要的.history目錄

有時候在GitHub上不小心把不需要的`.history`目錄也push上去了，這時候想要同步刪除local和remote上的`.history`目錄，可以按照以下步驟進行：

1. 切換到你的專案目錄：
   ```bash
   cd your-project-path
   ```

2. 強制刪除`.history`目錄及其底下的所有子目錄和文件（請小心使用）：
   ```bash
   rm -rf .history
   ```

3. 開啟或新建一個名為`.gitignore`的文件。

4. 將`.history/`這一行加入到`.gitignore`文件中，這樣Git就會忽略這個目錄及其內容：
   ```
   .history/
   ```

5. 將變更加入暫存區：
   ```bash
   git add .
   ```

6. 提交變更：
   ```bash
   git commit -m "your-commit-message"
   ```

7. 推送變更到遠端分支：
   ```bash
   git push origin your-branch-name
   ```

這樣就完成了同步刪除不需要的`.history`目錄的操作了!

---

#### 特殊情境：push 了才發現忘記加入 .gitignore 的檔案

**情境**：
某些檔案在 push 到 remote 後，才發現忘記加到 `.gitignore` 中，但在加入 `.gitignore` 之後，發現 remote 還是有這些檔案，沒有被移除掉!!

**原因**： 即使 `.gitignore` 被更新，remote 的 tracking 並不會自動移除這些檔案。

**解決辦法**：只好手動把它移除
1. `git rm -r --cached "the_file_name_you_wanna_remove"`
2. `git add .`
3. `git commit -m"your_commit_message"`
4. `git push origin "branch_name"`