---
layout: post
title: Odpowiedzi laboratorium 5
---

# {{ page.title }}

## Zadanie 1
Znajdź w swoim katalogu domowym (bez podkatalogów) wszystkie pliki, które zostały zmodyfikowane w ciągu ostatnich dziesięciu dni i wyświetl ich nazwy.
<pre>
[mskorb@localhost]$ find ~/ -mtime -10 -maxdepth 1
</pre>

## Zadanie 2
Znajdź wszystkie pliki zwykłe w systemie, które mają w nazwie ciąg znaków „conf” i wyświetl ich nazwy na ekranie.
<pre>
[mskorb@localhost]$ find /-type f -name \*conf\*
</pre>

## Zadanie 3
Znajdź w swoim katalogu domowym wszystkie pliki, które nie były używane w ciągu ostatnich 20 dni.
<pre>
[mskorb@localhost]$ find ~/ -mtime -20 -type f
</pre>

## Zadanie 4
Znajdź w katalogu /etc wszystkie niepuste podkatalogi i pliki o nazwach zaczynających się na literę „a”.
<pre>
[mskorb@localhost]$ find /etc 
</pre>

## Zadanie 5
Z bieżącego katalogu usuń pliki, których nazwa zaczyna się na literę „x” i zawiera dokładnie trzy znaki
<pre>
[mskorb@localhost temp]$ touch xa1 xa2 xa3
[mskorb@localhost temp]$ touch xaa2 xaa3 xaa4
[mskorb@localhost temp]$ ls
xa1  xa2  xa3  xaa2  xaa3  xaa4
<strong>[mskorb@localhost temp]$ rm x??</strong>
[mskorb@localhost temp]$ ls
xaa2  xaa3  xaa4

</pre>

## Zadanie 6
<pre>
[mskorb@localhost sp]$ mkdir `date +%Y-%m-%d`
</pre>

## Zadanie dodatkowe
Eksportowanie manuala:
 - Metoda podana na zajeciach:
<pre>
[mskorb@localhost temp]  man find -t 
</pre>

