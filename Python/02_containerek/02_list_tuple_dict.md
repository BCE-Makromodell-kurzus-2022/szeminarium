# Container objektumok

## List
A list több objektum tárolására használható indexált objektum, melyet szögletes zárójelek között definiálunk.

```python
a = [7, 6.2, 'alma', True]
```


```python
type(a)
```




    list




```python
a
```




    [7, 6.2, 'alma', True]




```python
# Pythonban zero indexing van, az első elem indexe mindig 0
a[0]
```




    7




```python
a[1]
```




    6.2




```python
a[2]
```




    'alma'




```python
a[3]
```




    True




```python
a[4]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    /tmp/ipykernel_9828/3944406842.py in <module>
    ----> 1 a[4]
    

    IndexError: list index out of range



```python
a[-1]
```




    True




```python
a[-2]
```




    'alma'




```python
a[-3]
```




    6.2




```python
a[-4]
```




    7




```python
a[-5]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    /tmp/ipykernel_9828/639495242.py in <module>
    ----> 1 a[-5]
    

    IndexError: list index out of range



```python
# Intervallumok is kiválaszthatók, ekkor a nyitó indexben zárt, a záró indexben nyitott az intervallum
```


```python
a[0:2]
```




    [7, 6.2]




```python
a[0:3]
```




    [7, 6.2, 'alma']




```python
a[2:]
```




    ['alma', True]




```python
a[:3]
```




    [7, 6.2, 'alma']




```python
a[1:2]
```




    [6.2]




```python
# Vegyük észre, hogy intervallum kiválasztásánál, még ha az egy elemű is, lista az output
```


```python
a[2]
```




    'alma'




```python
a[2:3]
```




    ['alma']




```python
# A listának vannak ú.n. methodjai, amikkel műveleteket végezhetünk rajta
```


```python
# Append: Elem hozzáadása a listához
```


```python
a
```




    [7, 6.2, 'alma', True]




```python
a.append(False)
```


```python
a
```




    [7, 6.2, 'alma', True, False]




```python
# A listán azonos elem többször is szerepelhet
```


```python
a.append(5)
```


```python
a.append(5)
```


```python
a.append(5)
```


```python
a
```




    [7, 6.2, 'alma', True, False, 5, 5, 5]




```python
# Count: megszámolja, hogy egy adott elem hányszor szerepel a listán
```


```python
a.count(5)
```




    3




```python
# Remove: Eltávolítja az adott elem első előfordulását a listáról
a.remove(True)
```


```python
a
```




    [7, 6.2, 'alma', False, 5, 5, 5]




```python
a.remove(5)
```


```python
a
```




    [7, 6.2, 'alma', False, 5, 5]




```python
# Pop: Eltávolítja az adott indexű elemet a listáról
```


```python
a.pop(2)
```




    'alma'




```python
a
```




    [7, 6.2, False, 5, 5]




```python
# Reverse: megfordítja a lista elemek sorrendjét
```


```python
a.reverse()
```


```python
a
```




    [5, 5, False, 6.2, 7]




```python
# Sort: sortolja a listát
```


```python
a.sort()
```


```python
a
```




    [False, 5, 5, 6.2, 7]


A lista elemei felülírhatók

```python
a[0] = 'körte'
```


```python
a
```




    ['körte', 5, 5, 6.2, 7]




```python
a[0:2] = [2, 3]
```


```python
a
```




    [2, 3, 5, 6.2, 7]


Még több a list methodokról a Python dokumentációjában: https://docs.python.org/3/tutorial/datastructures.html
## Műveletek list-ekkel


```python
# List hosszának meghatározása
```


```python
len(a)
```




    5




```python
# List elemeinek összege - csak ha összeadhatók a listaelemek
sum(a)
```




    23.2




```python
# Listelemek ismétlése
a*3
```




    [2, 3, 5, 6.2, 7, 2, 3, 5, 6.2, 7, 2, 3, 5, 6.2, 7]




```python
# Szöveges listáknál konkatenálás lehetséges
strlist = ['Ez', 'egy', 'lista', 'szavakkal']
' '.join(strlist)
```




    'Ez egy lista szavakkal'




```python
# Szöveg könnyen listába bontható
```


```python
stringem = "Ez egy mondat, amit szavakra fogok majd bontani"
```


```python
stringem.split()
```




    ['Ez', 'egy', 'mondat,', 'amit', 'szavakra', 'fogok', 'majd', 'bontani']



## Tuple
List-hez hasonló objektum, azonban az elemei nem módosíthatók és nem adható hozzá elem. Zárójelek között definiáljuk.

```python
b = (1, 2, 3, 'alma', True)
```


```python
# Ugyanúgy indexálható
b[0]
```




    1




```python
b[3]
```




    'alma'




```python
b[-4]
```




    2




```python
# Több elem kiválasztásánál egy újabb tuple-t kapunk vissza
b[2:5]
```




    (3, 'alma', True)




```python
b[2:3]
```




    (3,)




