### Commit 命令整理

分享兩種可以幫助整理 git commit 的命令。

#### 方法一：建立乾淨的新 Branch

1. 建立一個全新的、乾淨的 branch，可以將紀錄合併為單一個新的 commit。
    ```bash
    git checkout --orphan new_branch
    git add .
    git commit -m "Initial commit on new branch"
    git branch -D original_branch
    git branch -m original_branch
    git push origin main --force
    ```

#### 方法二：合併多個 Commits 為一個新的 Commit

1. 合併多個 commits 為一個新的 commit，會保留第一個 commit，並把後續所有 commits 合併為第二個 commit，所以最少會有兩個 commits。
    ```bash
    git rev-list --count HEAD
    git log --reverse
    git reset --soft xxxxxxx
    git commit -m "New commit"
    git push origin main --force
    ```