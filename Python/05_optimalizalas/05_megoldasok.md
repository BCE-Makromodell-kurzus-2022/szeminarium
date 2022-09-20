Egy ket idoszakig elo fogyaszto elso idoszaki jovedelme 100 egyseg, masodik idoszaki jovedelme 120 egyseg. A fogyaszto mindket idoszakban 109.87 egyseget fogyaszt. Milyen kamatlab mellett all elo a fenti egysensuly?


```python
from scipy.optimize import fsolve
def koltsegvetes(r):
    return 100+120/(1+r)-109.87-109.87/(1+r)

fsolve(koltsegvetes, 0)
```




    array([0.02634245])



Egy gazdasagban a termelesi fuggveny Cobb-Douglas, a teljes termelekenyseg 1.7. Ha a tokeallomany 100 egyseg, a munkaallomany 200 egyseg, a teljes termeles erteke 180 egyseg. Mekkora a reprezentativ vallalat teljes tokekoltsege?


```python
def termeles(a):
    return 200-1.7*100**a*130**(1-a)

fsolve(termeles, 0.2)[0]*200
```




    76.11199274593858



Egy RBC gazdasagban (eredeti, nem linearizalt modell) allandosult allapotban a kibocsatas 130 egyseg. A teljes termelekenyseg 1.2, a termelesi fuggveny Cobb-Douglas. Az egyensulyi munkaallomany 70 egyseg, a toke realberleti dija 0.2 egyseg. A termelesi es a tokekeresleti fuggveny felhasznalasaval hatarozd meg az egyensulyi tokeallomanyt es a tokekoltseg aranyat.


```python
def rbc(val):
    K = val[0]
    a = val[1]
    eq1=130-1.2*K**a*70**(1-a)
    eq2=0.2-a*130/K
    return [eq1, eq2]

fsolve(rbc, [130, 0.5])
```




    array([234.66533306,   0.36102359])



Az alábbiakat ismerjük egy végtelen időszakig működő RBC gazdaságról:

ß=0.97, az amortizációs ráta 3 százalék.
A termelési függvény Cobb-Douglas, a teljes termelékenység 1.4, a tőkejavakra fordított kiadások a vállalat teljes költségének 38 százalékát teszik ki.
Állandósult állapotban a munkakínálat w/C=L^0.4 alakú.
A gazdaság állandósult állapotban van. Hatarozd meg a termeles erteket allandosult allapotban.


```python
from scipy.optimize import fsolve

def rbc(variables):
    K, L= variables
    r = 1/0.97-1
    d = 0.03
    rk = r+d
    e = [
        1.4*K**0.38*L**0.62-(1.2*0.62*(K/L)**0.38)/L**0.4-d*K,
        1.4*0.38*(L/K)**0.62-rk
    ]
    return e

K, L = fsolve(rbc,[5,1])
print(1.4*K**0.38*L**0.62)
```

    3.9001352664177156

