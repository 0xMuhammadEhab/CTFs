- first get the size of images by :
```
ls -ls  | awk '{ printf "%s\n", $6 " "  $10  }' | cut -d "." -f 1
```
- then this python script will extarct the same size 
```
data ="""38944 0bccb1d1c22e0be8
67613 2e3ce7aac0aaa336
102400 3a973c5833db32dc
36458 4b0cfc10c3d111e1
60592 4d92f7335fe137a5
63941 6ef417e6992f4447
50779 7374cab892a94e76
102400 7e0f1f468037ec6f
103677 7f49a3c13cf59fb7
49158 809c03b6bddcda76
165192 8242612b93ae2929
55169 83521b27baf383a9
12606 980425b4686e12d7
116350 a013214dafe3abad
119581 a87e9fdb4ac26186
474395 ad8c6a6913c98e98
117624 af3eea1d4cf1ab91
300241 b7586c22159b2e1a
148595 bef74b74ebed0387
119747 bff026a57836534d
6302 c62068303f969abf
12550 ca5f33ac4b8ef393
43799 d1dcc744b9cdd5b0
111144 e23e2498d53ece65
16046 e2b3c48de6b49e8b
6288 e46c279f5d1ea743
73478 e9b752c0c77226bb
37145 eafc520456e66909
20090 eddca12518d0cdb6
195139 f660c3f6e3de3fb6
40367 f90fb2945c5de29a
52291 fb80d6ee782552b2"""

list_of_data = data.split("\n")
cha = dict()
for i in list_of_data:
    cha[i.split(" ")[1]] = i.split(" ")[0]


cha2 = cha.copy()
for i in cha:
    del cha2[i]
    for j in cha2:
        if cha[i] == cha2[j]:
            print( cha[i], cha[j])
            print(f"{i}{j}")
```
