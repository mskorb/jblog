---
layout: post
title: Odpowiedzi laboratorium 2

---

# {{ page.title }}

W katalogu c utwórz plik program.c zawierający co najmniej 10 linii kodu napisanego w języku C. (Sam kod należy wyszukać i pobrać z sieci.)
<pre>
[mskorb@sigma temp]$ cd nauka
[mskorb@sigma nauka]$ cd c
[mskorb@sigma c]$ nano program.c
[mskorb@sigma c]$ ls
program.c
</pre>


## Zadanie 1

Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)
<pre>
[mskorb@sigma c]$ cat program.c | grep . -m 2
\#include<stdio.h>
main()
</pre>
## Zadanie 2

Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)
<pre>
[mskorb@sigma c]$ tail program.c -n -4
        printf("\n");
        i=i+1;
        }
}

</pre>
## Zadanie 3

Wyświetl na ekran całą zawartość pliku program.c.
<pre>
[mskorb@sigma c]$ cat program.c
\#include<stdio.h>
main()
{
int j=0;
int i=0;
int t;

while(i<10)
        {
        while(j<10)
                {
                t=i*j;
                printf("%2i " ,t);
                j=j+1;
                }
        j=0;
        printf("\n");
        i=i+1;
        }
</pre>
## Zadanie 4

W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)
<pre>

[mskorb@sigma c]$ cat program.c | grep '\bmain\b'
main()

</pre>
## Zadanie 5

Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)
<pre>

[mskorb@sigma c]$ chmod u+rw program.c
[mskorb@sigma c]$ chmod g+r program.c
[mskorb@sigma c]$ chmod o-rwx program.c

</pre>
## Zadanie 6

Będąc w katalogu temp przenieś katalog wazne-sprawy do katalogu praca.
<pre>
[mskorb@sigma temp]$ mv dom/wazne-sprawy/ praca/
</pre>
## Zadanie 7
Zarchiwizuj cały katalog temp. (zip i tar)
<pre>
[mskorb@sigma ~]$ zip -r temp.zip temp
updating: temp/ (stored 0%)
  adding: temp/praca/ (stored 0%)
  adding: temp/praca/dokumenty/ (stored 0%)
  adding: temp/praca/dokumenty/xab (stored 0%)
  adding: temp/praca/dokumenty/xaa (stored 0%)
  adding: temp/praca/dokumenty/xac (stored 0%)
  adding: temp/praca/zlecenia/ (stored 0%)
  adding: temp/praca/zlecenia/niezrealizowane/ (stored 0%)
  adding: temp/praca/zlecenia/zrealizowane/ (stored 0%)
  adding: temp/praca/zlecenia/zrealizowane/xab (stored 0%)
  adding: temp/praca/zlecenia/zrealizowane/wykonano.txt (stored 0%)
  adding: temp/praca/zlecenia/zrealizowane/xaa (stored 0%)
  adding: temp/praca/zlecenia/zrealizowane/xac (stored 0%)
  adding: temp/praca/wazne-sprawy/ (stored 0%)
  adding: temp/praca/wazne-sprawy/odtworzono.txt (stored 0%)
  adding: temp/nauka/ (stored 0%)
  adding: temp/nauka/logo/ (stored 0%)
  adding: temp/nauka/c/ (stored 0%)
  adding: temp/nauka/c/program.c (deflated 25%)
  adding: temp/nauka/pascal/ (stored 0%)
  adding: temp/dom/ (stored 0%)
  adding: temp/dom/rachunki.txt (stored 0%)
  

[mskorb@sigma ~]$ tar -cf temp.tar temp
</pre>


## Zadanie 8

Usuń katalog temp.
<pre>
[mskorb@sigma ~]$ rm -r temp
</pre>
## Zadanie 9

Odtwórz z archiwum katalog temp. (unzip i tar)
<pre>
[mskorb@sigma ~]$ unzip temp.zip
Archive:  temp.zip
   creating: temp/
   creating: temp/praca/
   creating: temp/praca/dokumenty/
 extracting: temp/praca/dokumenty/xab
 extracting: temp/praca/dokumenty/xaa
 extracting: temp/praca/dokumenty/xac
   creating: temp/praca/zlecenia/
   creating: temp/praca/zlecenia/niezrealizowane/
   creating: temp/praca/zlecenia/zrealizowane/
 extracting: temp/praca/zlecenia/zrealizowane/xab
 extracting: temp/praca/zlecenia/zrealizowane/wykonano.txt
 extracting: temp/praca/zlecenia/zrealizowane/xaa
 extracting: temp/praca/zlecenia/zrealizowane/xac
   creating: temp/praca/wazne-sprawy/
 extracting: temp/praca/wazne-sprawy/odtworzono.txt
   creating: temp/nauka/
   creating: temp/nauka/logo/
   creating: temp/nauka/c/
  inflating: temp/nauka/c/program.c
   creating: temp/nauka/pascal/
   creating: temp/dom/
 extracting: temp/dom/rachunki.txt


[mskorb@sigma ~]$ rm -r  temp
[mskorb@sigma ~]$ tar xvf temp.tar
temp/
temp/praca/
temp/praca/dokumenty/
temp/praca/dokumenty/xab
temp/praca/dokumenty/xaa
temp/praca/dokumenty/xac
temp/praca/zlecenia/
temp/praca/zlecenia/niezrealizowane/
temp/praca/zlecenia/zrealizowane/
temp/praca/zlecenia/zrealizowane/xab
temp/praca/zlecenia/zrealizowane/wykonano.txt
temp/praca/zlecenia/zrealizowane/xaa
temp/praca/zlecenia/zrealizowane/xac
temp/praca/wazne-sprawy/
temp/praca/wazne-sprawy/odtworzono.txt
temp/nauka/
temp/nauka/logo/
temp/nauka/c/
temp/nauka/c/program.c
temp/nauka/pascal/
temp/dom/
temp/dom/rachunki.txt
</pre>

## Zadanie 10

Posprzątaj na swoim koncie.
<pre>
[mskorb@sigma ~]$ rm -r temp.zip
[mskorb@sigma ~]$ rm -r temp.tar
</pre>