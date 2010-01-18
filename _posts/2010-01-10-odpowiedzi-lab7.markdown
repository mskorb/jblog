---
layout: post
title: Odpowiedzi laboratorium 7 (skrypty)
---

# {{ page.title }}

## Zadanie 1
W bieżącym katalogu zamienić rozszerzenia wszystkich plików z rozszerzeniem htm na html.
 Jeżeli w nazwie pliku istnieje spacja, to należy zamienić ją na znak podkreślenia.

1 wersja
<pre>
#!/bin/bash

pliki=(`find \`pwd\` -iname "*.htm" `)
for file in ${pliki[*]}
do
    NowyPlik=`echo $file | tr " " "_"`
    mv "$file"  "$fileN"
done

</pre>



2 wersja (rename):<br>
<b>Użycie: ./nazwa.sh nazwa_pliku</b>
 
<pre>
#!/bin/bash
if [ "$1" == "" ]
then
  echo "Użycie skryptu $0 błędne. Prawdopodbnie nie podałes argumentu"
  exit 1
fi

arg=$@
  `rename ".htm" ".html" $arg`

if [ $? -eq 0 ]
then
    echo "Plik zostal zmieniony poprawnie"
fi
</pre>

</pre> 

## Zadanie 2
Napisać skrypt zawierający funkcję obliczającą silnię. Następnie należy obliczyć silnię
 z liczby, która jest argumentem skryptu. W przypadku niepoprawnego argumentu należy wypisać odpowiedni komunikat.
 <b>Użycie: ./nazwa.sh argument</b>
 
<pre>
#!/bin/bash
if [ "$1" == "" ]
then
  echo "Użycie skryptu $0 błędne. Prawdopodbnie nie podałes argumentu"
  exit 1
fi
silnia() {
  s=1
  N=$1
  while [ $N -ge 1 ]
  do
    s=$[$s * $N]
    N=$[$N - 1]
  done
  echo $s
}
  silnia $1
  sil='silnia $1'
  echo 'Silnia = ' $sil
</pre>

## Zadanie 3
Napisać skrypt zbierający jak najwięcej informacji o użytkowniku, którego login 
jest argumentem skryptu. Jeżeli skrypt nie ma argumentu, to należy użyć login osoby uruchamiającej skrypt.
 <b>Użycie: ./nazwa.sh argument</b>
<pre>
 #!/bin/bash
if [ "$1" == "" ]
then
  echo "Użycie skryptu $0 błędne. Prawdopodbnie nie podałes argumentu"
  exit 1
fi
  login=$1
  echo 'Witaj' $login
  echo 'Twoja statystyka: '
  echo 'Host: ' $HOSTNAME
  echo 'System: ' $OSTYPE
  echo 'Aktualny katalog: ' $PWD
  echo 'Katalog pocztowy: ' $MAIL
  echo 'Powloka: ' $SHELL
  echo 'UID: ' $UID
  echo 'Typ terminala: ' $TERM
  echo 'Architektury sprzętowa: ' $MACHTYPE
  echo 'Domyślny edytor: ' $EDITOR
  echo 'Zalogowano jako: ' $USER
</pre>

## Zadanie 4
Napisz skrypt usuwający z katalogu domowego i jego podkatalogów wszystkie pliki 
zwykłe o nazwie 'core' starsze niż 3 dni.

<pre>
#!/bin/bash

`find ~ -name "core" -ctime +3  -type f | xargs -I file rm "$file" `

echo "Pliki zstarsze niz 3 dni zostaly usuniete"

</pre>

## Zadanie 5 (Wlasny skrypt)
Program który wypisujący słowo podane w parametrze, obecny czas oraz nazwę użytkownika uruchamiającego skrypt

<pre>
#!/bin/bash
echo $1
date +%H:%M:%S
whoami 
</pre>
