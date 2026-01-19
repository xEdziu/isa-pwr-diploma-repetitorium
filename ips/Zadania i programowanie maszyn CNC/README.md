# Wprowadzenie
**CNC (Computer Numerical Control)** = komputerowe sterowanie numeryczne obrabiarki. To maszyny, które wykonują obróbkę (najczęściej skrawaniem), a ruchy osi i funkcje technologiczne realizują na podstawie programu NC (alfanumerycznego).
## Najważniejsze zadania obrabiarek CNC:
- Wykonywanie detali o zadanym kształcie, wymiarach i jakości (np. chropowatości) – celem programowania jest uzyskanie przedmiotu o określonych parametrach.
- Automatyzacja i powtarzalność: ruch narzędzia po zaplanowanym torze, z zaprogramowanymi prędkościami/posuwami, z automatycznymi funkcjami (wrzeciono, chłodziwo, wymiana narzędzia).
- Bezpieczne i logiczne prowadzenie procesu dzięki układom współrzędnych, punktom odniesienia, korekcjom narzędzia i cyklom/podprogramom.

Przykłady maszyn CNC:
- tokarki CNC,
- frezarki CNC,
- centra obróbcze (3/4/5 osi),
- wiertarko-frezarki,
- grawerki,
- wycinarki (np. laser/plazma),
- szlifierki CNC
  
# Narzędzia
W maszynach CNC narzędzia są **wymienne**, montowane w oprawkach i identyfikowane w sterowaniu numerem `T` oraz korekcjami geometrycznymi. Każde narzędzie ma określone przeznaczenie technologiczne, inną charakterystykę pracy i różne wymiary. (prędkość posuwu, ilość ostrzy, twardość, powierzchnia robocza)
Najbardziej popularne narzędzia:
- `Frez` - narzędzie wieloostrzowe (najczęściej 2–6 ostrzy), pracujące ruchem obrotowym, skrawające bokiem, czołem lub jednocześnie bokiem i czołem. Służy do obróbki płaszczyzn, rowków, kieszeni i konturów.
- `Głowica frezarska` - frez o dużej średnicy z wymiennymi płytkami skrawającymi, zwykle z wieloma ostrzami rozmieszczonymi obwodowo. Pracuje głównie czołem i służy do planowania oraz obróbki zgrubnej dużych powierzchni.
- `Wiertło` - narzędzie dwuostrzowe, wykonujące ruch obrotowy i posuw osiowy, skrawające czołem. Służy do wykonywania otworów przelotowych i nieprzelotowych.
- `Nawiertak` - krótkie narzędzie wieloostrzowe (zwykle 2–4 ostrza), pracujące czołem, służące do wykonania stożkowego zagłębienia pod wiercenie. Zapewnia osiowość i zapobiega „uciekaniu” wiertła.
- `Gwintownik` - narzędzie wieloostrzowe, skrawające bokiem, przeznaczone do wykonywania gwintów wewnętrznych. Pracuje ruchem obrotowym zsynchronizowanym z posuwem osiowym.
- `Nóż tokarski` - narzędzie jednoostrzowe, w którym skrawanie odbywa się bokiem ostrza, a ruch główny wykonuje obracający się przedmiot. Służy do toczenia powierzchni zewnętrznych, wewnętrznych, czołowych oraz do przecinania.
- `Próbnik` - nie jest narzędziem skrawającym – posiada element stykowy, który wykrywa kontakt z detalem. Służy do pomiaru, bazowania detalu oraz ustalania punktu zerowego przedmiotu.
# Program NC
Program NC = alfanumeryczny plan pracy obrabiarki: informacje **geometryczne** (tor narzędzia) i **technologiczne** (narzędzie, prędkości, posuw).

Struktura
- program składa się z bloków, a blok ze słów (adres + wartość), np. `N20 G0 X100 Y100`.
- Przykładowe adresy:
- `G` – funkcje przygotowawcze (np. rodzaj ruchu, układ współrzędnych),
- `M` – funkcje pomocnicze/maszynowe,
- `S` / `F` – parametry technologiczne (obroty/prędkość skrawania i posuw),
- `T` / `D` – narzędzie i rejestr korekcji.

# Podstawy do programowania:
**Absolutnie vs przyrostowo**
- `G90` – absolutnie, `G91` – przyrostowo (modalne).
- `AC` – absolutnie, `IC` – przyrostowo (niemodalne).

**Interpolacje** (czyli „jakim torem jedzie narzędzie”)
- `G0` – interpolacja punktowa / ruch szybki (ustawczy), uwaga na kolizje.
- `G1` – interpolacja liniowa (robocza), wymaga posuwu `F`.
- `G2/G3` – interpolacja kołowa: zgodnie (`G2`) / przeciwnie (`G3`) do ruchu wskazówek. Definiujesz punkt końcowy + promień/środek (np. `I`,`J`,`K`) + kierunek.

**Układ przedmiotu (WKS)** i **przesunięcia zera**
- `G500` – wyłącza przesunięcia (programujesz względem maszynowego `M`),
- `G53` – przywołanie punktu maszynowego `M`,
- `G54…G57` – kolejne rejestry przesunięć punktu zerowego (typowo różne mocowania/detale).

**Parametry technologiczne** (sens, nie wzory)
- Posuwy: `G94` (mm/min), `G95` (mm/obr), plus tryby specjalne.
- Prędkości: `G96` stała prędkość skrawania (toczenie – sterowanie dobiera obroty zależnie od promienia), `G97` stałe obroty (frezowanie).

**Funkcje `M`** (najbardziej „życiowe”)
- `M0`/`M1` stop, `M2`/`M30` koniec programu,
- `M3`/`M4`/`M5` wrzeciono prawo/lewo/stop,
- `M6` wymiana narzędzia,
- `M7`/`M8`/`M9` chłodzenie/powietrze ON/OFF,
- `M17` koniec podprogramu.

# Korekcje narzędzia
Po co? Żeby utrzymać wymiary w tolerancji mimo różnic narzędzia i zużycia ostrza.

Rodzaje:
- korekcja **długości** (np. długość wiertła/frezu/noża),
- korekcja **promienia** (promień frezu lub promień naroża ostrza noża).

Korekcja promienia:
- `G41` lewostronna, `G42` prawostronna, `G40` wyłączenie. 

Zasady (ważne!):
- musi być znane narzędzie `T` i rejestr `D`, wybrana płaszczyzna (`G17`/`G18`/`G19`),
- w bloku z `G40`/`G41`/`G42` ma być `G0` lub `G1` i ruch w co najmniej jednej osi tej płaszczyzny,
- włączać przy najedzie na kontur, wyłączać przy wyjeździe; w środku programować ruchy tylko w płaszczyźnie.

# Podprogramy i cykle
## Podprogramy
- pliki (np. `SPF`), kończą się `M17` albo `RET` (`RET` pozwala uniknąć gwałtownego zwalniania na granicy bloków).
- mogą być powtarzane (parametr `P`) albo wywoływane modalnie przez `MCALL`.
## Cykle
- To „gotowe, sparametryzowane podprogramy” w sterowaniu do typowych zabiegów (np. wiercenie, gwintowanie, toczenie itd.). Są wspierane dialogowo i podzielone na grupy (np. wiercenia/frezowania/toczenia…).
- Wywołania mogą być pojedyncze albo modalne (`MCALL`), żeby wykonać cykl w wielu punktach.
