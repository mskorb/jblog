---
layout: post
title: Odpowiedzi laboratorium 3
---

# {{ page.title }}

## Zadanie 1

Wyświetl plik /etc/passwd z podziałem na strony 
przyjmując, że strona na 5 linii tekstu.

<pre>
[mskorb@sigma etc]$ pg -5 /etc/passwd
</pre>

## Zadanie 2 

Korzystając z polecenia cat utwórz plik 
tekst3.txt, który będzie składał się z 
zawartości pliku tekst1.txt, ciągu znaków 
podanego ze standardowego wejścia (klawiatury) i 
pliku tekst2.txt.

<pre>

[mskorb@sigma sp]$ cat > tekst1.txt
t1
[mskorb@sigma sp]$ ls
tekst1.txt
[mskorb@sigma sp]$ cat > tekst2.txt
t2
[mskorb@sigma sp]$ cat tekst1.txt > tekst3.txt
[mskorb@sigma sp]$ ls
tekst1.txt  tekst2.txt  tekst3.txt
[mskorb@sigma sp]$ cat >> tekst3.txt
tekst z klawiatury
[mskorb@sigma sp]$ cat tekst3.txt
t1
tekst z klawiatury
t2
</pre>

## Zadanie 3

Wyświetl po 5 pierwszych linii wszystkich plików 
w swoim katalogu domowym w taki sposób, aby nie 
były wyświetlane ich nazwy.
<pre>
[mskorb@sigma sp]$ head --quiet --lines 5 *

wariant skrótowy:
[mskorb@sigma sp]$ head -qn 5 *
</pre>
## Zadanie 4 

Wyświetl linie o numerach 3, 4 i 5 z pliku 
/etc/passwd.
<pre>
[mskorb@sigma ~]$ nl /etc/passwd > passwd
[mskorb@sigma ~]$ ls
[mskorb@sigma ~]$ head -n 5 passwd  | tail -n 3
</pre>

## Zadanie 5

Wyświetl linie o numerach 7, 6 i 5 od końca 
pliku /etc/passwd.
<pre>
[mskorb@sigma ~]$ cat /etc/passwd | sed -n 3,5p
daemon:x:2:2:daemon:/sbin:/bin/false
adm:x:3:4:adm:/var/account:/bin/false
lp:x:4:7:lp:/var/spool/lpd:/bin/false

</pre>
## Zadanie 6

Wyświetl zawartość pliku /etc/passwd w jednej 
linii.
<pre>
[mskorb@sigma sp]$ cat /etc/passwd  | tr --delete "\n"

wariant skrótowy:
[mskorb@sigma sp]$ cat /etc/passwd  | tr -d "\n"
</pre>
## Zadanie 7

Za pomocą filtru tr wykonaj modyfikację pliku 
plik.txt, polegającą na umieszczeniu każdego 
słowa w osobnej linii.
<pre>

</pre>
## Zadanie 8

Zlicz wszystkie pliki znajdujące się w katalogu 
/etc i jego podkatalogach
<pre>
[mskorb@sigma ~]$ find /etc/ -type f 2> errors | wc -l
831

</pre>
## Zadanie 9

Napisać polecenie zliczające ilość znaków z 
pierwszych trzech linii pliku /etc/passwd.
<pre>
[mskorb@sigma ~]$ head /etc/passwd -n 3 | wc -c
99
</pre>