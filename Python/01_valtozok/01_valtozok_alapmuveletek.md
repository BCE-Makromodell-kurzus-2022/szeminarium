# Változók típusai


```python
# Kommentet kettőskereszt után lehet írni, nem lesz végrehajtva
```


```python
# Cella végrehajtása és következő cellára ugrás Shift + Enter
```


```python
# Cella végrehajtása de cellában maradás Ctrl + Enter
```


```python
# Értékadás
a = 5
```


```python
type(a)
```




    int




```python
b = 3.4
```


```python
type(b)
```




    float




```python
c = True
```


```python
type(c)
```




    bool




```python
d = False
```


```python
type(d)
```




    bool




```python
e = "alma"
```


```python
type(e)
```




    str




```python
f = 'narancs'
```


```python
type(f)
```




    str




```python
# Újabb értékadás felülír
f = 5
```


```python
f
```




    5




```python
type(f)
```




    int




```python
# Többszörös értékadás
g, h = 5, "paprika"
```


```python
g
```




    5




```python
h
```




    'paprika'




```python
# Kiértékelés
i = 7+4
```


```python
i
```




    11




```python
j = i+10
```


```python
j
```




    21




```python
type(j)
```




    int




```python
k = j + 3.4
```


```python
k
```




    24.4




```python
type(k)
```




    float




```python
# Bonyolultabb stringek
a = 'Ez egy szöveg \n sortöréssel'
```


```python
a
```




    'Ez egy szöveg \n sortöréssel'




```python
print(a)
```

    Ez egy szöveg 
     sortöréssel



```python
a = '''Ez
egy
több
soros
szöveg'''
```


```python
a
```




    'Ez\negy\ntöbb\nsoros\nszöveg'




```python
print(a)
```

    Ez
    egy
    több
    soros
    szöveg


# Alapműveletek változókkal


```python
int1 = 3
int2 = 4
float1 = 3.2
float2 = 5.6
bool1 = True
bool2 = False
str1 = 'alma'
str2 = 'korte'
str3 = '5'
str4 = '3.1'
str5 = 'True'
str6 = 'False'
```

## Összeadás - type függő


```python
a = int1+int2
type(a)
```




    int




```python
a = int1+float1
type(a)
```




    float




```python
a = int1+bool1
type(a)
```




    int




```python
a
```




    4




```python
a = int1+str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/3362671871.py in <module>
    ----> 1 a = int1+str1
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'



```python
a = int1+str3
```
Stringet számmal nem adhatunk össze (számként reprezentált az int, float és bool), de stringeket konkatenálhatunk

```python
a = str1+str2
```


```python
a
```




    4




```python
type(a)
```




    int



## Változó transzformálás


```python
int(str3)
```




    5




```python
float1 + int(str3)
```




    8.2




```python
float1 + int(str4)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    /tmp/ipykernel_31455/1836567247.py in <module>
    ----> 1 float1 + int(str4)
    

    ValueError: invalid literal for int() with base 10: '3.1'



```python
float1 + float(str3)
```




    8.2




```python
int(True)
```




    1




```python
int(False)
```




    0




```python
float(True)
```




    1.0




```python
float(False)
```




    0.0




```python
bool(1)
```




    True




```python
bool(0)
```




    False




```python
bool(10)
```




    True




```python
bool(0.5)
```




    True




```python
bool(-1)
```




    True




```python
bool(-4.56)
```




    True




```python
bool('alma')
```




    True




```python
bool('')
```




    False




```python
str(True)
```




    'True'




```python
str(False)
```




    'False'




```python
str(3.4)
```




    '3.4'



## Kivonás
Számokkal és boolean változókkal működik gond nélkül

```python
float1-int2-bool1-bool2-float2
```




    -7.3999999999999995


Stringet, illetve stringből nem lehet kivonni

```python
str1-str2
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/533321809.py in <module>
    ----> 1 str1-str2
    

    TypeError: unsupported operand type(s) for -: 'str' and 'str'



```python
float1-str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/1187642493.py in <module>
    ----> 1 float1-str1
    

    TypeError: unsupported operand type(s) for -: 'float' and 'str'



```python
str1-float1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/790374843.py in <module>
    ----> 1 str1-float1
    

    TypeError: unsupported operand type(s) for -: 'str' and 'float'



```python
int1-str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2973981053.py in <module>
    ----> 1 int1-str1
    

    TypeError: unsupported operand type(s) for -: 'int' and 'str'



```python
str1-int1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2808133596.py in <module>
    ----> 1 str1-int1
    

    TypeError: unsupported operand type(s) for -: 'str' and 'int'



```python
bool1-str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/3363146139.py in <module>
    ----> 1 bool1-str1
    

    TypeError: unsupported operand type(s) for -: 'bool' and 'str'



```python
str1-bool1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2286599795.py in <module>
    ----> 1 str1-bool1
    

    TypeError: unsupported operand type(s) for -: 'str' and 'bool'


## Szorzás


```python
int1*int2
```




    12




```python
int1*float1
```




    9.600000000000001


Látható, hogy a számítógép közelíti az eredményt, nem feltétlenül pontos. Az úgynevezett computer precision hardver és beállításfüggő.

```python
float1*float2
```




    17.919999999999998




```python
int1*bool1
```




    3




```python
int1*bool2
```




    0




```python
float1*bool1
```




    3.2




```python
float1*bool2
```




    0.0




```python
str1*str2
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/4199405932.py in <module>
    ----> 1 str1*str2
    

    TypeError: can't multiply sequence by non-int of type 'str'



