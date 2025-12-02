



# wget 与 curl：详细介绍与对比

## 概述

### wget
**wget**（GNU Wget）是一个**文件下载工具**，专注于从网络下载文件，支持递归下载和断点续传。

### curl
**curl**（Client URL）是一个**数据传输工具**，支持多种协议，更注重于与Web服务进行交互和数据传输。

## 核心特性对比

| 特性         | wget             | curl             |
| ------------ | ---------------- | ---------------- |
| **主要用途** | 下载文件         | 传输数据         |
| **设计哲学** | 简单直接的下载   | 强大的协议客户端 |
| **递归下载** | ✅ 内置支持       | ❌ 需要脚本配合   |
| **断点续传** | ✅ 自动支持       | ✅ 需手动指定     |
| **协议支持** | HTTP, HTTPS, FTP | 30+ 种协议       |
| **交互性**   | 较少             | 丰富             |
| **输出默认** | 保存到文件       | 输出到终端       |
| **进度条**   | 简洁             | 详细信息         |

---

## 详细功能介绍

### 1. wget - 下载专家

#### 基本语法
```bash
wget [选项] [URL]
```

#### 常用功能示例

**1. 基本下载**
```bash
# 下载文件
wget https://example.com/file.zip

# 指定保存文件名
wget -O myfile.zip https://example.com/file.zip

# 后台下载
wget -b https://example.com/large-file.iso
```

**2. 递归下载（网站镜像）**
```bash
# 下载整个网站
wget --mirror --convert-links --adjust-extension --page-requisites \
     --no-parent https://example.com/

# 限制递归深度
wget -r -l 2 https://example.com/

# 只下载特定类型文件
wget -r -A "*.pdf" https://example.com/
```

**3. 断点续传**
```bash
# 自动断点续传
wget -c https://example.com/large-file.iso

# 限制下载速度（防止占用所有带宽）
wget --limit-rate=100k https://example.com/file.iso
```

**4. 批量下载**
```bash
# 从文件读取URL列表
wget -i url-list.txt

# 按序列下载
wget https://example.com/images/{1..10}.jpg
```

**5. 认证和代理**
```bash
# HTTP认证
wget --user=username --password=password https://example.com/protected/

# FTP下载
wget ftp://username:password@ftp.example.com/file.zip

# 使用代理
wget --proxy=on --proxy-user=user --proxy-password=pass https://example.com/
```

### 2. curl - 传输专家

#### 基本语法
```bash
curl [选项] [URL]
```

#### 常用功能示例

**1. HTTP 请求**
```bash
# 基本GET请求
curl https://httpbin.org/get

# 发送POST请求
curl -X POST https://httpbin.org/post

# 发送POST数据
curl -X POST -d "name=John&age=30" https://httpbin.org/post
curl -X POST -H "Content-Type: application/json" \
     -d '{"name":"John","age":30}' https://httpbin.org/post
```

**2. 文件传输**
```bash
# 下载文件并保存
curl -o filename.jpg https://example.com/image.jpg

# 上传文件
curl -X POST -F "file=@localfile.zip" https://example.com/upload

# FTP上传下载
curl -u username:password -O ftp://example.com/file.zip
curl -u username:password -T localfile.zip ftp://example.com/
```

**3. 高级HTTP功能**
```bash
# 设置请求头
curl -H "Authorization: Bearer token123" \
     -H "Content-Type: application/json" \
     https://api.example.com/data

# 发送Cookie
curl -b "session=abc123" https://example.com/
curl -b cookies.txt -c cookies.txt https://example.com/login

# 跟随重定向
curl -L https://example.com/redirect

# 查看请求详情
curl -v https://example.com/
curl --trace-ascii debug.txt https://example.com/
```

**4. 认证**
```bash
# 基本认证
curl -u username:password https://example.com/

# OAuth2 Bearer Token
curl -H "Authorization: Bearer YOUR_TOKEN" https://api.example.com/

# API密钥
curl -H "X-API-Key: your-api-key" https://api.example.com/data
```

