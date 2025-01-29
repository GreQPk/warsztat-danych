---
layout: post
title: Pandas:DataSeries vs DataFrame. Czym są seria i ramka danych w Pandas?
categories: [pandas, dataseries,dataframe]
---

Tak jak obiecałem w  pierwszym wpisie, rozpoczniemy od podstaw Pandas-a. W tym poście omówię kluczowe koncepcje biblioteki Pandas wraz ze strukturami danych stanowiącymi podstawę pracy z danymi.

###  Pandas, czyli potrzeba matką wynalazków

Historia biblioteki Pandas rozpoczyna się w 2008 roku, kiedy to Pan Wes McKinney – amerykański programista i analityk danych podczas pracy w firmie AQR Capital Management poszukując narzędzia, które ułatwi mu pracę z dużymi zestawami danych i komfortowe analizowanie finansowych szeregów czasowych stworzył projekt na bazie NumPy do pracy z danymi tabelarycznymi. 
Początkowo projekt ten wykorzystywał wewnątrz firmy, ale w 2010 roku zdecydował się udostępnić bibliotekę publicznie jako projekt open-source. 
Od tego momentu rozwój Pandas znacznie przyśpieszył. 
Pierwsze wersje biblioteki pozwalały na przeprowadzanie podstawowych operacji na tabelach danych (DataFrame) oraz na pracy z szeregami czasowymi (DataSeries). 
Pomimo, iż  Wes McKinney zrezygnował z aktywnego rozwoju projektu w 2013 roku, dzięki społeczności programistów z całego świata, dotychczas postało wiele wersji biblioteki, a sam Pandas został uznany za stabilne narzędzie produkcyjne. 
Łatwość użycia, integracja z ekosystemem Pythona i wszechstronność sprawia, że analiza danych to czysta przyjemność nawet dla początkujących adeptów analityki biznesowej.

Ciekawostka:
Nazwa Pandas wywodzi się od terminu Panel Data, który odnosi się do zestawów danych wielowymiarowych – to właśnie praca z tego typu danymi była pierwotnym celem powstania tej biblioteki.


### Zaczynamy!

Rozpoczęcie pracy z biblioteką Pandas wymaga tak naprawdę dwóch kluczowych elementów. Odpowiedniego środowiska do uruchamiania kodu oraz zaimportowania samej biblioteki.
Jako środowisko polecam Google Colab, ponieważ nie wymaga lokalnej instalacji, a wszystkie notatniki przechowywane są w chmurze Google wobec czego mamy szybki dostęp do naszych projektów z dowolnego miejsca. 
Import biblioteki Pandas wykonujemy za pomocą konwencji:

{% highlight c %}
import pandas as pd
{% endhighlight %}

Gdzie pd to alias wykorzystywany później w kodzie w celu skrócenia wywołań funkcji zaimportowanej biblioteki.
