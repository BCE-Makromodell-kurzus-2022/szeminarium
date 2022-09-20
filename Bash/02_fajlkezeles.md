---
papersize: a4
documentclass: article
header-includes:
    - \usepackage{multicol}
    - \usepackage[magyar]{babel}
    - \DeclareUnicodeCharacter{25CF}{$\bullet$}
    - \DeclareUnicodeCharacter{251C}{\mbox{\kern.23em \vrule height2.2exdepth1exwidth.4pt\vrule height2.2ptdepth-1.8ptwidth.23em}}
    - \DeclareUnicodeCharacter{2500}{\mbox{\vrule height2.2ptdepth-1.8ptwidth.5em}}
    - \DeclareUnicodeCharacter{2514}{\mbox{\kern.23em \vrule height2.2exdepth-1.8ptwidth.4pt\vrule height2.2ptdepth-1.8ptwidth.23em}} 
    - \DeclareUnicodeCharacter{2502}{|}
    - \usepackage[utf8]{inputenc}
    - \usepackage[margin=.3in]{geometry}
    - \newcommand{\hideFromPandoc}[1]{#1}
    - \hideFromPandoc{
        \let\Begin\begin
        \let\End\end
      }
...


# Bash Feladatok - Fájlkezelés
A feladatok fordítással és kisebb módosításokkal a Software Carpentry-től származnak és itt érhetők el: http://software-carpentry.org/

------

\Begin{multicols}{2}

## 1. Feladat
Láttuk, hogyan készíthetünk új fájlokat a `nano` paranccsal. Próbáld ki az alábbi parancsot:

```
touch my_file.txt
```

- Mit csinált a `touch` parancs? Megjelenik a fájl a grafikus fájlkezelőben?
- Vizsgáld meg alaposabban is a keletkezett fájlt az `ls -l` paranccsal. Mekkora az új fájl?
- Mit gondolsz, mikor lehet hasznos a `touch` parancs?

## 2. Feladat
Jamie az alábbi parancsokat lefuttatva és az outputjukat megvizsgálva arra a következtetésre jut, hogy a `sucrose.dat` és a `maltose.dat` fájlok rossz helyen vannak, a `raw` mappában kéne lenniük.

```
$ ls -F
 analyzed/ raw/
$ ls -F analyzed
fructose.dat glucose.dat maltose.dat sucrose.dat
$ cd analyzed
```

Egészítsd ki az alábbi parancs üresen hagyott helyeit, hogy a fájlok a helyükre kerüljenek.

```
$ mv sucrose.dat maltose.dat ____/____
```

## 3. Feladat
Tegyük fel, hogy a jelenlegi mappádban készítettél egy szövegfájlt, ami felsorolja azokat a statisztikai teszteket amit le kell futtatnod az adataidon. Ezt a fájt `statstics.txt` néven mentetted el. Miután ezt megtetted, észrevetted, hogy elírtad a fájl nevét és ezt ki szeretnéd javítani. Az alábbi parancsok közül melyikkel teheted ezt meg?

1. `cp statstics.txt statistics.txt`
2. `mv statstics.txt statistics.txt`
3. `mv statstics.txt .`
4. `cp statstics.txt .`

## 4. Feladat
Alább néhány lefuttatott parancsot, illetve ahol van, azok outputjait látod. Mi lesz az utolsóként lefuttatott `ls` parancs outputja?
```
$ pwd
/Users/jamie/data
$ ls
proteins.dat
$ mkdir recombined
$ mv proteins.dat recombined/
$ cp recombined/proteins.dat ../proteins-saved.dat
$ ls
```

1. `proteins-saved.dat recombined`
2. `recombined`
3. `proteins.dat recombined`
4. `proteins-saved.dat`

## 5. Feladat
Sam egy mappája az alábbiak szerint van strukturálva: 
```
.
├── 2015-10-23-calibration.txt
├── 2015-10-23-dataset1.txt
├── 2015-10-23-dataset2.txt
├── 2015-10-23-dataset_overview.txt
├── 2015-10-26-calibration.txt
├── 2015-10-26-dataset1.txt
├── 2015-10-26-dataset2.txt
├── 2015-10-26-dataset_overview.txt
├── 2015-11-23-calibration.txt
├── 2015-11-23-dataset1.txt
├── 2015-11-23-dataset2.txt
├── 2015-11-23-dataset_overview.txt
├── backup
│   ├── calibration
│   └── datasets
└── send_to_bob
    ├── all_datasets_created_on_a_23rd
    └── all_november_files
```

Mielőtt egy újabb kísérletbe kezdene szeretne biztonsági másolatot készíteni az adatairól, illetve azok egy részét elküldeni kollégájának Bobnak. Sam az alábbi parancsokat használja ehhez:

```
$ cp *dataset* backup/datasets
$ cp ____calibration____ backup/calibration
$ cp 2015-____-____ send_to_bob/all_november_files/
$ cp ____ send_to_bob/all_datasets_created_on_a_23rd/
```

Segíts Samnek azzal, hogy kitöltöd a hiányzó részeket. A parancsok lefuttatása után az alábbi mappaszerkezetet kell kapnod:

```
.
├── 2015-10-23-calibration.txt
├── 2015-10-23-dataset1.txt
├── 2015-10-23-dataset2.txt
├── 2015-10-23-dataset_overview.txt
├── 2015-10-26-calibration.txt
├── 2015-10-26-dataset1.txt
├── 2015-10-26-dataset2.txt
├── 2015-10-26-dataset_overview.txt
├── 2015-11-23-calibration.txt
├── 2015-11-23-dataset1.txt
├── 2015-11-23-dataset2.txt
├── 2015-11-23-dataset_overview.txt
├── backup
│   ├── calibration
│   │   ├── 2015-10-23-calibration.txt
│   │   ├── 2015-10-26-calibration.txt
│   │   └── 2015-11-23-calibration.txt
│   └── datasets
│       ├── 2015-10-23-dataset1.txt
│       ├── 2015-10-23-dataset2.txt
│       ├── 2015-10-23-dataset_overview.txt
│       ├── 2015-10-26-dataset1.txt
│       ├── 2015-10-26-dataset2.txt
│       ├── 2015-10-26-dataset_overview.txt
│       ├── 2015-11-23-dataset1.txt
│       ├── 2015-11-23-dataset2.txt
│       └── 2015-11-23-dataset_overview.txt
└── send_to_bob
    ├── all_datasets_created_on_a_23rd
    │   ├── 2015-10-23-dataset1.txt
    │   ├── 2015-10-23-dataset2.txt
    │   ├── 2015-10-23-dataset_overview.txt
    │   ├── 2015-11-23-dataset1.txt
    │   ├── 2015-11-23-dataset2.txt
    │   └── 2015-11-23-dataset_overview.txt
    └── all_november_files
        ├── 2015-11-23-calibration.txt
        ├── 2015-11-23-dataset1.txt
        ├── 2015-11-23-dataset2.txt
        └── 2015-11-23-dataset_overview.txt
```

# 6. Feladat

Egy új kísérletbe kezdesz és ehhez duplikálni szeretnéd egy korábbi kísérleted mappaszerkezetét. Tegyük fel, hogy a korábbi kísérleted adatai a `2016-05-18-data` mappában vannak, amiben van egy `data` mappa, azon belül pedig egy `raw` és egy `processed` mappa amelyek adatfájlokat tartalmaznak. A célod, hogy előállíts egy `2016-05-20` nevű mappát azonos szerkezettel, tehát az alábbit szeretnéd elérni:

```
2016-05-20/
└── data
    ├── processed
    └── raw
``` 

Az alábbiak közül melyik kódsorok segítségével érheted el ezt?

### 1.

```
$ mkdir 2016-05-20
$ mkdir 2016-05-20/data
$ mkdir 2016-05-20/data/processed
$ mkdir 2016-05-20/data/raw
```

### 2.

```
$ mkdir 2016-05-20
$ cd 2016-05-20
$ mkdir data
$ cd data
$ mkdir raw processed
```

### 3.

```
$ mkdir 2016-05-20/data/raw
$ mkdir 2016-05-20/data/processed
```

### 4.

```
$ mkdir -p 2016-05-20/data/raw
$ mkdir -p 2016-05-20/data/processed
```

### 5.

```
$ mkdir 2016-05-20
$ cd 2016-05-20
$ mkdir data
$ mkdir raw processed
```
\End{multicols}
