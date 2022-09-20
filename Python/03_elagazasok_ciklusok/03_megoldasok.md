# Számítsd ki az első száz szám reciprokösszegét.


```python
osszeg = 0
for i in range(100):
    osszeg = osszeg + 1/(i+1)
osszeg
```




    5.187377517639621




```python
sum([1/(i+1) for i in range(100)])
```




    5.187377517639621




```python
reciprokok = []
for i in range(100):
    reciprokok.append(1/(i+1))
sum(reciprokok)
```




    5.187377517639621



# Határozd meg 5 százalékos éves kamatláb mellett az első 10 év diszkontfaktorát. Emlékeztetőül df = 1/(1+r)^t


```python
diszkontfaktorok = []
for t in range(10):
    diszkontfaktorok.append(1/pow(1.05,t+1))
diszkontfaktorok
```




    [0.9523809523809523,
     0.9070294784580498,
     0.863837598531476,
     0.8227024747918819,
     0.7835261664684589,
     0.7462153966366274,
     0.7106813301301214,
     0.676839362028687,
     0.6446089162177971,
     0.6139132535407591]




```python
[1/1.05**(t+1) for t in range(10)]
```




    [0.9523809523809523,
     0.9070294784580498,
     0.863837598531476,
     0.8227024747918819,
     0.7835261664684589,
     0.7462153966366274,
     0.7106813301301214,
     0.676839362028687,
     0.6446089162177971,
     0.6139132535407591]



# Ellenőrizd, hogy van-e 305900 és 329112 között olyan szám, ami osztható 23523-al.


```python
for i in range(305900,329113):
    if i%23523==0:
        print('{} osztható 23523-al')
else:
    print('egyik szám sem osztható 23523-al ebben a tartományban')
```

    egyik szám sem osztható 23523-al ebben a tartományban


# Határozd meg a hetes számrendszerben 24650165-ként kifejezett szám értékét tízes számrendszerben. Segítség: Próbáld ki, hogy mit kapsz ha egy stringet list-té transzformálsz.


```python
list("24650165")
```




    ['2', '4', '6', '5', '0', '1', '6', '5']




```python
szamjegyek = list("24650165")
szamjegyek.reverse()
osszeg = 0
tizedeshely = 0
for i in szamjegyek:
    osszeg = osszeg + int(i)*7**tizedeshely
    tizedeshely = tizedeshely + 1
osszeg
```




    2230625




```python
sum([int(list("24650165")[-i-1])*7**i for i in range(len(list("24650165")))])
```




    2230625



# Találd meg az első 20 prímszámot


```python
primek = []
vizsgaltszam=2
while len(primek)<20:
    for oszto in range(2, vizsgaltszam):
        if vizsgaltszam % oszto == 0:
            break
    else:
        primek.append(vizsgaltszam)
    vizsgaltszam = vizsgaltszam+1
    
primek
```




    [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71]


