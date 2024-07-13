## 【不專業筆記分享 43】同步 Repo

我有十足的把握和信心，下次我一定還是會不小心忘記...  
趁還沒忘記趕快筆記一下步驟...

### 同步步驟：

1. 添加上游遠端庫：
    ```bash
    git remote add upstream <organization-repo-url>
    ```

2. 從上游遠端庫抓取更新：
    ```bash
    git fetch upstream
    ```

3. 切換到 `main` 分支：
    ```bash
    git checkout main
    ```

4. 將上游遠端庫的 `master` 分支合併到本地 `main` 分支：
    ```bash
    git merge upstream/master
    ```

5. 將更新推送到自己的遠端庫：
    ```bash
    git push origin main
    ```

下次從第二步驟開始就可以~