**5. 测试和调试**
```bash
# 只显示响应头
curl -I https://example.com/

# 显示请求和响应头
curl -i https://example.com/

# 限制速度
curl --limit-rate 100K https://example.com/file.iso

# 设置超时
curl --max-time 10 https://example.com/
```

---

## 实际场景对比

### 场景1：下载单个文件

**wget**（更简单）：
```bash
wget https://example.com/software.tar.gz
# 自动保存到当前目录，显示进度
```

**curl**（需要指定输出）：
```bash
curl -O https://example.com/software.tar.gz
# 或
curl -o software.tar.gz https://example.com/software.tar.gz
```

### 场景2：API 调用

**wget**（基本GET）：
```bash
wget -qO- "https://api.example.com/data?param=value"
```

**curl**（更适合API）：
```bash
# GET请求
curl "https://api.example.com/data?param=value"

# POST请求
curl -X POST -H "Content-Type: application/json" \
     -d '{"key":"value"}' https://api.example.com/data

# 带认证
curl -H "Authorization: Bearer token" https://api.example.com/protected
```

### 场景3：网站镜像

**wget**（理想选择）：
```bash
wget --mirror --page-requisites --convert-links \
     --no-parent https://example.com/
```

**curl**（不支持递归，需要复杂脚本）：
```bash
# curl本身不支持递归下载
# 需要配合其他工具或编写复杂脚本
```

### 场景4：下载文件列表

**wget**：
```bash
wget -i url-list.txt
# 可以轻松从文件读取URL列表
```

**curl**：
```bash
# 需要xargs配合
cat url-list.txt | xargs -n 1 curl -O

# 或使用parallel加速
parallel curl -O ::: $(cat url-list.txt)
```

---

## 功能特性详细对比表

| 功能           | wget       | curl                             | 说明                           |
| -------------- | ---------- | -------------------------------- | ------------------------------ |
| **HTTP方法**   | GET, POST  | GET, POST, PUT, DELETE等所有方法 | curl支持完整的RESTful方法      |
| **HTTP/2**     | ❌ 支持有限 | ✅ 完全支持                       | curl在HTTP/2支持上更好         |
| **WebSocket**  | ❌          | ✅                                | curl支持WebSocket              |
| **代理支持**   | ✅          | ✅                                | 两者都支持HTTP/HTTPS/SOCKS代理 |
| **SSL/TLS**    | ✅          | ✅                                | curl支持更多加密套件           |
| **输出控制**   | 简单       | 丰富                             | curl可以输出到文件、终端或变量 |
| **进度显示**   | 简洁进度条 | 详细进度信息                     | curl可以显示更多传输细节       |
| **重试机制**   | ✅ 自动     | ✅ 可配置                         | wget更自动化                   |
| **Cookie管理** | 基本       | 强大                             | curl可以保存和读取cookie文件   |
| **表单提交**   | 有限       | 完整                             | curl支持multipart/form-data    |
| **压缩传输**   | ✅          | ✅                                | 两者都支持gzip/deflate         |
| **带宽限制**   | ✅          | ✅                                | 都可以限制下载速度             |
| **时间戳保持** | ✅          | ❌                                | wget可以保持服务器文件时间     |
| **IPv6**       | ✅          | ✅                                | 两者都支持                     |

---

## 性能对比

| 方面           | wget                 | curl         | 建议                       |
| -------------- | -------------------- | ------------ | -------------------------- |
| **大文件下载** | 更稳定，断点续传更好 | 同样优秀     | wget更适合长时间下载       |
| **小文件批量** | 优秀，自动处理       | 需要脚本     | wget更简单                 |
| **并发下载**   | 内置有限并发         | 需要外部工具 | 都需要额外工具实现高效并发 |
| **内存使用**   | 较低                 | 中等         | wget更轻量                 |
| **连接复用**   | ❌                    | ✅ Keep-Alive | curl在多次请求时效率更高   |

---

## 实际用例代码示例

### 1. 下载并解压文件

**wget方式**：
```bash
wget https://example.com/data.tar.gz
tar -xzf data.tar.gz
```

