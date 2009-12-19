---
layout: post
title: Odpowiedzi laboratorium 6
---

# {{ page.title }}

## Zadanie 1
W pliku „plik.txt” znajdź wiersze zawierające co najmniej jeden znak.
<pre>
[mskorb@sigma tmp] grep "[:alnum:]{1,}" plik.txt
</pre>

## Zadanie 2
Znajdź w plikach „pl*” wiersze rozpoczynające się od cyfry.
<pre>
[mskorb@sigma tmp] grep ^[0-9] pl*

</pre>

## Zadanie 3
Znajdź pliki, w których na 9 pozycji występuje litera „r”.
<pre>
[mskorb@sigma tmp] grep -E '^.{8}r.*'
</pre>

## Zadanie 4
Policz, ilu użytkowników systemu używa powłoki bash (zgodnie z zapisami w pliku /etc/passwd).
<pre> 
[mskorb@sigma tmp] grep -c bash /etc/passwd
</pre>

## Zadanie 5
Znajdź wiersze zawierające liczby rzymskie w pliku „plik.txt”.
<pre>
 [mskorb@sigma tmp] grep [IVXLCDM] plik.txt
</pre>