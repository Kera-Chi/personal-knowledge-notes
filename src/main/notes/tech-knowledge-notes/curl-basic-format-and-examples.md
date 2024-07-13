## 【不專業筆記分享 42】curl 基本格式和範例

### 基本格式：
```bash
curl [options] [URL]
```

### 常用選項：
- `-X`：指定 HTTP 方法（如 GET, POST, PUT, DELETE）
- `-H`：設置 HTTP 的 headers
- `-d`：設置請求數據（POST 請求）
- `-o`：將 response 輸出到文件

### 範例

#### GET 範例：
```bash
curl -X GET "example.com/api/resource" \
-H "Authorization: Bearer api_token"
```

#### POST 範例：
```bash
curl -X POST "example.com/api/resource" \
-H "Content-Type: application/json" \
-H "Authorization: Bearer api_token" \
-d '{"key1":"value1", "key2":"value2"}'
```

#### GET 輸出 response 到文件：
```bash
curl -X GET "example.com/api/resource" -o response.txt
```

#### POST 輸出 response 到文件：
```bash
curl -X POST "example.com/api/resource" \
-H "Content-Type: application/json" \
-H "Authorization: Bearer api_token" \
-d '{"key1":"value1", "key2":"value2"}' \
-o response.json
```

### Note:
'\\' 是用來換行的，前面不需要特別空一格（但習慣上會留一個），只需要確保反斜線後面緊跟著換行符就可以了！
