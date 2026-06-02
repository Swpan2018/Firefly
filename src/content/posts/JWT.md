---
title: jwt
published: 2026-06-02
---
![[Pasted image 20260603000010.png]]



# 设置签名为none,更改用户权限角色或者更改用户名
这个适用于后端未对签名进行校验,所以我们可以任意篡改jwt token中的内容



<!-- 这是一张图片，ocr 内容为：REQUEST RESPONSE IN                                 三 RAW HEX ONESCAN MARKLNFO RENDER HEX PRETTY RAW PRETTY POST /WEBGOAT/JWT/VOTINGS HTTP/1.1 HTTP/1.1 200 23 HOST:192.168.0.70:8080 CONTENT-TYPE:APPLICATION/JSON 7345 DATE:SAT. 27 SEP 2025 05:40:53 GMT CONTENT-LENGTH:0 3457890123456 X-REQUESTED-WITH:XMLHTTPREQUEST KEEP-ALIVE:TIMEOUT-60 USER-AGENT: MOZILLA/5.O (WINDOWS NT 10.0; WIN64: X64) APPLELTEBKIT/537 36 (RHTML. LIKE GECKO) CONNECTION:KEEP-AL IVE CONTENT-LENGTH: 227 CHROME/140.0.0.0 SAFARI/537.36 ACCEPT:*/* 1 CONTENT-TYPE:APPLICATION/X-WWW-FORM-URLENCODED: CHARSET-UTF-8 LESSONCOMPLETED":FALSE. ORIGIN:HTTP://192.168.0.70:8080 REFERER:HTTP://192.168.0.70:8080/WEBGOAT/START.MVC?USERNAME-TEST123 "FEEDBACK":"ONLY AN ADMIN USER CAN RESET THE VOTES", MUL "FEEDBACKARGS:NULL. ACCEPT-ENCODING:GZIP,DEFLATE,BR ACCEPT-LANGUAGE:ZH-CN.ZH:Q-0.9.EN-US:Q-0.8.EN:Q-0.7 "OUTPUT":NULL. COOKIE:ACCESS_TOKEN OUTPUTARGS":NULL, "ASSIGNMENT":"JWTVOTESENDPOINT". 2HMVF7 FF3BK3HSOYV3K4PLIKDS1OOCCIQHYGYHBOKG-MOGTIPKEVRV1XPVAQTLHA; JSESSIONID- ATTEMPTWASMADE":TRUE 95D39FC73FAFB1BA5525C115DD28AC86 X-FORWARDED-FOR:127.0.0.1 忆151 X-ORIGINATING-IP:127.0.0.1 X-REMOTE-IP:127.0.0.1 X-REMOTE-ADDR:127.0.0.1 X-REAL-IP:127.0.0.1 18 X-FORWARDED:127.0.0.1 X-CLUSTER-CLIENT-IP:127.0.0.1 FORWARDED-FOR:127.0. 0.1 FORWARDED:127.0.0.1 TRUE-CLIENT-IP:127.0.1 CLIENT-IP:127.0.1 24  ALI-CDN-REAL-IP:127.0.0.1 -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758952297098-8b99736c-aa84-4113-9b9b-36ecb55cf83a.png)

<!-- 这是一张图片，ocr 内容为：CLAIMS TABLE COPY JSON JWT COPY CLEAR VALID JWT "ALG"HS512" INVALID SIGNATURE EYUHBGCIOIJIUZUXMIJ9.EYJPYXQIOIE3NTK4MT DECODED PAYLOAD U2NDMSIMFKBWLUIIOIZMFSC2UILCJLC2VYIIOIV G9TINO.SFPCRSOLVEWBUWAS9NOAI2HMVF7 FF3B K3HSOYV3K4PIIKDSLOOCCLQMYGYHBQKG- CLAIMS TABLE JSON COPY MOGT1PKEVRVLXPVAQTLHA "IAT": 1759815643 FALSE ADMIN "USER":"TOM" JWT SIGNATURE VERIFICATION(OPTIONAL) ENTER THE SECRET USED TO SIGN THE JWT BELOW: SECRET COPY CLEAR FAILED SIGNATURE VERIFICATION A-STRING-SECRET-AT-LEAST-256-BITS-LONG -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758952286131-da2077c8-e439-402a-8b23-0a4533dcf1e9.png)

现在我们将签名改为none,admin改为true

<!-- 这是一张图片，ocr 内容为：FILL IN THE FIELDS BELOW TO GENERATE A SIGNED JWT. GENERATE EXAMPLE JSON WEB TOKEN HEADER CLEAR COPY THIS IS AN UNSECURED JWT AS DEFINED BY VALID HEADER SECTION 6 OF RFC 7519. "ALA": EYTHBGCIOIJUB25LINO.EYJPYXQIOJE3NTK4MTU 'NONE 2NDMSIMFKBWLUIJOIDHJ1ZSISINVZZXIIOIJUB2 OIFQ PAYLOAD CLEAR VALID PAYLOAD 1759815643 "ADMIN": "TRUE", "UGER"TOM"" REPORT ISSUE SHARE FEEDBACK -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758952403307-d50d5aee-e4a6-4dd1-a634-93b0d656214b.png)

成功绕过

<!-- 这是一张图片，ocr 内容为：RESPONSE REQUEST MARKLNFO ONESCAN HEX PRETTY RENDER HEX RAW PRETTY POST /WEBGOAT/JWT/VOTINGS HTTP/1.1 HTTP/1.1 200 HOST:192.168.0.70:8080 1234567890116456 CONTENT-TYPE:APPLICATION/JSON CONTENT-LENGTH:0 DATE: SAT, 27 SEP 2025 05:41:59 GMT KEEP-ALIVE:TIMEOUT60 X-REQUESTED-WITH:XMLHTTPREQUEST USER-AGENT: MOZILLA/5.O (WINDOWS NT 10.0; WIN64:X64) APPLELLEBKIT/537.36 (RHTML, LIKE GECKO) CONNECTION:KEEP-ALIVE CONTENT-LENGTH:  252 CHROME/140.0.0.0 SAFARI/537.36 ACCEPT:*/* PE:APPLICATION/X-WWW-FORM-URLENCODED; CHARSET-UTF-8 CONTENT-TYPE: OR IGIN:HTTP://192.168.0.70:8080 LESSONCOMPLETED":TRUE, HAVE SUCCESSFULLY COMPLETED THE ASSIGRMENT. " REFERER:HTTP://192.168.0.70:8080/WEBGOAT/START.MVC?USERNAME-TEST123 FEEDBACK":CONGRATULATIONS.YOU HA ACCEPT-ENCODING:GZIP,DEFLATE,BR FEEDBACKARGS"NULL, 1 ACCENT-LANOIIATE:ZH-ON ZHIO-O 9 EN-US.OE0 8 0-0 7 "OUTPUTARGS":NULL. ASSIGNMENT":"JWTVOTESENDPOINT". X-FORWARDED-FOR:127.0.0.1 ATTEMPTWASMADE":TRUE X-ORIGINATING-IP:127.0.0.1 X-REMOTE-IP:127.0.0.1 X-REMOTE-ADDR:127.0.0.1 X-REAL-IP:127.0.0.1 X-FORWARDED:127.0.0.1 X-CLUSTER-CLIENT-IP:127.0.0.1 FORWARDED-FOR:127.0.0.1 -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758952432933-aa1bad37-95ad-4a7a-a315-b704a7738575.png)



