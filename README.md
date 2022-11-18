# OpenAedMap.org
Software Design Document

Włodzimierz Bartczak (2022)
wersja 0.1

# 1.0 Wstęp
## 1.1 Cel

**NZK** do którego dochodzi poza szpitalem (OHCA - Out of Hospital Cardiac Arrest) jest trzecią najczęstszą przyczyną zgonów w Europie i stanowi istotny problem zdrowia publicznego na całym świecie. NZK w większości ma podłoże kardiologiczne (najczęściej zawał serca i inne ostre zespoły wieńcowe), ale także może być spowodowany przyczynami poza sercowymi (zatrzymanie oddechu, uraz wielonarządowy, wykrwawienie). W Polsce w 2018 roku 40,5% ogółu zgonów spowodowanych było chorobami układu krążenia, spośród których 59% stanowiły choroby serca, co jest znacznie częstsze niż w bogatszych krajach UE. Mimo wzrostu liczby zgonów w Polsce w 2020 roku z powodu pandemii SARS-CoV-2, których ogólna liczba jest najwyższa od kilkudziesięciu lat, ich główną przyczyną niezmiennie pozostają choroby układu krążenia (źródło danych: GUS, 2021 r.).

Cytując Wytyczne Europejskiej Rady Resuscytacji (ERC 2021), roczna częstotliwość występowania pozaszpitalnego zatrzymania krążenia (OHCA) w Europie wynosi 67-170 przypadków na 100 000 mieszkańców, gdzie dolną wartość występowania OHCA w Europie wyznaczyło badanie przeprowadzone w Polsce w Bielsku-Białej (nie ma w Polsce ogólnopolskiego rejestru NZK) opublikowane w Kardiologii Polskiej w 2016 roku. Przeżywalność w Europie po wystąpieniu OHCA do czasu wypisu ze szpitala wynosi średnio 8% i waha się w zakresie 0-18%. 

Przeżywalność po OHCA można znacznie zwiększyć, jeśli natychmiast podejmie się resuscytację oraz zostanie użyty automatyczny defibrylator zewnętrzny (AED - Automated External Defibrillator). Zastosowanie AED przez osoby bez przeszkolenia medycznego umożliwia podjęcie próby defibrylacji na klika minut przed przybyciem profesjonalnej  pomocy medycznej. Defibrylacja w ciągu 3-5 minut od OHCA może zapewnić przeżywalność na poziomie 50-70%. Każda minuta opóźnienia w wykonaniu defibrylacji zmniejsza  prawdopodobieństwo przeżycia do wypisu ze szpitala średnio o 3-5%, pod warunkiem prowadzenia resuscytacji. W przypadku jej braku prawdopodobieństwo przeżycia zmniejsza się o 10-12% na minutę opóźnienia defibrylacji.

Wśród wytycznych **ERC** znajdują się takie, które zalecają tworzenie map i jak najszersze udostępnianie informacji o lokalizacjach publicznie dostępnych defibrylatorów. Niestety większość dostępnych danych na temat lokalizacji AED jest tworzona w ramach projektów komercyjnych i dane zbierane przez te podmioty, nie są udostępnione szerokiemu odbiorcy, co znacznie utrudnia ich przetwarzanie i analizę przez niezależnych specjalistów.

