---
layout: post
title: Czym są seria i ramka danych w Pandas?
categories: [pandas, dataseries,dataframe]
---

Tak jak obiecałem w  pierwszym wpisie, rozpoczniemy od podstaw Pandas-a. W tym poście omówię kluczowe koncepcje biblioteki Pandas wraz ze strukturami danych stanowiącymi podstawę pracy z danymi.
Ale zanim zaczniemy pozwolę sobie na kilka słów odnośnie początków tej biblioteki.

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

Gdzie pd to alias wykorzystywany później w kodzie w celu skrócenia wywołań funkcji zaimportowanej biblioteki. Kolejnym krokiem jest już sama praca z danymi. Ten krok omówię w kolejnym wpisie. 

### DataSeries

Seria najczęściej składa się z jednowymiarowej listy z kontekstem, lub stanowi pojedynczą kolumnę z DataFrame. Oczywiście dla mnie teoria musi być zawsze poparta praktyką, wtedy wszystko staje się bardziej zrozumiałe. Serie najłatwiej utworzyć wykorzystując do tego listę Pythona.


{% highlight c %}

data = [10,15,20,25,30]
ds = pd.Series(data)
print(ds)

{% endhighlight %}

Tym sposobem utworzona została DataSeries. Możemy to również szybko zweryfikować za pomocą funkcji type.

{% highlight c %}

print(type(ds))

{% endhighlight %}

Domyślny, unikalny indeks dodany został automatycznie (możemy go również utworzyć sami wykorzystując do tego parametr index w metodzie Series). DataSeries zawsze przechowuje dane tego samego typu. W powyższym przypadku jest to int64.
Ok, wiemy już jak tworzyć DataSeries, ale zasadniczym pytaniem, które pierwsze pojawiło się w mojej głowie gdy zaczynałem przygodę z DataSeries, było mainstreamowe : „A na co to komu? A komu to potrzebne?”, skoro w swojej dotychczasowej karierze nie spotkałem się jeszcze z jednokolumnowym zestawem danych. Po głębszym zrozumieniu ich roli przekonałem się, że ten element w analizę danych jest równie ważny, jak DataFrame.

Series wykorzystuje się podczas pracy z :

<strong> 1.jednowymiarowymi danymi </strong>
   
Czym właściwie są te jednowymiarowe dane?

Jednowymiarowe dane to dane, które są zorganizowane w jednym ciągu, a każdy element zawiera tylko jedną wartość. Wszystkie elementy są też tego samego typu (np. dane liczbowe). Przykładem będzie tu m.in. lista w Pythonie lub tablica biblioteki NumPy.
 
Załózmy, że w ciągu dnia odczytaliśmy 5 pomiarów temperatury i zapisaliśmy je jako lista liczb, bez podawania o której godzinie został wykonany dany pomiar.
{% highlight c %}

temperature = [21, 23, 20, 24, 26]

{% endhighlight %}

Wykonajmy teraz kilka operacji na naszej liście, aby zobaczyć możliwości DataSeries w praktyce.
Oczywiście pierwszym krokiem będzie przekształcenie listy na obiekt DataSeries.

{% highlight c %}

ds = pd.Series(temperature)

{% endhighlight %}

Każda temperatura ma teraz swój unikalny indeks umożliwiający dostęp do konkretnej wartości. 

{% highlight c %}

	0
0	21
1	23
2	20
3	24
4	26


{% endhighlight %}


Przykładowo ds[0] zwróci nam 21. Teraz gdy mamy już nasz obiekt Series ds sprawdźmy jaka była minimalna, maksymalna i średnia temperatura w naszym zbiorze danych. 

{% highlight c %}

print('Minimalna temperatura: ', ds.min())
print('Maksymalna temperatura:',ds.max())
print('Średnia temperatura:', ds.mean())


Minimalna temperatura: 20
Maksymalna temperatura: 26
Średnia temperatura: 22.8

{% endhighlight %}




