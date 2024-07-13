## 【不專業筆記分享 45】Maven Surefire

### 常用指令

#### 運行單個測試類
```bash
mvn test -Dtest=JiraIssueControllerTest
```

#### 運行單個測試方法
```bash
mvn test -Dtest=JiraIssueControllerTest#testReceiveIssue
```

#### 運行多個測試類
```bash
mvn test -Dtest=JiraIssueControllerTest,CSVServiceTest
```

#### 運行匹配的測試類
```bash
mvn test -Dtest=*Test
```

#### 運行全部測試
```bash
mvn test
```

#### 運行指定 package 中的所有測試
```bash
mvn test -Dtest=com.tools.qajiraslack.service.**
```

#### 排除指定的測試類
```bash
mvn test -Dtest=CSVServiceTest -DexcludedTests=CSVServiceTest#testGetValueFromCSV_NotFound
```