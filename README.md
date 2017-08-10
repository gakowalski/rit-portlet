# Portlet / widget RIT

## Wprowadzenie

Portlet RIT to gotowy fragment strony internetowej, który można wstawić do istniejącego serwisu, aby uzyskać działającą przeglądarkę obiektów turystycznych zgromadzonych w RIT. Obiekty mogą być ograniczone do wybranego województwa i/lub kategorii. Portlet powstał jako **tania i szybka alternatywa** lub też **rozwiązanie tymczasowe** wobec drogich prac integracyjnych łączących systemy informatyczne.

Użycie portletu ma m.in. następujące zalety:
* wdrożenie do istniejacego systemu CMS nie wymaga praktycznie żadnego budżetu i zabiera niewiele czasu;
* Internauci oprócz standardowych możliwości filtrowania otrzymują do dyspozycji wyszukiwarkę pełno-tekstową m.in. obsługującą odmiany wyrazów;
* ponieważ portlet bazuje na wewnętrznych aplikacjach RIT, dziedziczy on pewne wewnętrzne funkcjonalności jak wyszukiwanie obiektow w odległości od wskazanej miejscowości czy odnajdywanie trasy.

## Dostosowanie do potrzeb

Portlet domyślnie posiada pewien własny szablon graficzny wykonany w technologii CSS i pewien określony układ treści, przycisków i innych elementów strony. Jeżeli szablon lub układ nie będą spełniać potrzeb - np. będą znacząco się różnić od stylistyki serwisu, w którym portlet został umieszczony - wówczas możliwe jest dostosowanie go w pewnym zakresie. Dostosowanie jest możliwe w drodze zastosowania standardowych technologii webowych: CSS oraz ewentualnie JavaScript.

Ponadto, portlet jest zbudowany o [udokumentowane API REST](https://github.com/pot-gov-pl/rit-dokumentacja/blob/master/rest-v1.md), które można użyć do budowy własnego komponentu tego typu.

## Instrukcja techniczna instalacji i dostosowania stylu

[Link do instrukcji](setup.md).

## Licencja portletu i prawa dostępu do danych

* Kod źródłowy portletu jest jawny, ale nie jest dostępny do wykorzystania na zasadach wolnej licencji.
* Dane zgromadzone w systemie RIT pochodzą z wielu źródeł i są objęte swoimi własnymi ograniczeniami licencyjnymi - nie są to wiec dane otwarte.

W sprawie wykorzystania kodu lub danych prosimy o kontakt z Polską Organizacją Turystyczną celem wypracowania stosownych porozumień prawnych.
