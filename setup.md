# Instalacja i zewnętrzne ostylowanie portletu RIT

## Instalacja portletu

Instalacja odbywa się poprzez zamieszczenie w kodzie strony znacznika:

```html
<div class="pot-content"></div>
```

Do którego zostanie załadowana zawartość portletu za pomocą skryptu inicjującego *widget-loader2.js*.

Skrypt inicjujący należy dodać do sekcji *<head>* w następującej postaci:

```html
<script
src=" http://rittest.poland.travel/informator-web/js/widget/widget-loader2.js"
mode="max" lang="en"
widgetBaseUrl=" http://rittest.poland.travel/informator-web" apiBaseUrl="http://rittest.poland.travel/informator-web">
</script>
```

Atrybuty:
* **widgetBaseUrl** wskazuje na serwer na którym jest osadzona Aplikacja Informator.
* **apiBaseUrl** wskazuje na serwer który dostarcza danych do portletu.

W szczególnym przypadku może to być ten sam URL.

UWAGA: Została zachowana zgodność wsteczna z poprzednią wersją skryptu inicjującego *widget-loader.js*.

Następnie należy załączyć ostylowanie wg wskazówek w sekcji „Zewnętrzne ostylowanie portletu RIT” oraz odpowiednio skonfigurować plik *widget-config.js* znajdujący się wewnątrz aplikacji *informator-web.war* na serwerze aplikacyjnym pod ścieżką *informator-web.war\js\widget\ widget-config.js*. W tym pliku wskazane są serwery odpowiedzialne za obsługę map, wyznaczanie tras oraz konfigurowalny komunikat o niedostępności API RIT.

## Obsługa stałych kryteriów wyszukiwania

Do portletu została dodana funkcjonalność obsługi stałych kryteriów wyszukiwania, które domyślnie zawężają wyniki wyszukiwania obiektów. Kryteria ustawia się w sekcji *script* tak jak wskazuje przykład:

```html
<script
src=" http://rittest.poland.travel/informator-web/js/widget/widget-loader2.js"
mode="max" lang="en"
region="mazowieckie"
categories="Agencja turystyczna,miasta"
widgetBaseUrl=" http://rittest.poland.travel/informator-web" apiBaseUrl="http://rittest.poland.travel/informator-web">
</script>
```

Atrybuty:
* *region* wskazuje województwo. Dopuszczalna jest pojedyncza wartość , wielkość liter bez znaczenia
* *categories* wskazuje ID kategorii obiektów. Możliwa jest lista kategorii po przecinku.

Uwagi:
*	Zastosowanie niewłaściwej bądź nieistniejącej kategorii sprawia, że nie trafia ona do filtra wyszukiwania;
*	Pominięcie parametru *categories* albo nie podanie w nim żadnej wartości sprawia, że filtr jest pusty, więc domyślnie wyszukiwane są wszystkie obiekty w każdej kategorii;
*	Lista kategorii zachowuje swoją hierarchiczność. Oznacza to, że zastosowanie kategorii wyższego rzędu, np. ROOT i jakiejkolwiek jego kategorii podrzędnej powoduje wyszukiwanie obiektów w kategorii ROOT.

## Konfiguracja informacji o niedostępności API RIT

Komunikat można konfigurować w następujący sposób:
* w pliku *widget-config.js* znajduje się treść komunikatu pod zmienną *InfWidget.API_NOT_RECHABLE*;
* w pliku *pot-widget.css* znajdują się następujące klasy styli: **.pot-widget-blankpage** – styl div’a wrapującego komunikat wewnątrz diva głównego (*.pot-content*); **.pot-widget-blankpage-content** – styl contentu (treści informacji) wewnątrz div’a *.pot-widget-blankpage*.

## Zewnętrzne ostylowanie portletu RIT.

W obecnym rozwiązaniu style CSS dotyczące portletu zostały przeniesione bezpośrednio na stronę, w której jest on osadzony, co umożliwia ich zewnętrzne zarządzanie. Głównym plikiem ze stylami jest *pot-widget.css*, w którym znajdują się dedykowane style dla Aplikacji RIT oraz nadpisywane style używanych w portlecie komponentów (*dynatree*, *choosen* i *jquery-ui*).