```python
# Nem írható felül egy eleme önmagában
b[2] = 3
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_9828/2963503365.py in <module>
          1 # Nem írható felül egy eleme önmagában
    ----> 2 b[2] = 3
    

    TypeError: 'tuple' object does not support item assignment



```python
# A tuple könnyen unpackelhető változókba
```


```python
b
```




    (1, 2, 3, 'alma', True)




```python
b1, b2, b3, b4, b5 = b
```


```python
b1
```




    1




```python
b4
```




    'alma'




```python
# A tuple egy eleme bármilyen objektum lehet, lista is
```


```python
c = (3, "alma", [2, 5, 6])
```


```python
c[2]
```




    [2, 5, 6]




```python
c[2][1]
```




    5




```python
# Ez a listára is igaz
```


```python
d = [2, 4, ["alma", True], ('paprika','narancs')]
```


```python
d[2]
```




    ['alma', True]




```python
d[3]
```




    ('paprika', 'narancs')




```python
d[3][1]
```




    'narancs'




```python
d[2].append("alma")
```


```python
d
```




    [2, 4, ['alma', True, 'alma'], ('paprika', 'narancs')]




```python
# Bár a tuple elemei nem módosíthatók, egyben felülírható az egész tuple
```


```python
b
```




    (1, 2, 3, 'alma', True)




```python
b = 3
```


```python
b
```




    3




```python
b = (2, 4, 6)
```


```python
b
```




    (2, 4, 6)




```python
b = ('alma', 'narancs')
```


```python
b
```




    ('alma', 'narancs')




```python
# Ugyanez igaz akkor is, ha a tuple egy list elem
```


```python
d
```




    [2, 4, ['alma', True, 'alma'], ('paprika', 'narancs')]




```python
d[3] = ('paradicsom','hagyma')
```


```python
d
```




    [2, 4, ['alma', True, 'alma'], ('paradicsom', 'hagyma')]




```python
# De ha a külső objektum egy tuple, annak az elemei nem módosíthatók, kivéve ha az adott elem egy ú.n. mutable object, mint a lista
```


```python
c
```




    (3, 'alma', [2, 5, 6])




```python
c[2]
```




    [2, 5, 6]




```python
c[2][1] = 3
```


```python
c
```




    (3, 'alma', [2, 3, 6])




```python
# De ezek már nem fognak működni:
```


```python
c[2] = 2
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_9828/2137047556.py in <module>
    ----> 1 c[2] = 2
    

    TypeError: 'tuple' object does not support item assignment



```python
c[1] = 3
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_9828/2460144158.py in <module>
    ----> 1 c[1] = 3
    

    TypeError: 'tuple' object does not support item assignment


## Set


```python
# A set egy rendezetlen halmaz, ami egy adott elemet maximum egyszer tartalmaz. Kapcsos zárójelek között definiáljuk.
```


```python
e = {2, 3, 4, 'alma', 'körte'}
```


```python
e
```




    {2, 3, 4, 'alma', 'körte'}




```python
f = {2, 6, 3.4, 'alma', 'narancs'}
```


```python
# Set elemek
2 in e
```




    True




```python
'alma' in e
```




    True




```python
'narancs' in e
```




    False




```python
# Set bővítés
```


```python
e.add('narancs')
```


```python
e
```




    {2, 3, 4, 'alma', 'körte', 'narancs'}




```python
'narancs' in e
```




    True




```python
# De minden elem csak egyszer
```


```python
e.add(2)
```


```python
e
```




    {2, 3, 4, 'alma', 'körte', 'narancs'}




```python
# Set műveletek
```


```python
# Metszet
e & f
```




    {2, 'alma', 'narancs'}




```python
# Unio
e | f
```




    {2, 3, 3.4, 4, 6, 'alma', 'körte', 'narancs'}




```python
# Különbség
e-f
```




    {3, 4, 'körte'}




```python
f-e
```




    {3.4, 6}




```python
# Set nem indexelhető, az elemeknek nincs sorrendje
e[2]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_9828/675013487.py in <module>
          1 # Set nem indexelhető, az elemeknek nincs sorrendje
    ----> 2 e[2]
    

    TypeError: 'set' object is not subscriptable



```python
# Set listté konvertálható, az elemek sorrendje véletlenszerű
list(e)
```




    ['körte', 2, 3, 4, 'alma', 'narancs']




```python
# List setté alakítható, duplikált elemekből egy marad
```


```python
a
```




    [2, 3, 5, 6.2, 7]




```python
a.append(2)
```


```python
a
```




    [2, 3, 5, 6.2, 7, 2]




```python
set(a)
```




    {2, 3, 5, 6.2, 7}




```python
# Duplikált elemek egyszerűen eltávolíthatók
list(set(a))
```




    [2, 3, 5, 6.2, 7]



## Dictionary


```python
# Key - value párok definiálására szolgál, integer indexek helyett a key az index amivel a value-ra hivatkozunk. Kapcsos zárójelek között key:value felsorolásokkal definiáljuk
```


```python
mydict = {'alma':'piros','dinnye':'sárga','uborka':'zöld'}
```


```python
mydict['alma']
```




    'piros'




```python
# Új elem hozzáadása
mydict['szilva'] = 'lila'
```


```python
mydict
```




    {'alma': 'piros', 'dinnye': 'sárga', 'uborka': 'zöld', 'szilva': 'lila'}




```python
# Key és value bármilyen objektum lehet
mydict[3] = True
```


```python
mydict
```




    {'alma': 'piros',
     'dinnye': 'sárga',
     'uborka': 'zöld',
     'szilva': 'lila',
     3: True}




```python
mydict['randomlista'] = [2, 3, 4, 5]
```


```python
mydict
```




    {'alma': 'piros',
     'dinnye': 'sárga',
     'uborka': 'zöld',
     'szilva': 'lila',
     3: True,
     'randomlista': [2, 3, 4, 5]}




```python
piac = {'alma':{'ár':500,'osztály':1},'narancs':{'ár':800,'osztály':2}}
```


```python
piac['alma']['ár']
```




    500




```python
# Dictionary-k update-elhetők egymással
```


```python
ujpiac = {'alma':{'ár':400,'osztály':2},'paprika':{'ár':400,'osztály':2}}
```


```python
piac.update(ujpiac)
```


```python
piac
```




    {'alma': {'ár': 400, 'osztály': 2},
     'narancs': {'ár': 800, 'osztály': 2},
     'paprika': {'ár': 400, 'osztály': 2}}