```python
str1*bool1
```




    'alma'




```python
str1*bool2
```




    ''




```python
str1*int1
```




    'almaalmaalma'




```python
int1*str1
```




    'almaalmaalma'




```python
str1*float1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/4192844329.py in <module>
    ----> 1 str1*float1
    

    TypeError: can't multiply sequence by non-int of type 'float'

String csak integerrel szorozható, a bool integerként reprezentált, így működik.
## Osztás


```python
int1/int2
```




    0.75




```python
float1/float2
```




    0.5714285714285715




```python
int1/float1
```




    0.9375




```python
float1/int1
```




    1.0666666666666667




```python
int1/bool1
```




    3.0




```python
int1/bool2
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    /tmp/ipykernel_31455/14314200.py in <module>
    ----> 1 int1/bool2
    

    ZeroDivisionError: division by zero



```python
float1/bool1
```




    3.2




```python
float1/bool2
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    /tmp/ipykernel_31455/911925175.py in <module>
    ----> 1 float1/bool2
    

    ZeroDivisionError: float division by zero



```python
bool1/int1
```




    0.3333333333333333




```python
bool2/float1
```




    0.0


Stringet nem lehet osztani és nem lehet osztó.

```python
int1/str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/698043087.py in <module>
    ----> 1 int1/str1
    

    TypeError: unsupported operand type(s) for /: 'int' and 'str'



```python
str1/int1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2323581952.py in <module>
    ----> 1 str1/int1
    

    TypeError: unsupported operand type(s) for /: 'str' and 'int'



```python
float1/str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2218432358.py in <module>
    ----> 1 float1/str1
    

    TypeError: unsupported operand type(s) for /: 'float' and 'str'



```python
str1/float1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2050698186.py in <module>
    ----> 1 str1/float1
    

    TypeError: unsupported operand type(s) for /: 'str' and 'float'



```python
bool1/str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/2166117422.py in <module>
    ----> 1 bool1/str1
    

    TypeError: unsupported operand type(s) for /: 'bool' and 'str'



```python
str1/bool1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/1210716140.py in <module>
    ----> 1 str1/bool1
    

    TypeError: unsupported operand type(s) for /: 'str' and 'bool'


## Hatványozás


```python
float1**int1
```




    32.76800000000001




```python
pow(float1,int1)
```




    32.76800000000001




```python
int1**float1
```




    33.63473536961897




```python
float2**bool2
```




    1.0


Stringet nem hatványozunk és nem lehet kitevő.

```python
str1**3
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/3127011896.py in <module>
    ----> 1 str1**3
    

    TypeError: unsupported operand type(s) for ** or pow(): 'str' and 'int'



```python
3**str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/1721925106.py in <module>
    ----> 1 3**str1
    

    TypeError: unsupported operand type(s) for ** or pow(): 'int' and 'str'


## Modulus, törtrész


```python
5 % 3
```




    2




```python
3.5 % 1.7
```




    0.10000000000000009




```python
-2.5 % 2.3
```




    2.0999999999999996



## Alsó egészrész


```python
5 // 2
```




    2




```python
3.5 // 1.1
```




    3.0




```python
-5 // 2
```




    -3


Alsó egészrész * osztó + törtrész = osztandó

```python
(-72.242//2.3)*2.3+(-72.242%2.3)
```




    -72.242



## Logikai


```python
# And: Akkor és csak akkor igaz, ha mindegyik igaz
True and True
```




    True




```python
True and False
```




    False




```python
False and False
```




    False




```python
True and True and True
```




    True




```python
True and True and False
```




    False




```python
# Or: Akkor igaz, ha legalább az egyik igaz
True or True
```




    True




```python
True or False
```




    True




```python
False or False
```




    False




```python
True or False or False
```




    True




```python
# Not: Tagadás
not True
```




    False




```python
not False
```




    True




```python
not False or False
```




    True




```python
not True or False
```




    False



## Relációk


```python
int1>int2
```




    False




```python
int1<=int2
```




    True




```python
float1<int2
```




    True




```python
float1>=int1
```




    True




```python
float1>bool1
```




    True




```python
float1>str1
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_31455/3186386486.py in <module>
    ----> 1 float1>str1
    

    TypeError: '>' not supported between instances of 'float' and 'str'



```python
str1>str2
```




    False




```python
# Stringek lexikografikusan kerülnek sorbarendezésre
```


```python
float1==float1
```




    True




```python
float1!=float2
```




    True



# Kiértékelés sorrendje


```python
# Balról jobbra, magasabb rendű műveletek elsőbbséget élveznek, először zárójelen belül van kiértékelés
```


```python
3+2*2
```




    7




```python
(3+2)*2
```




    10




```python
(3+4)**False
```




    1




```python
3**2*(True or False)
```




    9




```python
3**2*(True or False)*2
```




    18




```python
3**2*((True or False)*2)
```




    18




```python
3**(2*(True or False))*2
```




    18




```python
3**(2*((True or False)*2))
```




    81