Pliki css należy załączyć w sekcji *<head>* w następujący sposób:

```html
<LINK href="custom-theme/jquery-ui-1.9.2.custom.css" rel="stylesheet" type="text/css">
<LINK href="dynatree/ui.dynatree.css" rel="stylesheet" type="text/css">
<LINK href="selectList/chosen.css" rel="stylesheet" type="text/css">
<LINK href="pot-widget.css" rel="stylesheet" type="text/css">
```

Należy dopilnować żeby *pot-widget.css* był załączony jako ostatni poniżej plików css ze stylami komponentowymi.

Główne selektory klas używane w portlecie:

Nazwa	| Opis
--- | ---
.pot-content |	Główny selektor wrappera portletu
.pot-sov-main |	Wrapper wyszukiwarki obiektów
.pot-nav, .pot-content-action |	Pasek nawigacji portletu
.pot-content-action-btn, |	Przycisk akcji nawigacji „wstecz”
.pot-content-header |	Nagłówek sekcji / nazwy ekranu
.ui-button |	Ogólny styl dla przycisków
.pot-red-button |	Przyciski wyróżnione (Wyszukaj, Wybierz kategorię..)
.pot-button |	Przyciski standardowe
.chzn-container chzn-container-single chzn-container-single-nosearch |	Style pól combo (wyszukiwanie kategorii obiektu..)
.ui-dialog |	Styl okna popup
.ui-dialog-titlebar, ui-widget-header |	Pasek tytułowy okna popup
.ui-dialog-content, .ui-widget-content |	Content okna popup
.ui-dialog-buttonpane |	Pasek dolny z przyciskami nawigacji w oknie popup
.pot-mini-header |	Styl nagłówka tabelki „mini dialog” np. z wyborem kategorii, mapką
.pot-mini-content-gray |	Styl zawartości tabelki „mini dialog” np. z wyborem kategorii, mapką
\#olv-data-table |	Ostylowanie wyników wyszukiwania
.dataTables_wrapper |	Wrapper tabelki z wynikami wyszukiwania
.olv-table-header |	Nagłówek tabeli z wynikami wyszukiwania
.pot-inv-gradient-bg |	Wiersz tabeli z wynikami wyszukiwania
.dataTables_paginate, .paging_full_numbers, .paginate_button  |	Wiersz z przyciskami stron wyników wyszukiwania
.dataTables_info |	Informacja o ilości wyszukanych obiektów
.pot-red |	Styl hiperłączy do wyświetlania detali obiektów
.ui-tabs-nav |	Zakładki detali obiektu
.ui-tabs-panel |	Panel detali obiektu
.dataTables_processing |	Informacja „trwa przetwarzanie”
.pot-widget-blankpage, .pot-widget-blankpage-content, |	Styl okna informującego o niedostępności API RIT

## Przykładowe osadzenie portretu na stronie

```html
<!DOCTYPE html>
<html lang="pl">
<head>
	<meta charset="utf-8">
	<title>Strona testowa</title>

   <script
        src=http://rittest.poland.travel/informator-web/js/widget/widget-loader2.js
        mode="max" lang="pl"
	 			region="mazowieckie"
	 			categories="82,83"
	 			widgetBaseUrl="http://rittest.poland.travel/informator-web"       
        apiBaseUrl="http://rittest.poland.travel/informator-web">
   </script>

   <LINK href="custom-theme/jquery-ui-1.9.2.custom.css" rel="stylesheet" type="text/css">
   <LINK href="dynatree/ui.dynatree.css" rel="stylesheet" type="text/css">
   <LINK href="selectList/chosen.css" rel="stylesheet" type="text/css">
   <LINK href="pot-widget.css" rel="stylesheet" type="text/css">
</head>
<body>
	<div class="pot-content"></div>
</body>
</html>
```

## Inne przykłady

* [Pełen portlet bez ograniczen](examples/example-1-default.html);
* [Portlet minimalny](examples/example-2-minified.html) - jako pojedyczne pole *input*, przykład dostosowania CSS-em;
* [Portlet z ograniczeniem do województwa](examples/example-3-preselected-region.html);
* [Potrlet z ograniczeniem do województwa i kategorii](examples/example-4-preselected-region-and-category.html).