总结：如果后端未对签名进行校验，那我们可以任意更改token的内容进行绕过

         如果后端依赖于token的alg来设置签名，那我们我们可以更改token的alg为none，然后可以任意篡改token信息

        <font style="color:rgb(51, 51, 51);">需要注意的一件事是在末尾添加</font>`<font style="color:rgb(199, 37, 78);background-color:rgb(249, 242, 244);">一个 .</font>`<font style="color:rgb(51, 51, 51);">，否则令牌无效。</font>

<font style="color:rgb(51, 51, 51);"></font>

<font style="color:rgb(44, 44, 54);">你提到的两个 Java JWT 解析方法：</font>

<font style="color:rgb(44, 44, 54);background-color:rgba(204, 238, 255, 0.267);">Jwts.parser().setSigningKey(JWT_PASSWORD).parseClaimsJws(accessToken);</font>

<font style="color:rgb(44, 44, 54);">和</font><font style="color:rgb(108, 108, 108);background-color:rgb(226, 242, 255);"></font>

<font style="color:rgb(44, 44, 54);background-color:rgba(204, 238, 255, 0.267);">Jwts.parser().setSigningKey(JWT_PASSWORD).parse(accessToken);</font>

<font style="color:rgb(44, 44, 54);">虽然看起来相似，但它们在 </font>**<font style="color:rgb(17, 24, 39);">安全性、用途和行为</font>**<font style="color:rgb(44, 44, 54);"> 上有重要区别。下面我们详细对比分析。</font>

