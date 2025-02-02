# ADR 2: Implementacja testów jednostkowych z wykorzystaniem biblioteki `phpunit`

## Decyzja
* Na środowiskach lokalnych będziemy uruchamiać testy dla przestrzeni app/code za pomocą polecenia

```./vendor/bin/phpunit --exclude-group ignore -c phpunit.xml.dist app/code/```

* Podczas deploymentu na środowiska dev i uat/stage będziemy uruchamiać testy dla przestrzeni app/code za pomocą 
polecenia

```./vendor/bin/phpunit --testdox --exclude-group ignore -c phpunit.xml.dist```

* Uruchomienie testów jednostkowych zostanie wywołane automatycznie przy próbie wykonania operacji `commit`
* W przypadku implementacji testów jednostkowych do wybranych modułów sklepu będziemy je dodawać do zakresu testów 
zdefiniowanego w pliku `./phpunit.xml.dist`

## Racjonalne uzasadnienie
Wdrożenie wykorzystania testów jednostkowych w celu podniesienia jakości tworzonego oprogramowania, zwiększenia 
stabilności wdrożeń produkcyjnych oraz zautomatyzowanie wykonywania testów w procesach nadzorujących jakość 
dostarczanego oprogramowania 

## Status
Zaproponowano

## Konsekwencje
* Podniesiona jakość dostarczanego oprogramowania
* Zwiększona pewność co do stabilności wdrożeń produkcyjnych
* W okresie przejściowym/wdrożeniowym dla zespołu możliwe wystąpienie wzrostu czasu wdrażania nowych funkcjonalności 
