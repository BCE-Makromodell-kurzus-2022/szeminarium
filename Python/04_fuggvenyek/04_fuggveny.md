# Függvények

Változókon rendszeresen elvégzett műveletekhez érdemes függvényeket definiálni a kódismétlés elkerülésére. A függvények `def fuggvenynev(inputok):` szintaxissal definiálható, a függvény által elvégzett műveleteket indentálni kell. A függvény outputját a `return` parancs után definiáljuk. Fontos, hogy a függvényen belül definiált változók egy külön ú.n. namespace-en vannak, így a függvényen kívülről nem elérhetők és nem módosítják a global namespace-en lévő változókat. 


```python
# Példa
def osszead(a,b):
    return a+b
```


```python
osszead(3,4)
```




    7




```python
osszead("alma","narancs")
```




    'almanarancs'




```python
# Namespace példa
x = 'alma'
def xkorte():
    x = 'körte'
    print(x)

xkorte()
print(x)
```

    körte
    alma



```python
# Példa: Bontsunk egy számot a tört és egészrészére
def tortegesz(szam):
    egeszresz = szam//1
    tortresz = szam%1
    return [egeszresz, tortresz]
```


```python
tortegesz(3.44)
```




    [3.0, 0.43999999999999995]




```python
tortegesz(-2.222)
```




    [-3.0, 0.778]


