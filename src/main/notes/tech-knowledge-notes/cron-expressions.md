## 【不專業筆記分享 41】Cron 時間表達式

Jira Automation 的自動化排程透過 Cron 來管理的，但不同的系統對於支援 Cron 的表達式好像都有點不同，以下分享一些自己的筆記和常用的表達~

### 一般的表達式：`* * * * * *`
1. Minute（0 - 59）
2. Hour（0 - 23）
3. Day of the Month（1 - 31）
4. Month（1 - 12）
5. Day of the Week（0 - 7）（星期天可以是 0 或 7）
6. Year（Optional）

### Jira 的表達式：`* * * * * * *`（支援秒）
1. Second（0 - 59）
2. Minute（0 - 59）
3. Hour（0 - 23）
4. Day of the Month（1 - 31）
5. Month（1 - 12 or JAN-DEC）
6. Day of the Week（1 - 7 or SUN-SAT）
7. Year（Optional）

### 常見範例

1. **每天早上 8:00：**
    - Original：`0 8 * * *`
    - Jira：`0 0 8 * * ?`

2. **每個月的 1 號和 15 號凌晨 2:30：**
    - Original：`30 2 1,15 * *`
    - Jira：`0 30 2 1,15 * ?`

3. **每週一至週五的上午 9:00：**
    - Original：`0 9 * * 1-5`
    - Jira：`0 0 9 ? * MON-FRI`

4. **每小時的第 15 分鐘：**
    - Original：`15 * * * *`
    - Jira：`0 15 * * * ?`

5. **每隔 10 分鐘一次：**
    - Original：`*/10 * * * *`
    - Jira：`0 */10 * * * ?`

### 參考資料來源
[Jira Document](https://l.threads.net/?u=https%3A%2F%2Fconfluence.atlassian.com%2Fservicemanagementserver0422%2Fconstructing-cron-expressions-for-a-filter-subscription-1142233522.html&e=AT0tTZdW3MLAKpajQMORJxtOI6iLPe0ZMyEbpzMr5vGcXpsWUkfvbQq5JEUyRPicQOXdvG4yVUHEeA9xNt6lfMOgRqE5ZMC-xCQHMaa8_mdcWuoaygTlHWw95RP0Z9huGjLO7cRk34vP)
