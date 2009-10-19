---
layout: post
title: Odpowiedzi laboratorium 1
---

# {{ page.title }}

## Zadanie 1
<pre>
[mskorb@sigma temp]$ cal -m
  październik 2009
po wt śr cz pi so ni
          1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15 16 17 18
19 20 21 22 23 24 25
26 27 28 29 30 31
</pre>

## Zadanie 2
<pre>
[mskorb@sigma temp]$ date -d 1975-05-25 +%A
niedziela
</pre>

## Zadanie 3
<pre>
[mskorb@sigma ~]$ mkdir temp
[mskorb@sigma temp]$ mkdir dom
[mskorb@sigma temp]$ mkdir nauka
[mskorb@sigma temp]$ cd nauka
[mskorb@sigma nauka]$ mkdir c
[mskorb@sigma nauka]$ mkdir logo
[mskorb@sigma nauka]$ mkdir pascal
[mskorb@sigma nauka]$ cd ..
[mskorb@sigma temp]$ mkdir praca
[mskorb@sigma temp]$ cd praca
[mskorb@sigma praca]$ mkdir dokumenty
[mskorb@sigma praca]$ mkdir zlecenia
[mskorb@sigma praca]$ cd zlecenia
[mskorb@sigma zlecenia]$ mkdir niezrealizowane
[mskorb@sigma zlecenia]$ mkdir zrealizowane
[mskorb@sigma zlecenia]$ cd .. 
[mskorb@sigma praca]$ cd ..
[mskorb@sigma temp]$ tree
.
|-- dom
|-- nauka
|   |-- c
|   |-- logo
|   `-- pascal
`-- praca
    |-- dokumenty
    `-- zlecenia
        |-- niezrealizowane
        `-- zrealizowane
</pre>

## Zadanie 4
<pre>
[mskorb@sigma temp]$ cd dom
[mskorb@sigma dom]$ mkdir wazne-sprawy
</pre>

## Zadanie 5

<pre>
[mskorb@sigma dom]$ cd wazne-sprawy
[mskorb@sigma wazne-sprawy]$ echo 12345678911 > rachunki.txt
[mskorb@sigma wazne-sprawy]$ ls
rachunki.txt
</pre>

## Zadanie 6

<pre>
[mskorb@sigma wazne-sprawy]$ cp rachunki.txt ../../praca/zlecenia/zrealizowane
[mskorb@sigma wazne-sprawy]$ cd ..
[mskorb@sigma dom]$ cd ..
[mskorb@sigma temp]$ cd praca
[mskorb@sigma praca]$ cd zlecenia
[mskorb@sigma zlecenia]$ cd zrealizowane
[mskorb@sigma zrealizowane]$ ls
rachunki.txt

</pre>


## Zadanie 7

<pre>
[mskorb@sigma temp]$ cd praca
[mskorb@sigma praca]$ cd zlecenia
[mskorb@sigma zlecenia]$ cd zrealizowane
[mskorb@sigma zrealizowane]$ ls
rachunki.txt
[mskorb@sigma zrealizowane]$ mv rachunki.txt wykonano.txt
[mskorb@sigma zrealizowane]$ ls
wykonano.txt
</pre>


## Zadanie 8

<pre>
[mskorb@sigma zrealizowane]$ split --bytes=5 wykonano.txt
[mskorb@sigma zrealizowane]$ ls
wykonano.txt  xaa  xab  xac
[mskorb@sigma zrealizowane]$ cat xaa
12345
[mskorb@sigma zrealizowane]$ cat xab
67891
[mskorb@sigma zrealizowane]$ cat xac
1

</pre>


## Zadanie 9

<pre>
mskorb@sigma zrealizowane]$ cd ..
[mskorb@sigma zlecenia]$ cd ..
[mskorb@sigma praca]$ cd ..
[mskorb@sigma temp]$ tree
.
|-- dom
|   |-- rachunki.txt
|   `-- wazne-sprawy
|-- nauka
|   |-- c
|   |-- logo
|   `-- pascal
`-- praca
    |-- dokumenty
    `-- zlecenia
        |-- niezrealizowane
        `-- zrealizowane
            |-- wykonano.txt
            |-- xaa
            |-- xab
            `-- xac

11 directories, 5 files
[mskorb@sigma temp]$ cd nauka
[mskorb@sigma nauka]$ cd logo
[mskorb@sigma logo]$ cp ../../praca/zlecenia/zrealizowane/x* ../../praca/dokumenty

</pre>

## Zadanie 10

<pre>
[mskorb@sigma logo]$ cd ..
[mskorb@sigma nauka]$ cd ..
[mskorb@sigma temp]$ ls
dom  nauka  praca
[mskorb@sigma temp]$ cd praca
[mskorb@sigma praca]$ cd dokumenty
[mskorb@sigma dokumenty]$ ls
xaa  xab  xac
[mskorb@sigma dokumenty]$ cat x*
12345678901
[mskorb@sigma dokumenty]$ cat x* >> odtworzono.txt
[mskorb@sigma dokumenty]$ ls
odtworzono.txt  xaa  xab  xac
[mskorb@sigma dokumenty]$ cp odtworzono.txt ../../dom/wazne-sprawy
</pre>

## Zadanie 11

<pre>
[mskorb@sigma dokumenty]$ cd ..
[mskorb@sigma praca]$ cd ..
[mskorb@sigma temp]$ cd ..
[mskorb@sigma ~]$ cd temp
[mskorb@sigma temp]$ cd dom
[mskorb@sigma dom]$ ls
wazne-sprawy
[mskorb@sigma dom]$ cd wazne-sprawy
[mskorb@sigma wazne-sprawy]$ ls
odtworzono.txt rachunki.txt
[mskorb@sigma wazne-sprawy]$ diff ./odtworzono.txt ../../praca/zlecenia/zrealizowane/wykonano.txt
</pre>

## Zadanie 12

<pre>
[mskorb@sigma wazne-sprawy]$ 
[mskorb@sigma wazne-sprawy]$ cd ..
[mskorb@sigma dom]$ cd ..
[mskorb@sigma temp]$ cd nauka/c
[mskorb@sigma c]$ touch program.c
[mskorb@sigma c]$ emacs program.c
</pre>


