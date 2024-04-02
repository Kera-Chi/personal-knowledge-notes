### 管理工作目錄 & 分支

分享幾個在 Git 中常用的命令，用於處理文件和分支的變更。

- **git checkout -- file_name：**
  將特定文件恢復到上一次 commit 時的狀態，用於取消對單個文件的修改。

- **git reset --hard：**
  將工作目錄中的修改全部丟棄，回到上一次 commit 的狀態。這是一個不可逆操作！

- **git reset --soft：**
  將 HEAD 指向的 commit 往前移動一個 commit，並保留工作目錄和暫存區的修改。這樣就可以重新 commit 這些修改。

- **git reset --commit_id：**
  將 HEAD 指向的 commit 往前移動到指定的 commit。

- **git stash push -m"your_message"：**
  將目前的修改暫時存儲起來。

- **git stash apply：**
  應用最近一次 stash 的修改，但不刪除 stash 紀錄。可以保留 stash 列表中的記錄。

- **git stash pop：**
  應用最近一次 stash 的修改，同時刪除 stash 紀錄。基本上相當於執行 `git stash apply` 後再執行 `git stash drop`。