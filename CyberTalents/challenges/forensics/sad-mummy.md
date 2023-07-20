- use john to crack the zip password
```
zip2john ~/Downloads/SadMummy.zip > hash
john hash --wordlist=~/Desktop/rockyou.txt
7z x ~/Downloads/SadMummy.zip -pXD -o/tmp
```

- then strings image you will notice some interesting things 
```
strings SadMummy.jpg| grep -v "{K"  | grep "{"
```
or 
```
binwalk -e SadMummy.jpg
cd _SadMummy.jpg.extracted
grep -r '{' | cut -d ":" -f 2 | uniq
```
