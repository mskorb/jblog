---
layout: post
title: Odpowiedzi laboratorium 1 (poprawione)
---

# {{ page.title }}

## Zadanie 1
Używając linii poleceń stwórz strukturę katalogów.

<hr />
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

## Zadanie 2
Przejdź do katalogu dom i utwórz katalog wazne-sprawy.

<hr />
<pre>
[mskorb@sigma temp]$ cd dom
[mskorb@sigma dom]$ mkdir wazne-sprawy
</pre>

## Zadanie 3
Wejdź do katalogu wazne-sprawy i utwórz tam pusty plik rachunki.txt.

<hr />
<pre>
[mskorb@sigma dom]$ cd wazne-sprawy
[mskorb@sigma wazne-sprawy]$ touch rachunki.txt
[mskorb@sigma wazne-sprawy]$ ls
rachunki.txt
</pre>

## Zadanie 4
Będąc w katalogu wazne-sprawy skopiuj plik rachunki.txt do katalogu zrealizowane.

<hr />
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


## Zadanie 5
Przejdź do katalogu zrealizowane i zmień nazwę pliku rachunki.txt na wykonano.txt.

<hr />
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


## Zadanie 6
Utwórz plik wykonano.txt wielkości 11 bajtów, następnie podziel go pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki. (split)

<hr/>
<pre>
[mskorb@sigma zrealizowane]$ echo 1234567890 > rachunki.txt
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


## Zadanie 7
Będąc w katalogu logo skopiuj powyżej otrzymane 3 pliki do katalogu dokumenty.

<hr />
<pre>
mskorb@sigma zrealizowane]$ cd ..
[mskorb@sigma zlecenia]$ cd ..
[mskorb@sigma praca]$ cd ..
[mskorb@sigma temp]$ cd nauka
[mskorb@sigma nauka]$ cd logo
[mskorb@sigma logo]$ cp ../../praca/zlecenia/zrealizowane/x* ../../praca/dokumenty

</pre>

## Zadanie 8
Będąc w katalogu dokumenty połącz skopiowane 3 pliki w plik odtworzono.txt, tak aby otrzymać plik o zawartości identycznej z wykonano.txt. Następnie plik odtworzono.txt skopiuj do katalogu wazne-sprawy.

<hr />
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

## Zadanie 9
Będąc w katalogu wazne-sprawy sprawdź, czy są jakieś różnice w zawartości plików wykonano.txt i odtworzono.txt.

<hr />
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

## Zadanie 10
Wyświetl kalendarz na październik 2009 r. (cal)

<hr />
<pre>
[mskorb@sigma sp]$ cal -m
  październik 2009
po wt śr cz pi so ni
          1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15 16 17 18
19 20 21 22 23 24 25
26 27 28 29 30 31

</pre>

Wyświetl kalendarz na wrzesień, październik i listopad 2009 r.
 z miesiącami obok siebie (cal).

<pre>

[mskorb@sigma temp]$ cal -3m
    wrzesień 2009       październik 2009        listopad 2009
po wt śr cz pi so ni  	po wt śr cz pi so ni  	po wt śr cz pi so ni
    1  2  3  4  5  6            1  2  3  4                     1
 7  8  9 10 11 12 13   	5  6  7  8  9 10 11  	 2  3  4  5  6  7  8
14 15 16 17 18 19 20  	12 13 14 15 16 17 18  	 9 10 11 12 13 14 15
21 22 23 24 25 26 27  	19 20 21 22 23 24 25  	16 17 18 19 20 21 22
28 29 30              	26 27 28 29 30 31     	23 24 25 26 27 28 29
                                            	30
</pre>

Wyświetl kalendarz na październik, listopad i grudzień 2009 r.

<pre>

[mskorb@sigma temp]$ cal 11 2009 -3m
  październik 2009        listopad 2009         grudzień 2009
po wt śr cz pi so ni  po wt śr cz pi so ni  po wt śr cz pi so ni
          1  2  3  4                     1      1  2  3  4  5  6
 5  6  7  8  9 10 11   2  3  4  5  6  7  8   7  8  9 10 11 12 13
12 13 14 15 16 17 18   9 10 11 12 13 14 15  14 15 16 17 18 19 20
19 20 21 22 23 24 25  16 17 18 19 20 21 22  21 22 23 24 25 26 27
26 27 28 29 30 31     23 24 25 26 27 28 29  28 29 30 31
                      30
</pre>

##Zadanie 11
Jaki był dzień tygodnia 25 maja 1975 r. (cal i date)
<pre>
[mskorb@sigma temp]$ date -d 1975-05-25 +%A
niedziela
</pre>
