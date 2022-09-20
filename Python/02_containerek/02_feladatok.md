# A következő cellában több objektumot definiálunk. Határozd meg az alatta látható cellákban lévő kifejezések értékét. Verifikáld az eredményeid a kód lefuttatásával.


```python
a = [2, 'alma', [3, 'paprika']]
b = (2, [3, 6], 5)
c = {'alma':5,'narancs':[2, 3]}
d = [{2:3,4:8},('alma','paradicsom','krumpli'),'hagyma',['négy']]
```


```python
a[0]
```


```python
a[2][1]
```


```python
a[-1][0]
```


```python
b[-2]
```


```python
c['narancs'][1]
```


```python
d[2]
```


```python
d[0][4]
```


```python
d[-1][0]
```

# Vedd az első feladatban szereplő objektumokat. Az alábbi parancsok közül melyik eredményez hibát?  Verifikáld az eredményeid a kód lefuttatásával.


```python
b[1] = 4
```


```python
b[1][0] = 5
```


```python
d[1][2] = 0
```


```python
d[1] = 3
```


```python
c['narancs'] = d[0]
```
