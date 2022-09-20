# Írj egy függvényt ami összeszoroz minden számot egy iterálható inputban (list, tuple).


```python
def szoroz(iterable):
    prod = 1
    for i in iterable:
        prod = prod*i
    return prod
```


```python
szoroz([2, 4, 3])
```




    24



# Írj egy függvényt ami kiszámolja egy pozitív egész szám faktoriálisát.


```python
def faktorialis(szam):
    return szoroz(range(1,szam+1))
```


```python
faktorialis(5)
```




    120



# Írj egy függvényt aminek az inputja egy list, az outputja egy list amely az eredeti list egyedi elemeit tartalmazza.


```python
def egyedi(lista):
    return list(set(lista))
```


```python
egyedi([1, 1, 2, 'alma', 4, 3, 2, 'alma', 'narancs'])
```




    ['alma', 1, 2, 3, 4, 'narancs']



# Írj egy függvényt ami eldönti egy pozitív egész számról, hogy prím-e.


```python
def prim(szam):
    for i in range(2,szam):
        if szam%i==0:
            prime = False
            break
    else:
        prime = True
    return prime
```


```python
prim(4)
```




    False




```python
prim(7)
```




    True



# Írj egy függvényt aminek az inputja egy list, az outputja pedig a list numerikus elemeit tartalmazza (kiszűri a szöveges és boolean elemeket).


```python
def numerikus(lista):
    retval = []
    for x in lista:
        if type(x)==int or type(x)==float:
            retval.append(x)
        else:
            continue
    return retval
```


```python
numerikus([2, 3.33, 'alma', True])
```




    [2, 3.33]



# Írj egy függvényt aminek az inputja egy egész szám, az outputja pedig egy list ami az adott szám prímtényezős felbontását tartalmazza.


```python
def felbont(szam):
    maradek = szam
    primtenyezok=[]
    while maradek!=1:
        for i in range(2, maradek+1):
            if maradek%i==0:
                primtenyezok.append(i)
                maradek=maradek//i
                break
    return primtenyezok
```


```python
felbont(4163126)
```




    [2, 11, 11, 17203]




```python
prim(17203)
```




    True