## <font style="color:rgb(44, 44, 54);">🔍</font><font style="color:rgb(44, 44, 54);"> 一、核心区别</font>
| | | | |
| --- | --- | --- | --- |
| `<font style="color:rgb(97, 92, 237);background-color:rgb(239, 238, 255);">parseClaimsJws()</font>` | <font style="color:rgb(29, 29, 32);">只解析并验证</font>**<font style="color:rgb(17, 24, 39);">带签名的 JWT（JWS）</font>**<font style="color:rgb(29, 29, 32);">，且 payload 是 Claims 类型</font> | <font style="color:rgb(29, 29, 32);">✅</font><font style="color:rgb(29, 29, 32);"> 高</font> | <font style="color:rgb(29, 29, 32);">✅</font><font style="color:rgb(29, 29, 32);"> 强制验证签名</font> |
| `<font style="color:rgb(97, 92, 237);background-color:rgb(239, 238, 255);">parse()</font>` | <font style="color:rgb(29, 29, 32);">解析任意 JWT（包括无签名的</font>`<font style="color:rgb(97, 92, 237);background-color:rgb(239, 238, 255);">none</font>`<font style="color:rgb(29, 29, 32);">算法）,也包括alg中设置了签名算法，但是token中没有签名体的方式</font> | <font style="color:rgb(29, 29, 32);">⚠️</font><font style="color:rgb(29, 29, 32);"> 低</font> | <font style="color:rgb(29, 29, 32);">❌</font><font style="color:rgb(29, 29, 32);"> 不强制验证算法或签名</font> |






# jwt密钥爆破


```plain
eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJXZWJHb2F0IFRva2VuIEJ1aWxkZXIiLCJhdWQiOiJ3ZWJnb2F0Lm9yZyIsImlhdCI6MTc1ODk1MTYzMCwiZXhwIjoxNzU4OTUxNjkwLCJzdWIiOiJ0b21Ad2ViZ29hdC5vcmciLCJ1c2VybmFtZSI6IlRvbSIsIkVtYWlsIjoidG9tQHdlYmdvYXQub3JnIiwiUm9sZSI6WyJNYW5hZ2VyIiwiUHJvamVjdCBBZG1pbmlzdHJhdG9yIl19.E9anU8Qf9pydaRM7EQWTQN_E2eenHxzpUP0Euk-6C_g
```

适用jwt_tool工具爆破

python jwt_tool.py -C jwt_token -d dit.txt

```plain
python jwt_tool.py -C eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJXZWJHb2F0IFRva2VuIEJ1aWxkZXIiLCJhdWQiOiJ3ZWJnb2F0Lm9yZyIsImlhdCI6MTc1ODk1MTYzMCwiZXhwIjoxNzU4OTUxNjkwLCJzdWIiOiJ0b21Ad2ViZ29hdC5vcmciLCJ1c2VybmFtZSI6IlRvbSIsIkVtYWlsIjoidG9tQHdlYmdvYXQub3JnIiwiUm9sZSI6WyJNYW5hZ2VyIiwiUHJvamVjdCBBZG1pbmlzdHJhdG9yIl19.E9anU8Qf9pydaRM7EQWTQN_E2eenHxzpUP0Euk-6C_g -d F:\information_security\tools\jwt_tool-master\jwt_tool-master\jwtdict.txt
```