**curl方式**：
```bash
curl -L https://example.com/data.tar.gz | tar -xz
# 或
curl -o data.tar.gz https://example.com/data.tar.gz && tar -xzf data.tar.gz
```

### 2. 测试网站可用性

**wget方式**：
```bash
wget --spider --timeout=10 --tries=2 https://example.com/
```

**curl方式**：
```bash
curl -s -o /dev/null -w "%{http_code}" https://example.com/
curl --max-time 10 --retry 2 https://example.com/
```

### 3. 文件上传

**wget**（基本不支持上传）：
```bash
# wget主要设计用于下载
```

**curl**：
```bash
# 上传文件到服务器
curl -F "file=@localfile.txt" https://example.com/upload

# 带进度显示的上传
curl --progress-bar -T largefile.iso ftp://example.com/
```

### 4. 监控网页变化

**wget方式**：
```bash
# 定时检查网站变化
while true; do
    wget -q -O current.html https://example.com/
    if ! diff -q previous.html current.html > /dev/null; then
        echo "网站已更新!"
        cp current.html previous.html
    fi
    sleep 300
done
```

**curl方式**：
```bash
# 获取特定元素
while true; do
    current=$(curl -s https://example.com/ | grep -o '<title>.*</title>')
    if [ "$current" != "$previous" ]; then
        echo "标题已更改: $current"
        previous="$current"
    fi
    sleep 300
done
```

### 5. 自动化脚本示例

**使用wget的下载脚本**：
```bash
#!/bin/bash
# download_script.sh

BASE_URL="https://example.com/files"
OUTPUT_DIR="downloads"

mkdir -p "$OUTPUT_DIR"

# 下载一系列文件
for i in {1..10}; do
    filename="file_${i}.pdf"
    echo "下载: $filename"
    wget -q -c -P "$OUTPUT_DIR" "${BASE_URL}/${filename}"
    
    # 检查文件完整性
    if [ $? -eq 0 ]; then
        echo "✓ $filename 下载成功"
    else
        echo "✗ $filename 下载失败"
    fi
done

echo "所有文件已保存到: $OUTPUT_DIR"
```

**使用curl的API测试脚本**：
```bash
#!/bin/bash
# api_test_script.sh

API_BASE="https://api.example.com"
TOKEN="your_api_token"

# 测试GET请求
echo "测试GET /users..."
response=$(curl -s -H "Authorization: Bearer $TOKEN" "${API_BASE}/users")
echo "响应: $response"

# 测试POST请求
echo -e "\n测试POST /users..."
curl -X POST \
     -H "Authorization: Bearer $TOKEN" \
     -H "Content-Type: application/json" \
     -d '{"name":"John Doe","email":"john@example.com"}' \
     "${API_BASE}/users"

# 测试文件上传
echo -e "\n测试文件上传..."
curl -X POST \
     -H "Authorization: Bearer $TOKEN" \
     -F "file=@test.txt" \
     -F "description=Test file" \
     "${API_BASE}/upload"
```

---

## 选择建议

### 使用 wget 当：

1. **需要下载整个网站**（递归下载）
2. **下载大文件**（自动断点续传）
3. **简单的文件下载任务**
4. **需要保持目录结构**
5. **做网站备份或镜像**

### 使用 curl 当：

1. **与API交互**（RESTful服务）
2. **需要发送复杂HTTP请求**（各种方法、头部）
3. **测试Web服务**
4. **需要支持多种协议**
5. **在脚本中进行复杂的数据传输**

---

## 互补使用

实际工作中，两者经常结合使用：

```bash
# 使用curl获取URL列表，然后用wget下载
curl -s https://api.example.com/files | jq -r '.urls[]' | wget -i -

# 或者反过来
# 使用wget下载，curl处理
wget -qO- https://example.com/api-data | curl -X POST -d @- https://other-api.com/
```

## 总结

- **wget**：像是"下载管理器"，专注于**获取文件**
- **curl**：像是"瑞士军刀"，专注于**数据传输**

两者都是命令行工具的瑰宝，根据不同的需求选择合适的工具，或者结合使用，可以大大提高工作效率。对于系统管理员和开发者来说，熟练掌握这两个工具是必备技能。