**OSMP** jest twórcą oraz administratorem [mapy lokalizacji](https://aed.openstreetmap.org.pl) defibratorów na terenie Polski. Użytkownik ma możliwość pobierania aktualnych danych oraz po zalogowaniu możliwość ich dodawania i edycji na bieżąco w bazie OpenStreetMap. Obecnie pracujemy, by znacząco poszerzyć funkcjonalność naszego portalu oraz rozszerzyć jego zasięg z Polski na cały świat. Tym samym chcemy utworzyć pierwszą całkowicie darmową i kompleksową bazę lokalizacji urządzeń AED na świecie.

Nasze analizy wykazały, że wiele lokalizacji AED na terenie Europy jest dostępnych w bazie danych projektu OpenStreetMap, chcielibyśmy w prosty sposób te dane udostępnić. Jednocześnie, dzięki doświadczeniu zdobytemu we wcześniejszych projektach, umożliwić dodawanie oraz edycję informacji o tych urządzeniach jak największej grupie osób, niekoniecznie posiadających umiejętności cyfrowe niezbędne do takich zadań.

## 1.2 Zakres

Dokument obejmuje swoim zakresem utworzenie portalu [openaedmap.org](https://openaedmap.org), z interfejsem dostępnym w kilku językach, rozbudowaniu obecnej funkcjonalności o możliwość dodawania fotografii AED w celu ich weryfikacji oraz szybszego zlokalizowaniu ich w terenie. Umożliwi opracowanie mechanizmu pozwalającego pobierać dane AED dla poszczególnych krajów, nie tylko jak obecnie dla Polski. Wypracowanie modułów analitycznych pozwalających użytkownikom lepsze pozycjonowanie kolejnych urządzeń.

## 1.3 Słownik - definicje, akronimy i skróty.

- **AED** - Automated External Defibrillator, czyli automatyczny defibrylator zewnętrzny,
- **ERC** - European Resuscitation Council - Europejska Rada Resuscytacji,
- **JST** - Jednostka Samorządu Terytorialnego,
- **NZK** - nagłe zatrzymanie krążenia,
- **OSMP** - Stowarzyszenie OpenStreetMap Polska,
- **OSMF** - Fundacja OpenStreetMap z siedzibą w Londynie,
- **OSM** - OpenStreetMap,
- **UE** - Unia Europejska,
- **QA** - Quality Assurance - analiza i zapewnienie jakości.

# 2.0 Przegląd funkcjonalności
*Przegląd poszczególnych funkcjonalności portalu*
## 2.1 Moduł prezentacji danych
*Wersja beta już działa.*
## 2.2 Moduł dodawania / aktualizacji danych
*Wersja beta już działa.*

### 2.2.1 Wprowadzanie lokalizacji urządzenia
### 2.2.2 Wprowadzania fotografii urządzenia
### 2.2.3 Generowanie QR-kodów z lokalizacją najbliższego urządzenia.
*Generowanie kodu QR dla każdego urządzenia z jego lokalizacją. Pozwalający na pobranie takiego kodu w formie .svg lub .pdf.*
## 2.3 Moduł analizy danych
Moduł pozwalający generować podstawowe analizy dotyczące lokalizacji urządzeń AED.
### 2.3.1 Analiza rekomendowanych miejsc pod kątem umieszczenie stacjonarnych urządzeń.
*Moduł tworzący warstwę danych pokazującą obiekty, w których powinny znajdować się urządzenia AED zgodnie z listą obiektów rekomendowanych. Rekomendacje obejmują obiekty generujące ruch oraz odosobnione, które wymagają instalacji AED ze względu na czas potrzebny do zapewnienia pomocy medycznej.*
### 2.2.4 Pobieranie danych AED
* Dedykowana strona do pobierania danych z podziałem dla poszcególnych krajów
* Informacja o licencji ODbL podczas pobierania danych lokalizacji
* Podział na kraje


#### Lista obiektów rekomendowanych
>Listę trzeba przerobić na tabelę oraz dodać do niej tagi i typy obiektów

1. Stacje kolejowe.
2. Porty lotnicze.
3. Terminale autobusów dalekobieżnych.
4. Terminale portowe i promowe.
5. Miejsca odpoczynku na drogach ekspresowych (miejsca obsługi podróżnych) oraz przydrożne obiekty wypoczynkowe.
6. Galerie, parki i inne obiekty handlowe, w tym sklepy wielkopowierzchniowe i supermarkety.
7. Budynki użyteczności publicznej:
    1. ratusze, starostwa, urzędy wojewódzkie oraz ich filie,
    2. domy kultury,
    3. świetlice wiejskie i środowiskowe,
    4. biblioteki,
    5. komisariaty i posterunki policji oraz straży miejskiej,
    6. remizy strażackie,
    7. budynki i obiekty w zarządzie Lasów Państwowych,
    8. powiatowe i wojewódzkie stacje sanitarno-epidemiologiczne.
8. Domy pomocy społecznej, centra usług społecznych, zakłady aktywizacji zawodowej, placówki opiekuńcze dla osób starszych.
9. Placówki edukacyjne:
    1. przedszkola,
    2. szkoły podstawowe,
    3. szkoły średnie,
    4. uczelnie wyższe,
    5. pozostałe placówki edukacyjne.
10. Przedsiębiorstwa oraz fabryki i zakłady produkcyjne.
11. Obiekty rekreacyjne i sportowe:
    1. stadiony,
    2. siłownie,
    3. sale fitness,
    4. baseny pływackie,
    5. stacje narciarskie - w pobliżu wyciągów. 
12. Duże hotele, centra kongresowe oraz ośrodki wypoczynkowe.
13. Obiekty w odległych i słabo zaludnionych obszarach, takie jak:
    1. schroniska turystyczne,
    2. wyspy i obszary górskie.
## 2.4 Moduł raportów i statystyk
### 2.4.1 Statystyki liczby AED w rozbiciu na poszczególne kraje (tabela)
>Tabela w postaci linków do strony kraju z poszczególnymi statystykami
### 2.4.2 Lista edytorów TOP100
### 2.4.3 Statystyki dla kraju / jednostki administracyjnej
*Zebranie statystyk dla kraju w formie tabeli oraz wykresu w zależności od danych*
| Statystyka | Forma | Opis |
|:-----------|:------|:-----|
|TOP30 Edytorów | Tabela | linki do kont OSM |
|AED bez opisu | Wykres | Wykres pokazujący wszystkie AED do tych bez opisu lokalizacji w języku rodzimym |
|AED bez opisu | Tabela | Lista z linkami do poszczególnych urządzeń |
|AED bez *access* | Wykres | Wykres pokazujący wszystkie AED do tych bez oznaczenia dostępu w języku rodzimym |
|AED bez *access* | Tabela | Lista z linkami do poszczególnych urządzeń |
|AED bez *defibrillator:location:en* | Wykres | Wykres pokazujący wszystkie AED do tych bez opisu loklizacji w języku angielskim |
|AED bez *defibrillator:location:en* | Tabela | Lista z linkami do poszczególnych urządzeń |
## 2.5 Moduł QA
*Moduł generujący raport oraz prezentujący możliwe błędy lub braki w danych urządzeń AED i umożliwiający ich poprawienie*
### 2.5.1 AED bez tagu *defibrillator:location* i bez opisu
> Sprawdzanie czy istnieje opis w języku angielskim jako opcja - Przetłumacz?
### 2.5.2 AED oznaczone *fixme*
### 2.5.3 AED bez fotografii
### 2.5.4 AED bez *access=*
## 2.6 Dedykowany podkład mapowy
*Dedykowany podkład skupiający się na wyświetlaniu danych przydatnych ratownikom medycznym*
### 2.6.1 Lista obiektów do oznaczenia

| Kategoria | Obiekt |
|-----------|--------|
|Medyczne|Szpital|
|	Medyczne	|	SOR	|
|	Medyczne	|	Izba przyjęć	|
|	Medyczne	|	Oddział Szpitalny	|
|	Medyczne	|	Przychodnia	|
|	Medyczne	|	Apteka	|
|	Medyczne	|	Punkt krwiodawstwa	|
|	Medyczne	|	Punkt dializ	|
|	Medyczne	|	Dentysta	|
|	Medyczne	|	Hospicjum	|
|	Medyczne	|	Bank Krwi	|
|	Medyczne	|	Laboratorium	|
|	Medyczne	|	Punkt szczepień	|
|	Medyczne	|	Punkt pobrań laboratoryjnych	|
|	Medyczne	|	Punkt opatrunkowy	|
|	Medyczne	|	Apteczka	|
|	Medyczne	|	AED	|
|	Medyczne	|	Gabinet lekarski (ze wskazaniem specjalności)	|
|	Medyczne	|	Gabinet pielęgniarski	|
|	Medyczne	|	Stacja pogotowia ratunkowego	|
|	Medyczne	|	Baza HEMS (LPR w Polsce)	|
|	Medyczne	|	Lądowisko HEMS (aeroway=helipad)	|
|	Strażackie	|	Hydrant	|
|	Strażackie	|	Punkt poboru wody	|
|	Strażackie	|	Pikietaż dróg	|
|	Strażackie	|	Punkt lądowania śmigłowców (landing_site)	|
|	Strażackie	|	Drogi pożarowe	|
|	Strażackie	|	Przyłącze zasilania istalacji ppoż w budynku	|
|	Strażackie	|	Jednostka ratowniczo-gaśnicza	|
|	Strażackie	|	Remiza	|
|	Strażackie	|	Centrala alarmowa (np. niemieckie BMZ)	|
|	Strażackie	|	Gaśnica	|
|	Strażackie	|	Wąż strażacki	|
|	Policyjne	|	Komisariat	|
|	Policyjne	|	Posterunek policji wodnej	|
|	Policyjne	|	Straż miejska	|
|	Wodne	|	SAR	|
|	Wodne	|	Stacja ratownictwa wodnego	|
|	Wodne	|	Wieża ratownicza	|
|	Wodne	|	Koło ratunkowe	|
|	Inne	|	Stacja ratownictwa górskiego	|
|	Inne	|	Schronisko górskie	|

# 3.0 Przypadki zastosowania
## 3.1 Aktorzy
### 3.1.1 Wolontariusz dodający urządzenie
### 3.1.2 Pracownik JST
## 3.2 Interakcje
### 3.2.1 Dodanie AED
### 3.2.2 Edycja AED
### 3.2.3 Dodanie fotografii
### 3.3.4 Pobranie danych AED dla kraju / jednostki administracyjnej
### 3.3.5 Generowanie raportu dla kraju / jednostki administracyjnej
### 3.3.6 Korzystanie z warstwy QA
# 4.0 Przegląd Projektu
## 4.1 Architektura systemu
## 4.2 Baza danych
## 4.3 Interface użytkownika
# 5.0 Notatki robocze
## 5.1 Funkcjonalność

1. Automatyczne proponowanie tłumaczenia na język angielski.

## 5.2 Raporty

1. Trzeba będzie tworzyć raporty na poszczególne jednostki administracyjne.
