### 合併更動到主分支

有時候在修復問題時，可能希望將這些更改合併到主分支中。以下是如何在基於開發分支進行修復時將更改合併到主分支的步驟：

1. 切換到修復的分支：`git checkout fixing_branch_name`
2. 使用 `git log` 查看要合併到主分支的提交記錄，並複製要合併的提交哈希值。
3. 切換回主分支並確保它是最新的：`git checkout master`，`git pull origin master`
4. 使用 `git cherry-pick commit_hash` 將修復分支上的特定提交合併到主分支。
5. 使用 `git push origin master` 將更改推送到遠端的主分支。

這樣，修復就可以成功地合併到主分支中了！