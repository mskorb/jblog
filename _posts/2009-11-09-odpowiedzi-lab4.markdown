---
layout: post
title: Odpowiedzi laboratorium 4
---

# {{ page.title }}

## Zadanie 1
Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.
<pre>
Dla poczatkujacych:

[mskorb@localhost sp]$ ls
tekst1.txt  tekst2.txt  tekst3.txt
[mskorb@localhost sp]$ ls | tr a-z A-Z
TEKST1.TXT
TEKST2.TXT
TEKST3.TXT

[mskorb@localhost sp]$ ls | tr a-zą A-ZĄ

</pre>

<pre>
Drugie rozwiazanie:

[mskorb@localhost sp]$ ls | tr '[:lower:]' '[:upper:]' 
TEKST1.TXT
TEKST2.TXT
TEKST3.TXT
</pre>


## Zadanie 2
Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.
<pre>
[mskorb@localhost sp]$ ls -l | cut -b 1-10,28-33,48-
</pre>

## Zadanie 3

Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.

<pre>
[mskorb@localhost sp]$ ls --sort=size -l
razem 8
-rw-r--r-- 1 mskorb studinf 19 10-29 18:28 tekst3.txt
-rw-r--r-- 1 mskorb studinf  3 10-29 18:26 tekst2.txt
-rw-r--r-- 1 mskorb studinf  0 10-29 18:25 tekst1.txt

Wariant skrótowy:
[mskorb@localhost sp]$ ls -s -l
</pre>

## Zadanie 4
Wyświetl zawartość pliku /etc/passwd posortowaną według numerów UID w kolejności od największego do najmniejszego.
 <pre>
[mskorb@localhost]$ cat /etc/passwd/ | sort --reverse --general-numeric-sort --key 3
</pre>

## Zadanie 5
Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.
<pre>
[mskorb@localhost]$ cat /etc/passwd/ | sort --general-numeric-sort --key 4,3 --reverse
 </pre>
## Zadanie 6
Podaj liczbę plików każdego użytkownika.

<pre>
Na sigmie: brak uprawnien
prosta wersja: domowa
</pre>

## Zadanie 7

Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj ile razy zostało ono przydzielone).
ls -l
ile jest r ile w ile x
 
 <pre>
[mskorb@localhost$ find -printf "%m\n" | sort | uniq -c
 </pre>

## Zadanie 8 

Czy potrafisz odpowiedzieć jaki będzie efekt wykonania poniższych poleceń?
  
<pre>
ls -l > lsout.txt                          #  1
</pre>
Zapisanie do pliku  lsout.txt szczególowej listy plików z aktualnego katalogu.

<pre>
ls -la >> lsout.txt                        #  2
</pre>
Dopisanie do pliku  lsout.txt szczególowej listy plików, lacznie z plikami zaczynajacymi sie od "." (ukrytymi) z aktualnego katalogu.

<pre>
ps >> psout.txt                            #  3
</pre>
Dopisuje do pliku psout.txt opis biezacych procesow.

<pre>
free -m >> ~/wynik                         #  4
</pre>
Dopisanie do pliku znajdującego się w lokalizacji "~/wynik" informacji o wolnej i wykorzystanej pamieci podanej w megabajtach.
   
<pre>
kill -1 1234 > killout.txt 2>killerr.txt   #  5
</pre>
 Zakonczenie procesu o id 1234 oraz przakazanie komunikatow informacyjnych do pliku killout.txt, natomiast bledy zapisz do pliku killerr.txt

<pre>
kill -1 1234 > killout.txt 2>&1            #  6
</pre>
Zakonczenie procesu o id 1234 komunikaty informacyjne zapisz do pliku "killout.txt" a bledy wypisz na ekran.

<pre>
kill -1 1234 > /dev/null 2>&1              #  7
</pre>
Zakonczenie procesu o id 1234 komunikaty informacyjne zapisz w lokalizacji "/dev/null" a bledy wypisz na ekran.

<pre>
sort psout.txt > pssort.txt                #  8
</pre>
Sortowanie procesow w pliku psout.txt i zapisanie wyniku w pliku pssort.txt


<pre>
ps | sort > pssort.txt                     #  9
</pre>
  Sortowanie procesow i zapisanie do pliku pssort.txt

<pre>
cat lsout.txt | sort > lssort.txt          # 10
</pre>
Wypisanie pliku lsout.txt posortowanie i zapisanie do pliku lssort.txt
 
<pre>
who | sort | more                          # 11
</pre>
Posortowanie listy zalogowanych uzytkownikow ze stronami.
 
<pre>
who | sort | less                          # 12
</pre>
Posortowanie listy zalogowanych uzytkownikow ze stronami.






