<!-- 这是一张图片，ocr 内容为：LLUGITIONDLYUINGLIDITIONGLIDITIONDLYULITIONGLIDITIONLLYUNDITIONLLYUNDITIONDLY DITIONDITIONDITIONLLUNI FORMATION.SECURITY\TOOLS\JWT.TOOL-MASTER\JWT.TOOL-MASTER\JWEDICT.TXT JWTTOOL OTICARPI VERSION 2.3.0 C:\USERS\ADMINISTRATOR/JWT_TOOL/JWTCONF.INI ORIGINAL JWT: [+] IS THE CORRECT KEY! U CAN TAMPER/FUZZ THE TOKEN CONTENTS (-T/-I) AND SIGN IT USI YOU CA IT USING: 43 JWT_TOOL.PY [OPTIONS HERE] -S HS256 -P "BUSINESS" PYTHON3 JWT. -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758956226494-c7d654b1-b4b9-4208-9a7f-81438253380f.png)

这里使用获得的密钥进行签名，当然不要忘记更改exp的值，也就是时间戳，这里是过期时间

[https://tool.lu/timestamp/](https://tool.lu/timestamp/)

<!-- 这是一张图片，ocr 内容为：FILL IN THE FIELDS BELOW TO GENERATE A SIGNED JWT. GENERATE EXAMPLE HEADER JSON WEB TOKEN COPY CLEAR VALID HEADER EYUHBGCIOIJIUZI1NIJ9.EYJPC3MIOIJXZWJHB2 FOIFRVA2VUIEJLAWXKZXIILCJHDWQIOIJ3ZWJNB 2FOLM9YZYISIMLHDCI6MTCLODK1MTYZMCWIZXHW "ALG": "HS256" IJOXNZU40TU2MZU0LCJZDWIIOIJ0B21AD2VIZ29 子 HDC5VCMCILCJLC2VYBMFTZSI6ILDLYKDVYXQILC JFBWFPBCI6INRVBUB3ZWJNB2FOLM9VZYISILJVB GUIOLSITWFUYWDLCIISILBYB2PLY3QGQWRTAW5P C3RYYXRVCIJDFQ.GTDW7ELFLTTDXNIVZKRNEDT5 PAYLOAD CLEAR EOFKIX-OVR9KP3JRUOC VALID PAYLOAD "ISS": "WEBGOAT TOKEN BUILDER", 'AUD": "WEBGOAT.ORG'', 1758951630, IAT": "EXP": 1758956354, "SUB":"TOM@WEBGOAT.ORG", "USERNAME": "WEBGOAT", "EMAIL"; "TOM@WEBGOAT.ORG", "ROLE": [ "MANAGER", "PROJECT ADMINISTRATOR" JWT SIGN CLEAR VALID SECRET BUSINESS ENCODING FORMAT UTF-8 SHARE FEEDBACK | REPORT ISSUE -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1758956253240-f68f412c-9c6b-4124-adaa-9a8f196f0270.png)当然可以！在现代的认证和授权系统中（尤其是使用 OAuth 2.0 协议时），**Access Token** 和 **Refresh Token** 是两个非常重要的概念。它们共同协作，既能保证系统的安全性，又能提升用户体验。下面是对它们的详细介绍：

---



# 访问令牌与刷新令牌
### 🔐 1. Access Token（访问令牌）
+ **作用**：用于访问受保护的资源（如 API 接口）。
+ **特点**：
    - 通常是短期有效的（例如 15 分钟到 1 小时）。
    - 每次请求需要携带该 token（通常放在 HTTP 请求头 `Authorization: Bearer <token>` 中）。
    - 一旦过期，服务器将拒绝请求。
+ **安全性**：
    - 因为有效期短，即使被泄露，影响也有限。
    - 建议通过 HTTPS 传输，避免中间人攻击。

✅ 类比：就像一张临时门票，只能进一次游乐场，而且几小时后就失效。

---

### ♻️ 2. Refresh Token（刷新令牌）
+ **作用**：用于获取新的 Access Token，而无需用户重新登录。
+ **特点**：
    - 通常是长期有效的（例如几天、几周甚至几个月）。
    - 不用于直接访问资源，只用于向认证服务器申请新的 Access Token。
    - 只在客户端与认证服务器之间使用（不会发给资源服务器）。
+ **安全性**：
    - 更加敏感，必须安全存储（如加密保存在服务端或安全的本地存储中）。
    - 有些系统支持“一次性刷新令牌”（one-time use），用完即失效，防止重放攻击。
    - 如果泄露，可能被用来持续获取新的 access token，因此需严格保护。

✅ 类比：像一张会员卡，可以在门票（access token）过期后，去柜台换一张新门票，而不用重新买票。

---

### 🔄 工作流程示例（OAuth 2.0）
1. 用户登录成功后，认证服务器返回：
    - 一个 **Access Token**
    - 一个 **Refresh Token**
2. 客户端使用 Access Token 访问 API：

```http
GET /api/user
Authorization: Bearer <access_token>
```

3. 当 Access Token 过期后，客户端使用 Refresh Token 向认证服务器请求新 token：

```http
POST /token
grant_type=refresh_token
refresh_token=<refresh_token>
client_id=...
```

4. 认证服务器验证 Refresh Token 合法后，返回新的 Access Token（有时也返回新的 Refresh Token）。
5. 客户端使用新 Access Token 继续访问资源。

---

### ✅ 最佳实践
| 实践 | 说明 |
| --- | --- |
| 短期 Access Token | 减少泄露风险 |
| 安全存储 Refresh Token | 避免明文存储，建议服务端存储 |
| Refresh Token 可撤销 | 支持用户登出时使其失效 |
| 使用 HTTPS | 所有 token 传输都应加密 |
| 绑定客户端信息 | 如 IP、设备指纹，增强安全性 |


---

### ❗ 注意事项
+ 不要将 Refresh Token 发送给前端（如浏览器）明文存储（除非使用安全机制如 HttpOnly Cookie）。
+ 移动 App 或 SPA 应结合安全策略（如 PKCE）防止 token 被劫持。
+ 某些场景下可不使用 Refresh Token（如使用 JWT + 无状态会话），但需权衡安全与便利。

---

总结一句话：

> **Access Token 用来“干活”，Refresh Token 用来“续命”。**
>

如果你有具体的应用场景（比如 Web、App、API 设计），我可以给出更具体的建议 😊





# 获取刷新令牌，生成有效的访问临牌（获取的是其他用户的）


在日志文件中，发现tom用户泄露的jwt token

<!-- 这是一张图片，ocr 内容为：194.201.170.15 [20/JAN/ 201 BJN7Q HTTP/1.1 401 242 FTANF 195.201.170. [28/J 28:01 GET +010 /TVT/REFREAH/WOVE TOCHECKOUT HT -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1759297941321-7cd189d5-014e-40ad-ae25-82e9766cdec8.png)

然后在/WebGoat/JWT/refresh/checkout 使用这个token进行访问的时候

告知时间已过期

<!-- 这是一张图片，ocr 内容为：HTTP/1.1 200 POST /WEBGOAT/JWT/REFRESH/CHECKOUT HTTP/1.1 CONTENT-TYPE:APPL ICATION/JSON HOST:192.168.11:8080 CONTENT-LENGTH:0 DATE:WED.01 0CT 2025 05:22:54 GMT AUTHORIZATION:BEARER KEEP-ALIVE:TIMEOUT-60 5 CONNECTION:KEEP-ALIVE 103 9 CONTENT-LENGTH:393 0. DCOUG9ZAKYOH2SEAVIKCDBYVFULAC9DAJRVSQOQQYI9IAD4OUAMKCCHFBUBFNZEBNZEBNF9TLEFXHZLU4YRKA-BJM70 X-REQUESTED-WITH:XMLHTTPREQUEST 7890117 I USER-AGENT: MOZILLA/5.O (VINDOWS NT 10.0; WIN64:  X64) APPLEWIT/537 36 (KHTIL,  LIKE GECKO LESSONCOMPLETED":FALSE, CHROME/140.0.0.0 SAFARI/537.36 'FEEDBACK"SORRY THE SOLUTION IS NOT CORRECT, PLEASE TRY AGAIN.", ACCOPT:*/* CONTENT-TYPE:APPLICATION/X-WWW-FORM-URLENCODED; CHARSET-UTF-8 FEODBACKARGS":NULL. ORIGIN:HTTP://192.168.11:8080 OUTPUT: ,JHT EXPIRED AT 2018-05-13121;23:31Z QURRANT TIME; 2025-10-01T13:ZZ:54Z, A DIFFERENCE OF 23307836351 REFERER:HTTP://192.168.1.11:8080/WEBGOAT/START.MVE?USERNAME-TEST123 8 MILLISECONDS. ALLONED CLOCK SKEW: O MILLISECONDS," ACCEPT-ENCODING:GZIP.DEFLATE,BR 信假11 ACCEPT-LANGUAGE:ZH-CN,ZH:Q-0.9,EN-US:Q-0.8,EN:Q-0.7 OUTPUTARGS :NUL L. COOKIE: JSESSIONID 60D55D4117875AFC9DOA6B7EC3D1FD13 ASSIGNMENT":"JWTREFRESHENDPOINT". ATTEMPTWASMADE :TRUE GONNEGTJ.N:.KEER,ALIXE -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1759298066043-516bd518-067a-48bc-a165-03fb4ca58dd9.png)

然后我们在登录Jerry的时候，发现，其实会返回给一个刷新令牌，

<!-- 这是一张图片，ocr 内容为：REQUEST RESPONSE 兰 S PRETTY ONESCAN MARKINFO PRETTY HTTP/1.1 200 POST /WEBGOAT/JWT/REFRESH/LOGIN HTTP/1.1 HOST:192.168.1.11:8080 CONTENT-TYPE:APPLICATION/JSON 23456789 CONTENT-LENGTH:46 DATE:WED.01 0OT 2025 05:45:43 GMT X-REQUESTED-WITH:XMLHTTPREQUEST KEEP-ALIVE:TIMEOUT-60 USER-AGENT: MOZILLA/5.0 (WINDOWS NT 10.0;  WIN64; X64) APPLEIEIKIT/537.36 (KHTIML, LIKE GECKO) CONNECTION:KEEP-ALIVE CHROME/140.0.0.0 SAFARI/537.36 CONTENT-LENGTH:223 ACCEPT:*/* CONTENT-TYPE:APPL ICATION/JSON ORIGIN:HTTP://192.168.11:8080 ACCESS_TOKEN": "EYJHBGCIOIJLUZUXMIJ9.8YJHZ61OBILGLIMZHBHNIIIWIDXNICIL6IKOLCNJ5IND.7-ZX2LORUUBOLEVI9HEYVADI7KKAOGL REFERER:HTTP://192.168.11:8080/WEBGOAT/START.MVC?USERNAME-TEST123 JERG1DDA6Z5_H-SREXH1MYHOLXRYAPNOP7NFFONP3ROW1Y5QIOA", ACCEPT-ENCODING:GZIP,DEFLATE,BR ACCEPT-LANGUAGE:ZH-CN,ZH;Q-0.9,EN-US:Q-0.8,EN:Q-0.7 10 REFRESH_TOKEN":"LMRBKPXMZCNOBXWRYOLA" COOKIE:JSESSIONID-60D55D4117875AFC9DOA6B7EC3D1FD13 11] GONNEATJ.ON..KEER:ALIXE USER:JERRY "PASSWORD":"BM5NHSKXCXZKKRY4" -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1759298123176-02444b80-d76f-4683-b917-1855f045b84a.png)

我们访问/WebGoat/JWT/refresh/newToken这个接口（这个是从源码中拿的，黑盒没找到，我觉得应该要fuzz吧）

使用tom过期的token和我们获取的刷新令牌

<!-- 这是一张图片，ocr 内容为：RESPONSE SI PRATTY ONESCAN SELECTION T/WEBGOAT/JWT/REFRESH/NEWTOKEN HTTP/1.1 HOST:192.168.11.11:8080 CONTENT-TYPE:APPLICATION/JSON TOM已过期的 DATE:WOD.01 0OT 2025 05:47:27 GNT CONTENT-LENGTH:50 KEEP-ALIVE:TIMEOUT-60 AUTHOR IZATION:BEARERER 56789 CONNECTION:KEEP-ALIVE 0.DCOAG9ZOKYDH25ECVIKODBYVFUL409DAJRVEQOQQQQQVI9IAD4QUGRKCCHFBUBFIZEBNF9TLEFXHZLU4YRKA-BJU70 CONTENT-LENGTH:220 TOM用户的新JWTTOKEN X-RECUESTED-WITH:XMLTNRGAUESST 6 USOR-AGONT: MOZILLA/5.0 (WINDOWS'NT 10.0; WIN64: X64) APPLELILLELKIT/537.36 (KHTIL, LIKE GOCKO) "ACCESS TOKEN*: CHROME/140.0.0.0 SAFARI/537.36 "EYJH6GC10/JIUZUIDXNIJ9.6YUHZ0106I16LAZHTHRUN[[[WIDXNIEIIRY65J9.  4YUADQUVAL7ICS-HSEBCRALHG UBYDTKRXI ACCEPT:*/* IF7GD.17V7WCTURWERUNW9U IAH8F4VNG31XAFVWYUFMAT OSGE". CONTENT-TYPE:APPLICATION/JSON REFRESH_TOKEN":OWASHDEUNSZSKAGVWJKB 0RIGIN:HTTP://192.168.1.11:8080 11 REFERER:HTTP://192.168.11.11:8080/WEBGOAT/START.MVC?USERNAME-TEST123 TES 19199 ACCEPT-ENCODING:GZIP,DEFLATE,BR ACCEPT-LANGUAGE:ZH-CN,ZH:Q-0.9,EN-US:Q-0.8.EN:Q-0.7 X-REQUE COOKIE:JSESSIONID 60D55D4117875AFC9DOA6B7EC3D1FD13 GONNEGTJANI.KEER:ALIXE 'REFRESH_TOKEN :'LMRBKPXMZCNOBXWRYOLA REQUEST ATT REQUEST QUE REQUEST COO ROQUOST HES -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1759298268852-67059a7f-0965-4647-b1f5-a0c6b2ba88a7.png)



用这个新的访问令牌去访问，成功

<!-- 这是一张图片，ocr 内容为：IN                                      三 PRETTY HEX RENDER RAW POST/WEBGOAT/JWT/REFRESH/CHECKOUT]HTTP/1.1 1 HTTP/1.1 200 2 CONTENT-TYPE:APPLICATION/JSON HOST:192.168.11:11:8080 134 3 DATE:WED,01 0CT 2025 05:48:36 GMT CONTENT-LENGTH:0 4 KEEP-ALIVE:TIMEOUT60 AUTHORIZATION:BEARER LEYJHBGAIJLUZUXNIJP.0YJHZALODOUVELMZHBHNIL IVIDXNLCILBLIRRBSJ9.3GYLODOUVEL7IC5 HBEFORALHS UBYDTERIGH CONNECTION:KEEP-AL IVE ZVZWCTUR WBBUNW9UJAB8F4VNG31XAEVWYUEMATOSGG CONTENT-LENGTH: 254 5X-REQUESTED-WITH:XMLHTTPREQUEST I USER-AGENT: MOZILLA/5.0 (WINDOWS NT 10.0; WIN64; X64) APPLELLELLEBKIT/537.36 (KHTML, LIKE GECKO) LESSONCOMPLETED":TRUE. CHROME/140.0.0.0 SAFARI/537.36 "FEEDBACK?: CONGRATULATIONS. YOU HAVE SUCCESSFULLY COMPLETED THE ASSIGRMENT." ACCEPT:*/* -WWW-FORM-UR LENCODED:CHARSET-UTF-8 'FEEDBACKARGS":NULL, CONTENT-TYPE:APPLICATION/X-WWW-FO ORIGIN:HTTP://192.168.11:8080 "OUTPUT":NULL, REFERER:HTTP://192.168.11.11:8080/WEB6OAT/START.MVC?USERNAME-TEST123 "OUTPUTARGS":NULL. "ASSIGNMENT":"JWTREFRESHENDPOINT". ACCEPT-ENCODING:GZIP,DEFLATE,BR ACCEPT-LANGUAGE:ZH-CN,ZH:Q-0.9,EN-US:Q-0.8,EN:Q-0.7 "ATTEMPTWASMADE":TRUE COOKIE:JSESSIONID-60D55D4117875AFC9DOA6B7EC3D1FD13 SONNEATJ.GO:.KGOR:ALIXE -->
![](https://cdn.nlark.com/yuque/0/2025/png/40434544/1759298311061-ab1928da-98c0-43d3-82c7-9364cf82173e.png)





在 JWT（JSON Web Token）中，`kid` 是一个非常重要的字段，全称是：

> 🔑 **Key ID（密钥标识符）**
>

它的作用是：**帮助接收方快速找到用于验证 JWT 签名的正确公钥。**

---

# 前置：什么是kid？
## ✅ 一、`kid` 的全称与位置
+ **全称**：`key ID`（密钥 ID）
+ **类型**：字符串
+ **出现位置**：
    - 在 JWT 的 **头部（JOSE Header）** 中
    - 不在 Payload 里

### 示例 JWT 头部（Base64 解码后）：
```json
{
  "alg": "RS256",
  "typ": "JWT",
  "kid": "abc123def456"
}
```

👉 这个 `kid` 告诉你：“这个 token 是用 ID 为 `abc123def456` 的密钥签的名”。

---

## 🎯 二、为什么需要 `kid`？
想象一下这个场景：

> 你的系统信任多个公钥（比如轮换过的旧密钥、多个服务提供者），但你收到一个 JWT，怎么知道该用哪个公钥来验证签名？
>

✅ 答案就是：看 `kid`！

### 工作流程：
```plain
收到 JWT
   ↓
解析头部 → 提取 kid = "abc123def456"
   ↓
查找本地或远程的 JWKS（公钥集合）
   ↓
找到对应的公钥：{"kid": "abc123def456", "n": "...", "e": "AQAB"}
   ↓
使用该公钥验证签名
```

---

## 🧩 三、`kid` 和 JWKS 的关系
JWKS（JSON Web Key Set）是一个公开的 JSON 文件，列出所有可用的公钥。

### 示例 `jwks.json`：
```json
{
  "keys": [
    {
      "kid": "abc123def456",
      "kty": "RSA",
      "alg": "RS256",
      "use": "sig",
      "n": "0vx7...",
      "e": "AQAB"
    },
    {
      "kid": "xyz789uvw012",
      "kty": "RSA",
      "alg": "RS256",
      "use": "sig",
      "n": "sflk...",
      "e": "AQAB"
    }
  ]
}
```

当你看到 JWT 的 `kid: abc123def456`，你就从这个列表中选第一个公钥来验证。

---

## ✅ 四、`kid` 的典型应用场景
| 场景 | 说明 |
| --- | --- |
| 🔁 密钥轮换（Key Rotation） | AWS Cognito、Auth0 每隔一段时间换一次密钥，不同 token 使用不同 `kid` |
| 🌐 多租户系统 | 每个租户有自己的密钥对，用 `kid` 区分 |
| 🔐 第三方登录 | Google、Apple 登录返回的 JWT 都带 `kid`，用于匹配其公钥 |
| 🛡 安全审计 | 记录哪个密钥签发了哪个 token，便于追踪 |


---

## ⚠️ 五、常见问题与最佳实践
| 问题/建议 | 说明 |
| --- | --- |
| ❌ 不要忽略 `kid` | 否则无法正确选择公钥，可能导致验证失败或安全漏洞 |
| ✅ 必须校验 `kid` 存在于 JWKS 中 | 防止伪造 header |
| ✅ 支持多个 `kid` | 系统应能处理新旧密钥共存 |
| 🔒 不要用 `kid` 传递敏感信息 | 它是公开的，可能被日志记录 |
| 🔄 密钥轮换时保留旧 `kid` 一段时间 | 让旧 token 能正常过期 |


---

## ✅ 六、实际例子（AWS Cognito）
当你使用 AWS Cognito 登录，返回的 ID Token 头部可能是：

```json
{
  "kid": "1234567890abcdef1234567890abcdef12345678",
  "alg": "RS256"
}
```

然后你的后端会去：

```plain
https://cognito-idp.us-east-1.amazonaws.com/{user-pool-id}/.well-known/jwks.json
```

查找是否有匹配 `kid` 的公钥，如果有，就用它验证签名。

---

## ✅ 七、总结
| 项目 | 内容 |
| --- | --- |
| 名称 | `kid`（Key ID） |
| 位置 | JWT 的头部（Header） |
| 作用 | 标识“这个 token 是用哪把密钥签名的” |
| 是否必需 | ❌ 不强制，但在多密钥系统中强烈建议使用 |
| 安全性 | 是公有信息，不保密，但必须正确验证 |


---

🔐 **一句话记住**：

> `kid` 就像一把钥匙上的编号标签 ——  
“别试所有锁，直接拿编号 `abc123` 的钥匙来开就行。”
>

---





