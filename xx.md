## 签名方法

---

### 1. 申请安全凭证

在第一次使用 API 之前，请前往 [API 密钥页面](https://ai.haimacloud.com:10090/api_key) 申请安全凭证。
安全凭证包括 SecretId 和 SecretKey：

- SecretId 用于标识 API 调用者身份
- SecretKey 用于加密签名字符串和服务器端验证签名字符串的密钥。
- **用户必须严格保管安全凭证，避免泄露。**

申请安全凭证的具体步骤如下：

1. 登录 [AI 能力中台](https://ai.haimacloud.com:10090/login)。
2. 前往 [API 密钥管理](https://ai.haimacloud.com:10090/api_key)页面
3. 在 [API 密钥](https://ai.haimacloud.com:10090/api_key)页面，单击【新建密钥】即可以创建一对 SecretId/SecretKey。

注意：每个账号最多可以拥有三对 SecretId/SecretKey。

### 2. 生成签名串

有了安全凭证 SecretId 和 SecretKey 后，就可以生成签名串了。以下是使用签名方法 v1 生成签名串的详细过程：

假设用户的 SecretId 和 SecretKey 分别是：

- SecretId: AKIDz8krbsJ5yKBZQpn74WFkmLPx3**\*\*\***

- SecretKey: Gu5t9xGARNpq86cd98joQYCN3**\*\*\***

以语音合成请求为例，当用户调用这一接口时，其请求参数可能如下:

**公共参数**

| 参数名称  | 中文       | 参数值                                  |
| --------- | ---------- | --------------------------------------- |
| SecretId  | 密钥 ID    | AKIDz8krbsJ5yKBZQpn74WFkmLPx3**\*\*\*** |
| Timestamp | 当前时间戳 | 1691159877000                           |
| AppId     | APPID      | 1252422369                              |

**接口参数**

| 参数名称 | 中文 | 参数值           |
| -------- | ---- | ---------------- |
| question | 问题 | 你有哪些小伙伴？ |
| role_id  | 3    | 角色 ID          |

#### 2.1. 拼接请求字符串

此步骤生成请求字符串。
接口参数合转为 json 字符串。最终生成的请求字符串为:

POST 请求

```json
{ "question": "你有哪些小伙伴？", "role_id": 3 }
```

GET 请求

```
question=你有哪些小伙伴？&role_id=3
```

#### 2.2. 拼接签名原文字符串

此步骤生成签名原文字符串。

签名原文字符串由以下几个参数构成:

- SecretKey: Gu5t9xGARNpq86cd98joQYCN3**\*\*\*** 。
- SecretId: AKIDz8krbsJ5yKBZQpn74WFkmLPx3**\*\*\***。
- Timestamp: 当前时间戳。
- AppId: APPID。
- 请求路径: /ai/nlp/stream 。
- 请求字符串: 即上一步生成的请求字符串。

**GET 请求**

签名原文串的拼接规则为：SecretKey + | + Timestamp + | + AppId + | + SecretId + | + 请求路径 + ?args= + 请求字符串。

**POST 请求**

签名原文串的拼接规则为：SecretKey + | + Timestamp + | + AppId + | + SecretId + | + 请求路径 + ?body= + 请求字符串。

示例的拼接结果为：

```json

Gu5t9xGARNpq86cd98joQYCN3*******|1691159877000|1252422369|AKIDz8krbsJ5yKBZQpn74WFkmLPx3*******|/ai/nlp/stream?body={"question":"你有哪些小伙伴？","role_id":3}
```

#### 2.3. 生成签名串

此步骤生成签名串。

使用 MD5 算法对上一步中获得的签名原文字符串进行 MD5 即可获得最终的签名串。

具体代码如下，以 PYTHON 语言为例：

```python
src_str = 'Gu5t9xGARNpq86cd98joQYCN3*******|1691159877000|1252422369|AKIDz8krbsJ5yKBZQpn74WFkmLPx3*******|/ai/nlp/stream?body={"question":"你有哪些小伙伴？","role_id":3}';
md5_hash = hashlib.md5()
md5_hash.update(src_str.encode("utf-8"))
sign_str = md5_hash.hexdigest()
print(sign_str);
```

最终得到的签名串为：

9f786e2b56ae18fa0963aa0a74a63bb5

### 3.签名演示

#### Python

```python
    import hashlib
    def calculate_md5(self, string):
        md5_hash = hashlib.md5()
        md5_hash.update(string.encode("utf-8"))
        return md5_hash.hexdigest()

    def __main__():
        secret_key = 'xxxxx'
        app_id = 'xxxxx'
        timestamp = int(time.time()) * 1000
        secret_id = 'xxxxxx'

        self.logger.log_with_entry_line("info", "计算签名")

        url = '/ai/nlp'

        sign_str = secret_key + "|" + int(timestamp) + "|" + app_id + "|" + secret_id + "|" + url

        body = {
            'question':'你有哪些小伙伴？',
            'role_id':3
        }

        sign_str += "?body=" + json.dumps(
            body, ensure_ascii=False, separators=(",", ":")
        )
        print(calculate_md5(sign_str))
```

#### JavaScrip

```javascript
// 首先需要引入crypto-js.js
var url = '/ai/tts';
var appId = 'xxxx';
var secretKey = 'xxxx';
var secretId = 'xxxxx';
var timestamp = Date.now();
sign_str = secretKey + '|' + timestamp + '|' + appId + '|' + secretId + '|' + url;
var body = {
  role_id: Number(role_id),
  text: ttsText
};
sign_str += '?body=' + JSON.stringify(body);
sign = CryptoJS.MD5(sign_str).toString();
console.log(sign);
```
