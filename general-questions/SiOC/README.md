<img width="1523" height="1142" alt="image" src="https://github.com/user-attachments/assets/aec00618-0cb9-4686-ae82-0da1a2d07da1" />


# Wprowadzenie
## Pojęcie sygnału
Sygnał to funkcja niosąca informację o pewnym zjawisku fizycznym. Najczęściej opisuje zależność pewnej wielkości fizycznej od czasu lub przestrzeni.
Przykłady sygnałów:
- sygnał dźwiękowy – zmiany ciśnienia powietrza w czasie
- sygnał elektryczny – napięcie lub prąd w funkcji czasu
- sygnał optyczny – natężenie światła
- obraz – sygnał dwuwymiarowy opisujący jasność (i kolor) w przestrzeni
## Rodzaje sygnałów ze względu na naturę
### Sygnały analogowe
- mają **ciągłą dziedzinę** (czas/przestrzeń)
- mają **ciągłą amplitudę**
- istnieją fizycznie w naturze
Przykłady:
- fala dźwiękowa
- światło padające na matrycę
- napięcie z mikrofonu
### Sygnały cyfrowe
- są dyskretne w czasie (lub przestrzeni)
- mają dyskretną amplitudę
- powstają w wyniku przetwarzania sygnałów analogowych
Sygnał cyfrowy nie istnieje w naturze — zawsze jest wynikiem: próbkowania + kwantyzacji
## Obraz jako sygnał
Obraz cyfrowy to szczególny przypadek sygnału:
- sygnał dwuwymiarowy (x, y)
- wartościami są:
- jasność (obraz w skali szarości)
- lub wektor koloru (np. RGB)
Matematycznie:
- obraz = funkcja f(x, y)
- w postaci cyfrowej: macierz wartości pikseli
## Źródła sygnałów i obrazów
Sygnały akustyczne
- mikrofony
- fale dźwiękowe
- zastosowania: audio, telefonia, rozpoznawanie mowy
Sygnały elektromagnetyczne
- światło widzialne (kamery)
- podczerwień
- fale radiowe
Obrazy cyfrowe
- kamery CMOS / CCD
- skanery
- systemy wizyjne
## Akwizycja sygnału – przejście analog → cyfrowy
Proces zamiany sygnału analogowego na cyfrowy składa się z dwóch niezależnych etapów:
### Próbkowanie
- dyskretyzacja dziedziny (czasu lub przestrzeni)
- wybieramy próbki sygnału w określonych odstępach
### Kwantyzacja
- dyskretyzacja amplitudy
- każda próbka jest zaokrąglana do jednego z dozwolonych poziomów
## Znaczenie cyfrowego przetwarzania sygnałów i obrazów
Cyfrowe przetwarzanie umożliwia:
- odporność na zakłócenia
- łatwą transmisję danych
- kompresję
- zaawansowane algorytmy analizy
- implementację programową (software)
Przykładowe zastosowania:
- kompresja audio i wideo
- systemy wizyjne
- analiza obrazów medycznych
- transmisja danych
- rozpoznawanie wzorców
# Próbkowanie i kwantyzacja sygnałów i obrazów
## Cel próbkowania i kwantyzacji
Sygnały występujące w naturze są analogowe – ciągłe w czasie (lub przestrzeni) i amplitudzie.
Aby możliwe było ich przetwarzanie w systemach cyfrowych (komputerach, mikrokontrolerach), konieczna jest ich dyskretyzacja.
Proces przejścia z postaci analogowej do cyfrowej obejmuje:
- próbkowanie – dyskretyzację dziedziny
- kwantyzację – dyskretyzację amplitudy
Są to dwa niezależne etapy, często mylone, ale konceptualnie różne.
## Próbkowanie sygnałów
### Definicja próbkowania
Próbkowanie polega na pobieraniu wartości sygnału analogowego w określonych odstępach czasu (lub przestrzeni).
Dla sygnału jednowymiarowego:
- sygnał ciągły:
- sygnał próbkowany:
gdzie:
- – okres próbkowania
- – częstotliwość próbkowania
### Próbkowanie obrazów
W przypadku obrazu:
- próbkowanie odbywa się w przestrzeni
- obraz ciągły → macierz pikseli
Częstotliwość próbkowania obrazu odpowiada:
- rozdzielczości przestrzennej (liczbie pikseli)
- gęstości próbek w poziomie i pionie
## Twierdzenie Shannona–Nyquista
### Treść twierdzenia
Aby możliwa była idealna rekonstrukcja sygnału ciągłego z próbek, częstotliwość próbkowania musi spełniać warunek:

gdzie:
- – najwyższa częstotliwość występująca w sygnale
### Znaczenie praktyczne
- częstotliwość nazywana jest częstotliwością Nyquista
- próbkowanie zbyt rzadkie prowadzi do aliasingu
- w praktyce stosuje się filtry antyaliasingowe przed próbkowaniem
## Aliasing
### Czym jest aliasing?
Aliasing to zjawisko, w którym:
- wysokie częstotliwości sygnału
- są błędnie interpretowane jako niższe
Powstaje, gdy:
Skutki aliasingu
- zniekształcenia sygnału
- artefakty w obrazie (np. mory, fałszywe wzory)
- nieodwracalna utrata informacji
## Kwantyzacja sygnałów
### Definicja kwantyzacji
Kwantyzacja polega na przypisaniu każdej próbce sygnału jednej z ograniczonej liczby wartości amplitudy.
- sygnał próbkowany ma nadal wartości rzeczywiste
- po kwantyzacji wartości są dyskretne
### Poziomy kwantyzacji
Liczba poziomów kwantyzacji zależy od:
- liczby bitów

Przykłady:
- 8 bitów → 256 poziomów
- 10 bitów → 1024 poziomy
- 16 bitów → 65536 poziomów
## Błąd kwantyzacji
### Charakter błędu
Błąd kwantyzacji:
- jest różnicą między wartością rzeczywistą a skwantyzowaną
- ma charakter szumu
- jest nieodwracalny
### Wpływ liczby bitów
- większa liczba bitów → mniejszy błąd kwantyzacji
- większy zakres dynamiki
- większy rozmiar danych
## Próbkowanie vs kwantyzacja – porównanie
## Znaczenie w przetwarzaniu obrazów i sygnałów
- próbkowanie decyduje o rozdzielczości
- kwantyzacja decyduje o dokładności amplitudy
- oba etapy wpływają na:
- jakość
- rozmiar danych
- dalsze przetwarzanie (filtracja, kompresja)
## Powiązanie z dalszymi rozdziałami
Ten rozdział jest fundamentem dla:
- interpolacji (rekonstrukcja sygnału)
- filtracji
- transformacji
- kompresji stratnej i bezstratnej
Bez poprawnego próbkowania nie ma sensu mówić o jakości obrazu ani dźwięku.
# Sygnały cyfrowe, kanał informacyjny i entropia
## Sygnał cyfrowy – ujęcie formalne
Sygnał cyfrowy to sygnał:
- dyskretny w dziedzinie (czas / przestrzeń),
- dyskretny w amplitudzie,
- opisany skończonym alfabetem symboli (np. {0,1}).
Najczęściej spotykana postać:
- ciąg bitów
- ciąg symboli binarnych lub wielowartościowych
Sygnał cyfrowy jest wygodny do przetwarzania, przechowywania i transmisji, ale wymaga odpowiedniego modelowania kanału.
## Kanał informacyjny
### Definicja kanału informacyjnego
Kanał informacyjny to medium, za pomocą którego przesyłana jest informacja od nadawcy do odbiorcy.
Kanał może być:
- fizyczny (przewód, światłowód)
- bezprzewodowy (fale radiowe)
- logiczny (kanał pamięci, plik)
### Właściwości kanału
Kanał informacyjny charakteryzuje się:
- przepustowością – maksymalną ilością informacji na jednostkę czasu
- opóźnieniem
- podatnością na zakłócenia
- prawdopodobieństwem błędu
## Zakłócenia i błędy transmisji
### Zakłócenia
Zakłócenia to wszelkie czynniki powodujące zmianę przesyłanego sygnału, np.:
- szum
- interferencje
- tłumienie
- zniekształcenia nieliniowe
### Błędy transmisji
W wyniku zakłóceń:
- bity mogą zostać zmienione (0 → 1 lub 1 → 0)
- symbole mogą zostać błędnie zinterpretowane
## Entropia informacji
### Pojęcie entropii
Entropia to miara:
- średniej ilości informacji
- niepewności źródła danych
Dla zmiennej losowej :

gdzie:
- – prawdopodobieństwo wystąpienia symbolu
### Interpretacja entropii
- wysoka entropia → dane „losowe”, trudne do kompresji
- niska entropia → dużo redundancji, dobra kompresja
## Entropia a kompresja
- entropia wyznacza dolne ograniczenie stopnia kompresji bezstratnej
- nie da się bezstratnie skompresować danych poniżej ich entropii
Przykład:
- ciąg pełen zer → bardzo niska entropia
- szum losowy → wysoka entropia
## Przepustowość kanału a ilość informacji
### Przepustowość
Przepustowość kanału to maksymalna ilość informacji, jaką można przesłać w jednostce czasu przy zadanym poziomie błędów.
Zależy od:
- pasma
- poziomu szumu
- zastosowanego kodowania
### Znaczenie praktyczne
- zbyt duża ilość danych → błędy lub opóźnienia
- kompresja i kodowanie umożliwiają efektywną transmisję
## Detekcja i korekcja błędów – idea
### Detekcja błędów
- pozwala stwierdzić, że błąd wystąpił
- przykład: bit parzystości
### Korekcja błędów
- pozwala wykryć i poprawić błędy
- przykład: kod Hamminga
# Szumy w sygnałach i obrazach cyfrowych
## Pojęcie szumu
Szum to niepożądana, losowa składowa sygnału, która:
- nie niesie informacji użytecznej,
- zniekształca sygnał właściwy,
- pogarsza jakość przetwarzania i analizy.
Szum:
- nie jest błędem algorytmu,
- jest naturalną konsekwencją fizycznych procesów pomiarowych.
## Źródła szumów
Szumy mogą pochodzić z:
- elementów elektronicznych (termiczne, wzmacniacze),
- kanału transmisyjnego,
- procesu akwizycji (szczególnie w obrazach),
- kwantyzacji.
## Szum w obrazach cyfrowych
### Jak „widzi” sensor obrazu
Sensor obrazu:
- nie mierzy „koloru” ani „jasności” bezpośrednio,
- zlicza fotony padające na element światłoczuły w danym czasie.
Proces zliczania fotonów ma charakter losowy, co prowadzi do szumu.
## Szum Poissona
### Model Poissona
Liczba fotonów docierających do sensora w danym czasie:
- jest zmienną losową,
- podlega rozkładowi Poissona.
Właściwości rozkładu Poissona:
- wartość oczekiwana:

- wariancja:

### Konsekwencje dla obrazu
- jasne obszary (duże ) → większy szum
- ciemne obszary → mniejszy szum
- szum zależy od sygnału
## Szum Gaussa – model obliczeniowy
### Dlaczego używa się modelu Gaussa
Wiele algorytmów przetwarzania:
- filtracja,
- estymacja,
- detekcja cech
zakłada, że szum:
- ma rozkład normalny,
- ma zerową wartość oczekiwaną,
- ma stałą wariancję.
### Problem
Szum Poissona:
- nie spełnia tych założeń,
- ma wariancję zależną od jasności.
Konieczna jest transformacja. (Walimy w deformacje na czy, czte, ry …. DEFORMACJAAAA!!!)
## Stabilizacja wariancji
### Cel stabilizacji wariancji
Celem jest:
- przekształcenie szumu Poissona
- w szum o charakterze zbliżonym do Gaussa
- ze stałą wariancją
Dzięki temu:
- klasyczne algorytmy filtracji działają poprawnie.
### Transformata Anscombe’a
Dla zmiennej losowej stosuje się transformację:

Po transformacji:
- rozkład ≈ Gaussowski,
- wariancja ≈ 1 (stała),
- niezależna od jasności obrazu.
### Znaczenie praktyczne
- szum staje się „jednakowy” w całym obrazie,
- możliwe jest skuteczne filtrowanie,
- poprawia się jakość estymacji.
## Inne rodzaje szumów (krótko)
- szum Gaussa (addytywny)
- szum impulsowy („sól i pieprz”)
- szum kwantyzacji
Każdy typ szumu wymaga innego podejścia filtracyjnego.
## Znaczenie modelowania szumu
Poprawne modelowanie szumu:
- pozwala dobrać właściwy filtr,
- zapobiega utracie szczegółów,
- poprawia jakość dalszego przetwarzania:
- filtracji,
- detekcji krawędzi,
- kompresji.
# Reprezentacja obrazu cyfrowego i kolor

## Obraz cyfrowy – przypomnienie
Obraz cyfrowy to:
- sygnał dwuwymiarowy,
- próbkowany w przestrzeni,
- skwantyzowany w amplitudzie.
Każdy piksel zawiera informację o:
- jasności (obraz w skali szarości),
- lub kolorze (obraz barwny).
## Reprezentacja koloru
### Model RGB
Najprostszy i najbardziej intuicyjny model barw to RGB:
- R – składowa czerwona
- G – składowa zielona
- B – składowa niebieska
Każdy piksel jest wektorem:

Cechy RGB:
- bezpośrednio związany z wyświetlaczami,
- prosty,
- nieoptymalny do kompresji.
## Percepcja wzrokowa człowieka
Ludzki wzrok:
- jest bardziej czuły na zmiany jasności,
- mniej czuły na zmiany koloru.
Oznacza to, że:
- szczegóły luminancji są kluczowe,
- informację o kolorze można zapisać „gorzej” bez dużej straty jakości postrzeganej.
## Model YCbCr
### Składowe YCbCr
Model YCbCr rozdziela:
- Y – luminancję (jasność),
- Cb, Cr – chrominancję (informację o kolorze).
Znaczenie:
- Y odpowiada za szczegóły obrazu,
- Cb/Cr odpowiadają za barwę.
### Transformacja RGB → YCbCr
Standardowa transformacja (np. JPEG):
Próbkowanie chrominancji (Chroma Subsampling)
### Idea chroma subsamplingu
Skoro:
- luminancja jest najważniejsza,
- chrominancja mniej istotna percepcyjnie,
to można:
- zachować pełną rozdzielczość Y,
- zmniejszyć rozdzielczość Cb i Cr.
To właśnie chroma subsampling.
### Notacja 4:X:Y
Notacja 4:X:Y opisuje:
- 4 – liczbę próbek luminancji w poziomie,
- X – liczbę próbek chrominancji w poziomie,
- Y – liczbę próbek chrominancji w pionie.
### Najczęściej spotykane schematy
4:4:4
- brak redukcji chrominancji,
- najwyższa jakość,
- duży rozmiar danych.
4:2:2
- połowa próbek chrominancji w poziomie,
- stosowane w wideo profesjonalnym.
4:2:0
- redukcja chrominancji w poziomie i pionie,
- bardzo popularne (JPEG, MPEG).
## Znaczenie YCbCr i chroma subsamplingu w kompresji
Dzięki:
- rozdzieleniu jasności i koloru,
- obniżeniu rozdzielczości chrominancji,
można:
- znacząco zmniejszyć ilość danych,
- bez zauważalnej utraty jakości wizualnej.
To:
- pierwszy krok kompresji stratnej,
- stosowany przed transformacją i kwantyzacją.
## Konsekwencje i ograniczenia
- nadmierny chroma subsampling → artefakty kolorystyczne,
- tekst i grafika wektorowa są bardziej wrażliwe niż zdjęcia,
- dlatego różne zastosowania → różne schematy próbkowania.
# Interpolacja i aproksymacja sygnałów i obrazów
## Dlaczego potrzebujemy interpolacji i aproksymacji?
Sygnały i obrazy cyfrowe:
- są dyskretne,
- opisane tylko w punktach próbkowania.
Wiele operacji (skalowanie, obrót, rekonstrukcja, estymacja):
- wygodniej wykonać w postaci ciągłej.
Stąd potrzeba:
- interpolacji – dokładne przejście przez próbki,
- aproksymacji – przybliżone odwzorowanie sygnału.
## Interpolacja – idea
Interpolacja polega na:
- wyznaczeniu wartości sygnału w punktach pośrednich,
- przy dokładnym przechodzeniu przez znane próbki.
Formalnie:
- dane:
- wynik: funkcja ciągła
warunek:

## Interpolacja a twierdzenie Shannona
Zgodnie z twierdzeniem Shannona:
- idealna rekonstrukcja sygnału jest możliwa,
- jeśli spełniony jest warunek Nyquista.
Idealna funkcja interpolująca:
Praktyczne metody interpolacji
Najbliższego sąsiada (Nearest Neighbor)
- bierze wartość najbliższej próbki
- bardzo szybka
- powoduje „schodki” i pikselizację
Zastosowanie: gdy liczy się szybkość, nie jakość.
### Interpolacja liniowa / biliniowa
- 1D: interpolacja liniowa
- 2D (obrazy): biliniowa
- kompromis: jakość vs złożoność
Efekt: wygładzenie, ale rozmycie krawędzi.
### Interpolacja sześcienna / bikubiczna
- wykorzystuje więcej sąsiednich próbek
- lepsze zachowanie krawędzi
- większa złożoność obliczeniowa
Często domyślna w edytorach graficznych.
## Zastosowania interpolacji
- skalowanie obrazów
- obrót obrazów
- zmiana rozdzielczości
- rekonstrukcja sygnałów
## Aproksymacja – idea
Aproksymacja polega na:
- przybliżeniu sygnału funkcją,
- niekoniecznie przechodzącą dokładnie przez próbki.
Różnica kluczowa:
- interpolacja → dokładność w punktach
- aproksymacja → minimalizacja błędu globalnego
## Aproksymacja za pomocą baz ortogonalnych
Sygnał można zapisać jako:

gdzie:
- – funkcje bazowe,
- – współczynniki.
Przykładowe bazy:
- Fouriera (sinusy i cosinusy)
- kosinusowa (DCT)
- falkowa (wavelety)
To jest bezpośrednie przejście do transformacji.
## Aproksymacja a redukcja szumu
- szum → zwykle wysokie częstotliwości
- aproksymacja z ograniczoną liczbą współczynników:
- usuwa szum
- zachowuje strukturę sygnału
aproksymacja = estymacja sygnału
## Interpolacja vs aproksymacja (MUST KNOW)
## Znaczenie w przetwarzaniu obrazów i sygnałów
- interpolacja → operacje geometryczne
- aproksymacja → filtracja, kompresja, transformacje
- oba podejścia:
- opierają się na próbkach,
- zależą od jakości próbkowania
## Powiązanie z kolejnym rozdziałem
Aproksymacja prowadzi bezpośrednio do:
- transformat ortogonalnych:
- FFT
- DCT
- FWT
- kompresji danych
# Filtracja sygnałów i obrazów cyfrowych
## Cel filtracji
Filtracja to proces przekształcania sygnału lub obrazu w celu:
- redukcji szumu,
- wygładzenia,
- uwydatnienia cech (krawędzie, detale),
- poprawy jakości do dalszego przetwarzania.
Filtracja zawsze jest kompromisem między:
- redukcją zakłóceń,
- zachowaniem szczegółów.
## Filtry liniowe – splot (konwolucja)
### Idea splotu
Filtr liniowy działa poprzez splot sygnału z maską (jądrem).
Dla sygnału 1D:

Dla obrazu 2D:
- jądro (np. 3×3) jest przesuwane po obrazie,
- wynik piksela to suma ważona sąsiedztwa.
### Właściwości filtrów splotowych
- liniowe
- stacjonarne
- łatwe do analizy matematycznej
- wrażliwe na wartości odstające (szum impulsowy)
### Przykłady filtrów splotowych
- filtr uśredniający (wygładzający)
- filtr Gaussa
- filtry detekcji krawędzi (Sobel, Prewitt – ideowo)
## Filtry medianowe (nieliniowe)
### Idea filtru medianowego
Filtr medianowy:
- nie wykonuje splotu,
- zastępuje wartość piksela medianą z sąsiedztwa.

### Właściwości
- nieliniowy
- bardzo skuteczny w usuwaniu:
- szumu impulsowego („sól i pieprz”)
- lepiej zachowuje krawędzie niż filtry liniowe
## Filtry adaptacyjne – filtr bilateralny
### Idea filtru bilateralnego
Filtr bilateralny:
- jest rozszerzeniem filtru splotowego,
- uwzględnia:
- odległość przestrzenną,
- podobieństwo wartości pikseli.

### Zalety
- redukuje szum,
- zachowuje ostre krawędzie,
- adaptuje się do lokalnej struktury obrazu.
### Wady
- wysoka złożoność obliczeniowa,
- wolniejszy od filtrów klasycznych.
## Filtracja a rodzaj szumu
## Filtracja a aproksymacja
- filtracja splotowa → lokalna operacja
- aproksymacja → globalne przybliżenie
- oba podejścia:
- redukują szum,
- działają na różnych zasadach
## Znaczenie filtracji w przetwarzaniu obrazów
Filtracja jest:
- etapem wstępnym przed:
- detekcją krawędzi,
- segmentacją,
- kompresją,
- krytyczna dla jakości dalszych algorytmów.
# Transformaty w przetwarzaniu sygnałów i obrazów
## Dlaczego stosujemy transformaty?
Sygnał lub obraz w dziedzinie:
- czasu / przestrzeni → trudny do analizy,
- częstotliwości / skali → łatwiejszy do:
- filtracji,
- kompresji,
- redukcji szumu.
Transformata zmienia sposób opisu sygnału, a nie samą informację.
## Idea transformacji ortogonalnej
Transformata polega na:
- przedstawieniu sygnału jako sumy funkcji bazowych,
- wyznaczeniu współczynników opisujących „udział” każdej bazy.
Ogólnie:

gdzie:
- – funkcje bazowe,
- – współczynniki.
## Transformata Fouriera (FT)
### Sens fizyczny
Transformata Fouriera:
- rozkłada sygnał na składowe częstotliwościowe,
- mówi jakie częstotliwości są obecne w sygnale.
amplituda → „ile danej częstotliwości”.
### FFT – szybka transformata Fouriera
- FFT = algorytm obliczania FT
- redukcja złożoności:
z do
### Zastosowania FFT
- analiza widmowa sygnałów
- filtracja w dziedzinie częstotliwości
- kompresja sygnałów okresowych
## Transformata kosinusowa (DCT)
### Idea DCT
- wykorzystuje tylko cosinusy,
- bardzo dobra do sygnałów rzeczywistych,
- silnie skupia energię w kilku współczynnikach.
kluczowa cecha: kompaktowa reprezentacja.
### DCT w kompresji obrazu
- stosowana blokowo (np. 8×8),
- niskie częstotliwości → istotne,
- wysokie → często zerowane.
## Transformata falkowa (FWT)
### Idea falki
- analiza sygnału w:
- czasie i częstotliwości,
- lokalna analiza (w przeciwieństwie do FT).
### Właściwości FWT
- dobra do sygnałów nieustacjonarnych,
- wielorozdzielcza analiza,
- pozwala zachować detale i krawędzie.
## Porównanie transformacji (MUST KNOW)
## Transformacje a redukcja szumu
- szum → głównie wysokie częstotliwości,
- po transformacji:
- można je progować,
- lub usuwać selektywnie.
filtracja w dziedzinie transformacji = skuteczniejsza.
## Rola transformacji w kompresji
Pipeline kompresji:
- transformacja (FFT / DCT / FWT)
- progowanie
- kwantyzacja
- kodowanie entropijne
bez transformacji kompresja stratna nie działa efektywnie.
# Kompresja danych cyfrowych (bezstratna i stratna)
## Cel kompresji
Kompresja to proces zmniejszania ilości danych potrzebnych do reprezentacji sygnału lub obrazu.
Cele:
- zmniejszenie rozmiaru pliku,
- efektywniejsza transmisja,
- lepsze wykorzystanie przepustowości kanału.
Kompresja nie tworzy informacji, tylko usuwa redundancję.
## Rodzaje redundancji
- statystyczna – niektóre symbole występują częściej,
- przestrzenna / czasowa – sąsiednie próbki są podobne,
- percepcyjna – informacje mało istotne dla człowieka.
Kompresja wykorzystuje entropię źródła.
## Kompresja bezstratna
### Definicja
Kompresja bezstratna:
- pozwala idealnie odtworzyć dane po dekompresji,
- nie powoduje utraty informacji.
### Kodowanie entropijne
RLE (Run-Length Encoding)
- zapis sekwencji powtórzeń: (liczba, wartość)
- skuteczny dla danych z dużą liczbą zer.
Kodowanie Huffmana
- krótsze kody dla częstszych symboli,
- dłuższe dla rzadszych.
Kodowanie arytmetyczne / ANS
- koduje cały strumień jako jedną liczbę,
- bardzo wysoka efektywność.
## Kompresja stratna
### Definicja
Kompresja stratna:
- nie pozwala na idealne odtworzenie danych,
- usuwa informacje mało istotne percepcyjnie.
### Pipeline kompresji stratnej (klasyk)
- Transformacja (DCT / FWT)
- Progowanie – usuwanie małych współczynników
- Kwantyzacja – etap nieodwracalny
- Kodowanie entropijne (bezstratne)
Największa strata informacji = kwantyzacja.
## Kwantyzacja w kompresji stratnej (np. JPEG)
- współczynniki transformacji są dzielone przez wartości progowe,
- mniej istotne (wysokie częstotliwości) → silniej kwantyzowane,
- często zerowane.
## JPEG – przykład kompresji obrazu
Pipeline JPEG:
- RGB → YCbCr
- Chroma subsampling (np. 4:2:0)
- DCT (bloki 8×8)
- Kwantyzacja
- Zig-zag + RLE
- Huffman
## Kompresja audio i wideo (idea)
- usuwanie częstotliwości niesłyszalnych / niewidocznych,
- wykorzystanie maskowania percepcyjnego,
- podobna idea jak w JPEG, ale w czasie.
Przykłady:
- MP3 – audio
- MPEG – wideo
## Porównanie: bezstratna vs stratna (MUST KNOW)
# Zastosowania algorytmów przetwarzania sygnałów i obrazów
## Pipeline przetwarzania obrazu (schemat ogólny)
Typowy ciąg operacji:
- Akwizycja obrazu
- próbkowanie
- kwantyzacja
- obecność szumu
- Wstępne przetwarzanie
- stabilizacja wariancji
- filtracja
- Analiza
- detekcja cech
- estymacja
- Transformacje i kompresja
- DCT / FWT
- kwantyzacja
- kodowanie
Ten schemat można „przyłożyć” do niemal każdego systemu wizyjnego.
## Autofocus – klasyczne zastosowanie
### Idea autofokusu
Autofokus polega na:
- automatycznym ustawieniu ostrości,
- maksymalizacji „ostrości” obrazu.
### Autofokus oparty na kontraście
Zasada:
- obraz ostry → wysoka zawartość wysokich częstotliwości
- obraz rozmyty → dominacja niskich częstotliwości
Realizacja:
- filtracja (np. Laplace, Sobel),
- miara ostrości:
- wariancja,
- suma wartości bezwzględnych gradientu.
Maksimum miary = najlepsza ostrość.
### Autofokus z detekcją fazy (idea)
- analiza przesunięcia obrazów,
- szybszy od kontrastowego,
- wymaga dodatkowych elementów sprzętowych.
## Detekcja cech w obrazie
### Czym są cechy?
Cechy to:
- krawędzie,
- narożniki,
- tekstury,
- obiekty.
Są one podstawą:
- rozpoznawania obiektów,
- śledzenia,
- analizy obrazu.
## Detekcja krawędzi (idea)
- krawędzie = miejsca dużej zmiany jasności,
- wykrywane przez:
- filtry gradientowe,
- filtry splotowe.
Detekcja krawędzi zawsze wymaga wcześniejszej filtracji.
## Redukcja szumu jako element estymacji
- szum pogarsza detekcję i pomiary,
- filtracja:
- poprawia estymację,
- zmniejsza fałszywe detekcje.
## Zastosowania kompresji w praktyce
- transmisja wideo (kamery, monitoring),
- archiwizacja danych,
- systemy wbudowane (ograniczone zasoby).
Pipeline:
- filtracja → transformacja → kwantyzacja → kodowanie.
## Przykład odpowiedzi przekrojowej (GOLD)
Jeśli komisja zapyta:
„Jak wykorzystałby Pan/Pani przetwarzanie obrazu w praktyce?”
Modelowa odpowiedź:
„Obraz jest próbkowany i kwantyzowany, następnie poddany filtracji w celu redukcji szumu. Po stabilizacji sygnału można wykrywać cechy, np. krawędzie, a do przechowywania lub transmisji stosuje się transformacje i kompresję stratną.”

# Możliwe pytania:
## Wprowadzenie:
- Czym jest sygnał?
Podaj definicję oraz przykłady sygnałów spotykanych w technice.
- Jakie są podstawowe rodzaje sygnałów ze względu na postać?
Omów różnice między sygnałem analogowym a cyfrowym.
- Czy sygnał cyfrowy istnieje w naturze?
Uzasadnij odpowiedź.
- Jakie etapy obejmuje proces zamiany sygnału analogowego na cyfrowy?
Krótko scharakteryzuj każdy z nich.
- Czym różni się próbkowanie od kwantyzacji?
(To bardzo klasyczne pytanie egzaminacyjne.)
- Czym jest obraz cyfrowy z punktu widzenia teorii sygnałów?
Jak można go opisać matematycznie?
- Jakie są przykłady źródeł sygnałów akustycznych i elektromagnetycznych?
- Na czym polega akwizycja obrazu w kamerze cyfrowej?
Co jest fizycznie mierzone?
- Dlaczego cyfrowe przetwarzanie sygnałów jest powszechnie stosowane?
Wymień jego główne zalety.
- Podaj przykładowe zastosowania cyfrowego przetwarzania sygnałów i obrazów.
## Próbkowanie i kwantyzacja sygnałów i obrazów
- Na czym polega próbkowanie sygnału?
Próbkowanie polega na pobieraniu wartości sygnału analogowego w dyskretnych momentach czasu lub punktach przestrzeni, co prowadzi do dyskretyzacji dziedziny sygnału.
- Czym jest częstotliwość próbkowania?
Częstotliwość próbkowania to liczba próbek pobieranych w jednostce czasu. Jest równa odwrotności okresu próbkowania i decyduje o poprawności odwzorowania sygnału.
- Na czym polega próbkowanie obrazu cyfrowego?
Próbkowanie obrazu polega na dyskretyzacji przestrzeni, czyli podziale obrazu ciągłego na siatkę pikseli, z których każdy reprezentuje wartość jasności lub koloru w danym punkcie.
- Co mówi twierdzenie Shannona–Nyquista?
Twierdzenie Shannona–Nyquista mówi, że aby możliwa była idealna rekonstrukcja sygnału, częstotliwość próbkowania musi być co najmniej dwukrotnie większa od najwyższej częstotliwości występującej w sygnale.
- Czym jest częstotliwość Nyquista?
Częstotliwość Nyquista to połowa częstotliwości próbkowania i jednocześnie minimalna częstotliwość graniczna, powyżej której składowe sygnału nie mogą być poprawnie odwzorowane.
- Co to jest aliasing?
Aliasing to zjawisko polegające na błędnym odwzorowaniu wysokich częstotliwości sygnału jako niższych, powstające w wyniku zbyt niskiej częstotliwości próbkowania.
- Czy aliasing można usunąć po próbkowaniu?
Nie, aliasing jest zjawiskiem nieodwracalnym i nie może zostać usunięty po próbkowaniu. Można mu zapobiec jedynie przez odpowiednie filtrowanie antyaliasingowe przed próbkowaniem.
- Na czym polega kwantyzacja sygnału?
Kwantyzacja polega na przypisaniu każdej próbce sygnału jednej z ograniczonej liczby poziomów amplitudy, co prowadzi do dyskretyzacji wartości sygnału.
- Od czego zależy liczba poziomów kwantyzacji?
Liczba poziomów kwantyzacji zależy od liczby bitów użytych do zapisu próbki i jest równa , gdzie B to liczba bitów.
- Czym jest błąd kwantyzacji?
Błąd kwantyzacji to różnica między rzeczywistą wartością próbki a jej skwantyzowaną reprezentacją. Ma on charakter szumu i jest nieodwracalny.
- Jak zwiększenie liczby bitów wpływa na jakość sygnału?
Zwiększenie liczby bitów zmniejsza błąd kwantyzacji i poprawia dokładność odwzorowania amplitudy, ale jednocześnie zwiększa ilość danych.
- Czym różni się próbkowanie od kwantyzacji?
Próbkowanie dyskretyzuje dziedzinę sygnału (czas lub przestrzeń), natomiast kwantyzacja dyskretyzuje amplitudę. Próbkowanie może być odwracalne, a kwantyzacja jest procesem nieodwracalnym.
- Jakie są konsekwencje zbyt rzadkiego próbkowania obrazu?
Zbyt rzadkie próbkowanie obrazu prowadzi do aliasingu przestrzennego, objawiającego się artefaktami takimi jak mory lub fałszywe wzory.
- Dlaczego próbkowanie i kwantyzacja są kluczowe dla dalszego przetwarzania?
Ponieważ decydują o jakości, rozdzielczości i dokładności danych wejściowych, a błędy popełnione na tym etapie są przenoszone i często wzmacniane przez kolejne algorytmy przetwarzania.
## Sygnały cyfrowe, kanał informacyjny i entropia
- Czym jest sygnał cyfrowy?
Sygnał cyfrowy to sygnał dyskretny zarówno w dziedzinie, jak i amplitudzie, opisany skończonym alfabetem symboli, najczęściej binarnym.
- Dlaczego sygnały cyfrowe są powszechnie stosowane w transmisji danych?
Ponieważ są odporne na niewielkie zakłócenia, łatwe do przetwarzania, przechowywania i umożliwiają stosowanie algorytmów detekcji oraz korekcji błędów.
- Czym jest kanał informacyjny?
Kanał informacyjny to medium, za pomocą którego przesyłana jest informacja od nadawcy do odbiorcy, obejmujące zarówno aspekty fizyczne, jak i logiczne transmisji.
- Jakie są podstawowe właściwości kanału informacyjnego?
Kanał informacyjny charakteryzuje się przepustowością, opóźnieniem, podatnością na zakłócenia oraz prawdopodobieństwem błędów transmisji.
- Czym są zakłócenia w kanale transmisyjnym?
Zakłócenia to czynniki powodujące zniekształcenie sygnału podczas transmisji, takie jak szum, interferencje, tłumienie czy nieliniowości kanału.
- Czym różnią się zakłócenia od błędów transmisji?
Zakłócenia są przyczyną fizyczną, natomiast błędy transmisji są ich skutkiem, polegającym na błędnej interpretacji przesyłanych symboli lub bitów.
- Czym jest entropia informacji?
Entropia informacji to miara średniej ilości informacji lub niepewności źródła danych, wyrażona jako wartość oczekiwana informacji niesionej przez symbole.
- Jak interpretować wartość entropii?
Wysoka entropia oznacza dane losowe i trudne do kompresji, natomiast niska entropia wskazuje na dużą redundancję i możliwość skutecznej kompresji.
- Jaki jest związek między entropią a kompresją danych?
Entropia wyznacza dolną granicę kompresji bezstratnej – nie da się bezstratnie skompresować danych poniżej ich entropii.
- Czy dane o wysokiej entropii można skompresować?
Dane o wysokiej entropii są bardzo trudne lub praktycznie niemożliwe do skutecznej kompresji bezstratnej, ponieważ zawierają mało redundancji.
- Czym jest przepustowość kanału?
Przepustowość kanału to maksymalna ilość informacji, jaką można przesłać w jednostce czasu przy akceptowalnym poziomie błędów.
- Dlaczego stosuje się kompresję przed transmisją danych?
Aby zmniejszyć ilość przesyłanych danych, lepiej wykorzystać przepustowość kanału i ograniczyć liczbę błędów transmisji.
- Na czym polega detekcja błędów?
Detekcja błędów polega na wykrywaniu, czy w trakcie transmisji wystąpił błąd, bez konieczności jego poprawiania.
- Na czym polega korekcja błędów?
Korekcja błędów polega na wykrywaniu i automatycznym poprawianiu błędów transmisji bez potrzeby ponownego przesyłania danych.
- Dlaczego sygnał cyfrowy nie gwarantuje transmisji bezbłędnej?
Ponieważ kanał transmisyjny zawsze jest obarczony zakłóceniami, a sygnał cyfrowy jedynie ułatwia wykrywanie i korekcję błędów, ale nie eliminuje ich całkowicie.
## Szumy w sygnałach i obrazach cyfrowych
- Czym jest szum w sygnale lub obrazie?
Szum to losowa, niepożądana składowa sygnału, która nie niesie informacji użytecznej i zniekształca sygnał właściwy.
- Czy szum jest błędem algorytmu przetwarzania?
Nie, szum jest naturalną konsekwencją fizycznych procesów pomiarowych i transmisyjnych, a nie błędem algorytmu.
- Jakie są główne źródła szumu w systemach cyfrowych?
Główne źródła szumu to elementy elektroniczne, kanał transmisyjny, proces akwizycji sygnału oraz kwantyzacja.
- Na czym polega proces akwizycji obrazu w sensorze?
Akwizycja obrazu polega na zliczaniu fotonów padających na element światłoczuły sensora w określonym czasie ekspozycji.
- Jaki rozkład statystyczny opisuje szum w procesie zliczania fotonów?
Proces zliczania fotonów jest opisywany rozkładem Poissona.
- Jakie są podstawowe własności rozkładu Poissona?
W rozkładzie Poissona wartość oczekiwana jest równa wariancji i obie są równe parametrowi λ.
- Jak szum Poissona zależy od jasności obrazu?
Im jaśniejszy obszar obrazu, tym większa liczba zliczonych fotonów i tym samym większa wariancja szumu.
- Dlaczego szum Poissona jest problematyczny w przetwarzaniu obrazów?
Ponieważ jego wariancja zależy od sygnału, a wiele algorytmów przetwarzania zakłada szum o stałej wariancji.
- Czym jest szum Gaussa?
Szum Gaussa to szum o rozkładzie normalnym, zerowej wartości oczekiwanej i stałej wariancji, często stosowany jako model obliczeniowy.
- Dlaczego algorytmy przetwarzania często zakładają szum Gaussa?
Ponieważ model Gaussa jest matematycznie wygodny i dobrze opisuje wiele zjawisk po odpowiednich transformacjach danych.
- Na czym polega stabilizacja wariancji?
Stabilizacja wariancji polega na przekształceniu danych tak, aby wariancja szumu była stała i niezależna od sygnału.
- Jaką transformację stosuje się do stabilizacji wariancji szumu Poissona?
Stosuje się transformatę Anscombe’a.
- Podaj wzór transformaty Anscombe’a.

- Jakie są efekty zastosowania transformaty Anscombe’a?
Po transformacji szum ma charakter zbliżony do Gaussowskiego, o stałej wariancji, niezależnej od jasności obrazu.
- Dlaczego stabilizacja wariancji poprawia skuteczność filtracji?
Ponieważ umożliwia stosowanie klasycznych algorytmów filtracji, które zakładają szum o stałej wariancji.
- Jakie inne rodzaje szumów można spotkać w obrazach cyfrowych?
Szum Gaussa addytywny, szum impulsowy typu „sól i pieprz” oraz szum kwantyzacji.
- Dlaczego poprawne modelowanie szumu jest ważne?
Ponieważ umożliwia dobór odpowiednich metod filtracji i zapobiega utracie istotnych informacji w obrazie.
## Reprezentacja obrazu cyfrowego i kolor
- Czym jest obraz cyfrowy z punktu widzenia teorii sygnałów?
Obraz cyfrowy jest sygnałem dwuwymiarowym, próbkowanym w przestrzeni i skwantyzowanym w amplitudzie, reprezentowanym jako macierz pikseli.
- Na czym polega reprezentacja koloru w obrazie cyfrowym?
Reprezentacja koloru polega na opisie barwy piksela za pomocą zestawu składowych w określonej przestrzeni barw, np. RGB lub YCbCr.
- Czym jest model RGB?
Model RGB opisuje kolor jako kombinację trzech składowych: czerwonej, zielonej i niebieskiej, bezpośrednio związanych z technologią wyświetlaczy.
- Jakie są wady modelu RGB w kontekście przetwarzania i kompresji?
W modelu RGB informacja o jasności i kolorze jest silnie powiązana, co utrudnia efektywną kompresję i wykorzystanie właściwości percepcyjnych wzroku.
- Jakie właściwości ludzkiego wzroku wykorzystuje się w przetwarzaniu obrazów?
Wykorzystuje się fakt, że ludzki wzrok jest bardziej czuły na zmiany jasności niż na zmiany koloru.
- Czym jest model YCbCr?
Model YCbCr to przestrzeń barw, w której informacja o jasności (Y) jest oddzielona od informacji o kolorze (Cb i Cr).
- Jakie znaczenie ma składowa Y w modelu YCbCr?
Składowa Y reprezentuje luminancję, czyli jasność obrazu, która jest kluczowa dla percepcji szczegółów.
- Jakie znaczenie mają składowe Cb i Cr?
Składowe Cb i Cr opisują chrominancję, czyli informację o barwie, na którą wzrok jest mniej wrażliwy.
- Na czym polega transformacja RGB → YCbCr?
Polega na liniowej transformacji składowych RGB do postaci rozdzielającej jasność i kolor, z ewentualnym przesunięciem wartości chrominancji.
- Czym jest chroma subsampling?
Chroma subsampling to technika polegająca na zmniejszeniu rozdzielczości składowych chrominancji przy zachowaniu pełnej rozdzielczości luminancji.
- Co oznacza zapis 4:4:4?
Zapis 4:4:4 oznacza brak redukcji chrominancji — luminancja i chrominancja są próbkowane z tą samą rozdzielczością.
- Co oznacza zapis 4:2:2?
Zapis 4:2:2 oznacza zmniejszenie liczby próbek chrominancji o połowę w poziomie przy zachowaniu pełnej rozdzielczości w pionie.
- Co oznacza zapis 4:2:0?
Zapis 4:2:0 oznacza zmniejszenie liczby próbek chrominancji zarówno w poziomie, jak i w pionie, przy zachowaniu pełnej rozdzielczości luminancji.
- Dlaczego chroma subsampling nie powoduje dużej utraty jakości wizualnej?
Ponieważ ludzki wzrok jest znacznie mniej czuły na zmiany koloru niż na zmiany jasności.
- W jakich standardach stosuje się YCbCr i chroma subsampling?
Są one stosowane m.in. w standardach JPEG, MPEG oraz innych systemach kompresji obrazu i wideo.
- Czy chroma subsampling jest procesem stratnym?
Tak, jest procesem stratnym, ponieważ prowadzi do trwałej redukcji informacji o kolorze.
- Jakie są ograniczenia chroma subsamplingu?
Może powodować artefakty kolorystyczne, szczególnie widoczne w przypadku tekstu, grafiki i ostrych krawędzi barwnych.
## Interpolacja i aproksymacja sygnałów i obrazów
- Dlaczego w przetwarzaniu sygnałów potrzebujemy interpolacji?
Ponieważ sygnały cyfrowe są dyskretne, a wiele operacji, takich jak skalowanie czy obrót, wymaga wyznaczania wartości sygnału w punktach pośrednich.
- Na czym polega interpolacja sygnału?
Interpolacja polega na wyznaczaniu funkcji ciągłej, która dokładnie przechodzi przez wszystkie znane próbki sygnału.
- Jaki warunek musi być spełniony, aby idealna interpolacja była możliwa?
Musi być spełnione twierdzenie Shannona–Nyquista, czyli częstotliwość próbkowania musi być co najmniej dwukrotnie większa od najwyższej częstotliwości sygnału.
- Jaka jest idealna funkcja interpolująca?
Idealną funkcją interpolującą jest funkcja sinc, wynikająca bezpośrednio z twierdzenia Shannona.
- Dlaczego funkcja sinc nie jest stosowana w praktyce?
Ponieważ ma nieskończony zasięg i jest kosztowna obliczeniowo, co uniemożliwia jej praktyczne zastosowanie.
- Na czym polega interpolacja najbliższego sąsiada?
Polega na przypisaniu wartości najbliższej próbki, jest bardzo szybka, ale powoduje widoczne artefakty w obrazie.
- Czym różni się interpolacja liniowa od biliniowej?
Interpolacja liniowa dotyczy sygnałów jednowymiarowych, natomiast biliniowa jest jej odpowiednikiem dla obrazów dwuwymiarowych.
- Jakie są zalety interpolacji sześciennej (bikubicznej)?
Zapewnia lepsze zachowanie krawędzi i gładszy obraz kosztem większej złożoności obliczeniowej.
- Podaj typowe zastosowania interpolacji.
Skalowanie obrazów, obrót obrazów, zmiana rozdzielczości oraz rekonstrukcja sygnałów.
- Czym jest aproksymacja sygnału?
Aproksymacja polega na przybliżeniu sygnału funkcją, która nie musi dokładnie przechodzić przez wszystkie próbki, lecz minimalizuje błąd globalny.
- Jaka jest podstawowa różnica między interpolacją a aproksymacją?
Interpolacja przechodzi dokładnie przez próbki, natomiast aproksymacja dopuszcza odchylenia w punktach próbkowania.
- Jakie są zalety aproksymacji w obecności szumu?
Aproksymacja jest bardziej odporna na szum, ponieważ nie dopasowuje się dokładnie do zakłóconych próbek.
- Na czym polega aproksymacja z użyciem baz ortogonalnych?
Polega na przedstawieniu sygnału jako sumy funkcji bazowych z odpowiednimi współczynnikami, np. Fouriera lub falkowych.
- Jakie bazy ortogonalne są najczęściej stosowane?
Baza Fouriera, kosinusowa (DCT) oraz falkowa (wavelet).
- Jak aproksymacja wiąże się z redukcją szumu?
Ograniczenie liczby współczynników aproksymacji usuwa składowe wysokoczęstotliwościowe, które często odpowiadają za szum.
- W jakich zastosowaniach lepsza jest interpolacja, a w jakich aproksymacja?
Interpolacja jest lepsza w operacjach geometrycznych, natomiast aproksymacja w estymacji sygnału, filtracji i kompresji.
- Dlaczego interpolacja i aproksymacja są kluczowe dla dalszych etapów przetwarzania?
Ponieważ stanowią podstawę dla transformacji, filtracji oraz algorytmów kompresji sygnałów i obrazów.
## Filtracja sygnałów i obrazów cyfrowych
- Czym jest filtracja sygnałów i obrazów?
Filtracja to proces przekształcania sygnału lub obrazu w celu redukcji szumu, wygładzenia lub uwydatnienia istotnych cech, takich jak krawędzie.
- Jaki jest główny kompromis w procesie filtracji?
Kompromis polega na zmniejszaniu zakłóceń przy jednoczesnym zachowaniu istotnych szczegółów obrazu lub sygnału.
- Na czym polega filtr liniowy?
Filtr liniowy polega na obliczaniu nowej wartości próbki jako sumy ważonej sąsiednich próbek, czyli na wykonaniu splotu sygnału z jądrem filtru.
- Czym jest splot (konwolucja)?
Splot to operacja matematyczna polegająca na przesuwaniu maski po sygnale lub obrazie i obliczaniu sumy iloczynów wartości i wag.
- Jakie są cechy filtrów splotowych?
Są liniowe, stacjonarne, łatwe do analizy, ale wrażliwe na wartości odstające.
- Podaj przykłady filtrów splotowych.
Filtr uśredniający, filtr Gaussa, filtry detekcji krawędzi.
- Czym jest filtr medianowy?
Filtr medianowy to filtr nieliniowy, który zastępuje wartość piksela medianą z jego otoczenia.
- Dlaczego filtr medianowy dobrze usuwa szum impulsowy?
Ponieważ mediana jest odporna na wartości odstające, które są charakterystyczne dla szumu impulsowego.
- Jak filtr medianowy wpływa na krawędzie obrazu?
Zachowuje krawędzie lepiej niż filtry liniowe, ponieważ nie uśrednia intensywnie wartości po obu stronach krawędzi.
- Czym jest filtr bilateralny?
Filtr bilateralny to filtr adaptacyjny, który uwzględnia zarówno odległość przestrzenną, jak i podobieństwo wartości pikseli.
- Jakie są główne zalety filtru bilateralnego?
Skutecznie redukuje szum i jednocześnie zachowuje ostre krawędzie obrazu.
- Jakie są wady filtru bilateralnego?
Jest obliczeniowo kosztowny i wolniejszy od klasycznych filtrów splotowych.
- Jak dobrać filtr do rodzaju szumu?
Dla szumu Gaussa stosuje się filtry splotowe, dla szumu impulsowego filtry medianowe, a dla szumu Poissona – po stabilizacji wariancji – filtry splotowe lub bilateralne.
- Czym różni się filtracja od aproksymacji?
Filtracja jest operacją lokalną, a aproksymacja globalnym przybliżeniem sygnału za pomocą funkcji bazowych.
- Dlaczego filtracja jest ważna przed dalszym przetwarzaniem?
Ponieważ redukuje zakłócenia i poprawia jakość danych wejściowych dla kolejnych algorytmów, takich jak detekcja cech czy kompresja.
- Czy filtracja zawsze poprawia jakość obrazu?
Nie, nadmierna filtracja może prowadzić do utraty szczegółów i rozmycia obrazu.
- Jaką rolę pełni filtracja w całym pipeline przetwarzania obrazu?
Filtracja przygotowuje dane do dalszego przetwarzania, redukując szum i stabilizując sygnał przed transformacjami i kompresją.
## Transformaty w przetwarzaniu sygnałów i obrazów
- Po co stosuje się transformaty w przetwarzaniu sygnałów i obrazów?
Aby zmienić sposób reprezentacji sygnału na taki, który ułatwia analizę, filtrację, redukcję szumu i kompresję.
- Co oznacza, że transformata jest ortogonalna?
Oznacza to, że funkcje bazowe są wzajemnie ortogonalne, co pozwala na niezależną analizę poszczególnych współczynników.
- Na czym polega idea transformacji Fouriera?
Transformata Fouriera rozkłada sygnał na składowe częstotliwościowe, pokazując jakie częstotliwości i z jaką amplitudą występują w sygnale.
- Czym jest FFT?
FFT to szybki algorytm obliczania transformaty Fouriera, redukujący złożoność obliczeniową do rzędu .
- Jakie są główne ograniczenia transformaty Fouriera?
Brak lokalizacji czasowej – nie informuje, kiedy dana częstotliwość występuje w sygnale.
- Czym różni się DCT od FFT?
DCT wykorzystuje tylko funkcje kosinusowe, zapewnia lepszą kompaktowość energii i jest bardziej efektywna w kompresji obrazów.
- Dlaczego DCT jest stosowana w JPEG?
Ponieważ skupia większość energii obrazu w niewielkiej liczbie współczynników niskoczęstotliwościowych, co umożliwia skuteczną kompresję.
- Na czym polega blokowe przetwarzanie w DCT?
Obraz jest dzielony na małe bloki (np. 8×8), na których niezależnie wykonywana jest transformata DCT.
- Czym jest transformata falkowa (FWT)?
Transformata falkowa analizuje sygnał jednocześnie w dziedzinie czasu i częstotliwości, umożliwiając analizę lokalną.
- Jakie są zalety FWT w porównaniu do FFT i DCT?
Zapewnia lepszą analizę sygnałów nieustacjonarnych oraz wielorozdzielczą reprezentację.
- Dlaczego FWT jest stosowana w JPEG 2000?
Ponieważ oferuje lepszą kompresję przy zachowaniu szczegółów i mniejszą liczbę artefaktów blokowych.
- Jak transformacje pomagają w redukcji szumu?
Ponieważ szum jest zwykle reprezentowany przez wysokie częstotliwości, które można łatwo progować lub usuwać po transformacji.
- Co to jest kompaktowa reprezentacja sygnału?
To reprezentacja, w której większość energii sygnału skupiona jest w niewielkiej liczbie współczynników.
- Jaką rolę pełnią transformaty w kompresji stratnej?
Pozwalają oddzielić istotne składowe sygnału od mniej istotnych, które mogą zostać usunięte lub skwantyzowane.
- Podaj różnice między FFT, DCT i FWT.
FFT analizuje globalne częstotliwości, DCT zapewnia kompaktową reprezentację, a FWT umożliwia analizę lokalną i wielorozdzielczą.
- Czy transformata zmienia informację zawartą w sygnale?
Nie, transformata jedynie zmienia sposób reprezentacji informacji, bez jej utraty (przed kwantyzacją).
- Dlaczego transformaty są kluczowe w przetwarzaniu obrazów i sygnałów?
Ponieważ stanowią podstawę nowoczesnych algorytmów filtracji, estymacji i kompresji danych.
## Kompresja danych cyfrowych (bezstratna i stratna)
- Czym jest kompresja danych?
Kompresja danych to proces zmniejszania ilości danych potrzebnych do reprezentacji sygnału lub obrazu poprzez usuwanie redundancji.
- Jakie są główne cele kompresji?
Zmniejszenie rozmiaru plików, efektywna transmisja danych oraz lepsze wykorzystanie przepustowości kanału.
- Jakie rodzaje redundancji wykorzystuje kompresja?
Redundancję statystyczną, przestrzenną/czasową oraz percepcyjną.
- Czym różni się kompresja bezstratna od stratnej?
Kompresja bezstratna umożliwia idealne odtworzenie danych, natomiast stratna powoduje trwałą utratę części informacji.
- Czym jest kodowanie entropijne?
Kodowanie entropijne to bezstratna metoda kompresji, w której długość kodu symbolu zależy od częstości jego występowania.
- Na czym polega kodowanie RLE?
RLE zapisuje sekwencje powtarzających się symboli w postaci par: liczba wystąpień i wartość.
- Jak działa kodowanie Huffmana?
Kodowanie Huffmana przypisuje krótsze kody symbolom częściej występującym, a dłuższe symbolom rzadszym.
- Czym różni się kodowanie arytmetyczne od Huffmana?
Kodowanie arytmetyczne koduje cały strumień danych jako jedną liczbę, osiągając zwykle wyższą efektywność.
- Jaka jest granica skuteczności kompresji bezstratnej?
Granica skuteczności jest wyznaczona przez entropię źródła danych.
- Czym jest kompresja stratna?
Kompresja stratna usuwa informacje mało istotne percepcyjnie, nie pozwalając na idealne odtworzenie danych.
- Jakie są główne etapy kompresji stratnej?
Transformacja, progowanie, kwantyzacja oraz kodowanie entropijne.
- Który etap kompresji stratnej powoduje nieodwracalną utratę informacji?
Kwantyzacja.
- Jaką rolę pełni transformacja w kompresji stratnej?
Transformacja pozwala skupić energię sygnału w niewielkiej liczbie współczynników, ułatwiając usuwanie mniej istotnych informacji.
- Na czym polega kwantyzacja w kompresji stratnej?
Polega na przybliżeniu współczynników transformacji, często prowadząc do ich zerowania.
- Dlaczego wysokie częstotliwości są silniej kwantyzowane?
Ponieważ są mniej istotne percepcyjnie dla ludzkiego wzroku lub słuchu.
- Opisz w skrócie pipeline JPEG.
Konwersja RGB→YCbCr, chroma subsampling, DCT, kwantyzacja, kodowanie RLE i Huffmana.
- Dlaczego JPEG jest kompresją stratną?
Ponieważ zawiera etap kwantyzacji oraz redukcję chrominancji, które powodują trwałą utratę informacji.
- Jakie są przykłady kompresji stratnej audio i wideo?
MP3 dla audio oraz MPEG dla wideo.
- W jakich zastosowaniach stosuje się kompresję bezstratną?
W danych tekstowych, archiwach, danych medycznych i wszędzie tam, gdzie nie można dopuścić utraty informacji.
- Dlaczego kompresja jest kluczowym elementem przetwarzania sygnałów i obrazów?
Ponieważ umożliwia efektywne przechowywanie i transmisję dużych ilości danych przy ograniczonych zasobach.
## Zastosowania algorytmów przetwarzania sygnałów i obrazów
- Dlaczego zastosowania algorytmów są ważne na egzaminie dyplomowym?
Ponieważ pokazują praktyczne zrozumienie całego procesu przetwarzania sygnałów i obrazów, a nie tylko znajomość pojedynczych definicji.
- Na czym polega pipeline przetwarzania obrazu?
Pipeline obejmuje akwizycję obrazu, wstępne przetwarzanie, analizę oraz ewentualną transformację i kompresję danych.
- Jakie etapy obejmuje akwizycja obrazu?
Próbkowanie, kwantyzację oraz rejestrację sygnału obarczonego szumem.
- Dlaczego filtracja jest wykonywana na wczesnym etapie przetwarzania?
Ponieważ redukuje szum i poprawia jakość danych wejściowych dla dalszych algorytmów analizy i detekcji cech.
- Czym jest autofocus oparty na kontraście?
Jest to metoda ustawiania ostrości polegająca na maksymalizacji miary ostrości obrazu, związanej z zawartością wysokich częstotliwości.
- Jakie algorytmy są wykorzystywane w autofokusie kontrastowym?
Filtracja, detekcja krawędzi, obliczanie miar takich jak wariancja lub suma modułów gradientu.
- Dlaczego obraz ostry zawiera więcej wysokich częstotliwości?
Ponieważ ostre krawędzie i detale powodują gwałtowne zmiany jasności, które odpowiadają wysokim częstotliwościom.
- Na czym polega autofocus z detekcją fazy?
Polega na analizie przesunięcia obrazów w celu bezpośredniego wyznaczenia kierunku i wielkości korekty ostrości.
- Czym są cechy w obrazie cyfrowym?
Cechy to charakterystyczne elementy obrazu, takie jak krawędzie, narożniki czy tekstury, wykorzystywane w analizie obrazu.
- Dlaczego detekcja cech wymaga wcześniejszej filtracji?
Ponieważ szum może powodować fałszywe detekcje, a filtracja stabilizuje sygnał przed analizą.
- Jaką rolę pełni redukcja szumu w estymacji sygnału?
Poprawia dokładność estymacji i zmniejsza wpływ losowych zakłóceń na wyniki analizy.
- W jakich zastosowaniach kluczowa jest kompresja danych?
W transmisji wideo, systemach monitoringu, archiwizacji danych oraz systemach wbudowanych.
- Jakie elementy kursu są wykorzystywane w kompresji obrazu?
Próbkowanie, transformacje, kwantyzacja, filtracja oraz kodowanie entropijne.
- Dlaczego kompresja jest niezbędna w systemach wizyjnych?
Ponieważ obrazy i wideo generują bardzo duże ilości danych, których nie da się efektywnie przesyłać ani przechowywać bez kompresji.
- Jak można odpowiedzieć przekrojowo na pytanie o zastosowanie przetwarzania obrazu?
Opisując cały proces od akwizycji, przez filtrację i analizę, aż po transformację i kompresję danych.
- Dlaczego szum musi być uwzględniany w praktycznych zastosowaniach?
Ponieważ każdy realny system pomiarowy generuje szum, który wpływa na jakość analizy i decyzji algorytmów.
- Jakie są typowe błędy w odpowiedziach dotyczących zastosowań?
Skupianie się na pojedynczym algorytmie bez pokazania całego pipeline’u oraz pomijanie wpływu szumu.
- Dlaczego rozdział o zastosowaniach dobrze zamyka cały przedmiot?
Ponieważ pokazuje praktyczne wykorzystanie wszystkich wcześniej omawianych zagadnień w jednym spójnym systemie.

# Dla bardzo leniwych
## Sygnały i obrazy – absolutne podstawy
**Sygnał** – funkcja niosąca informację o zjawisku fizycznym (czas / przestrzeń).

**Obraz** – sygnał dwuwymiarowy .
Sygnał analogowy
- ciągły w czasie i amplitudzie
- istnieje w naturze
Sygnał cyfrowy
- dyskretny w czasie/przestrzeni i amplitudzie
- nie istnieje w naturze
- powstaje przez: próbkowanie + kwantyzację
Akwizycja obrazu
- sensor zlicza fotony
- proces losowy → szum
## Próbkowanie i kwantyzacja (MUST HAVE)
Próbkowanie
- dyskretyzacja czasu / przestrzeni
- częstotliwość próbkowania

Twierdzenie Shannona–Nyquista f_s >= 2f_max

za małe f_s → aliasing (nieodwracalny)

Kwantyzacja
- dyskretyzacja amplitudy
- liczba poziomów: L = 2^B

Błąd kwantyzacji
- ma charakter szumu
- jest nieodwracalny
Różnica (klasyk egzaminacyjny)
- próbkowanie → aliasing → potencjalnie odwracalne
- kwantyzacja → błąd kwantyzacji → nieodwracalna
### Sygnały cyfrowe, kanał i entropia
Sygnał cyfrowy
- dyskretny
- alfabet symboli (np. {0,1})
Kanał informacyjny
- medium transmisji (fizyczne / logiczne)
- cechy:
    - przepustowość
    - zakłócenia
    - błędy
      
Entropia
- miara ilości informacji
- niska entropia → dobra kompresja
- wysoka entropia → dane losowe
Entropia = dolna granica kompresji bezstratnej

Błędy
- zakłócenia → błędy bitów
- detekcja: np. bit parzystości
- korekcja: np. kod Hamminga
## Szumy w sygnałach i obrazach
Szum
- losowa, niepożądana składowa
- nie jest błędem algorytmu

Szum Poissona (bardzo ważne)
- wynika z zliczania fotonów

jaśniej = większy szum
wariancja zależy od sygnału

Szum Gaussa
- model obliczeniowy:
   - zerowa średnia
   - stała wariancja
- większość algorytmów go zakłada

Stabilizacja wariancji
Efekt:
- Poisson → ~Gauss
- stała wariancja
- można skutecznie filtrować
## Reprezentacja obrazu i kolor
RGB
- (R, G, B)
- prosty
- nieoptymalny do kompresji

Percepcja wzroku
- wzrok najbardziej czuły na jasność
- mniej czuły na kolor
## Interpolacja i aproksymacja
### Interpolacja
- wyznaczanie wartości między próbkami
- dokładnie przechodzi przez próbki
- idealna: sinc (teoria Shannona)
- praktyka:
    - nearest neighbor – szybka, słaba
    - biliniowa – kompromis
    - bikubiczna – dobra jakość, wolniejsza

Zastosowania: skalowanie, obrót, zmiana rozdzielczości
### Aproksymacja
- nie musi przechodzić przez próbki
- minimalizuje błąd globalny
- odporna na szum
- oparta o bazy ortogonalne:
    - Fourier
    - DCT
    - falki

aproksymacja = estymacja sygnału
## Filtracja sygnałów i obrazów
Cel filtracji
- redukcja szumu
- zachowanie istotnych cech (krawędzie)
### Filtry
Splotowe (liniowe)
- filtr Gaussa
- filtr uśredniający
- wrażliwe na szum impulsowy
Medianowe (nieliniowe)
- najlepsze dla „sól i pieprz”
- dobrze zachowują krawędzie
Bilateralne (adaptacyjne)
- filtrują + zachowują krawędzie
- wolne obliczeniowo
### Dobór filtru do szumu
- Gauss → filtr Gaussa
- impulsowy → medianowy
- Poisson (po Anscombe) → splotowy / bilateralny

filtracja = etap wstępny przed analizą
## Transformaty (FFT, DCT, FWT)
Po co?
- przejście z:
    - czasu/przestrzeni → częstotliwości/skali
- łatwiejsza:
    - filtracja
    - kompresja
    - redukcja szumu
### FFT
- analiza częstotliwości
- FFT = algorytm, nie nowa transformata
- brak lokalizacji czasowej
### DCT
- tylko cosinusy
- kompaktowa reprezentacja
- podstawa JPEG
### FWT (falki)
- analiza lokalna
- dobra dla sygnałów nieustacjonarnych
- JPEG2000
### MUST KNOW
- FFT → analiza
- DCT → kompresja obrazu
- FWT → nowoczesna kompresja + detale

## Kompresja danych
### Bezstratna
- brak utraty informacji
- granica = entropia
- RLE, Huffman, arytmetyczne
### Stratna
- usuwa informacje percepcyjnie nieistotne
- pipeline:
    - transformacja
    - progowanie
    - kwantyzacja (STRATA!)
    - kodowanie entropijne
### JPEG (MUST KNOW)
- RGB → YCbCr
- chroma subsampling (4:2:0)
- DCT 8×8
- kwantyzacja
- RLE + Huffman
### Porównanie
- bezstratna → dane, tekst
- stratna → obraz, audio, wideo
## Zastosowania (rozdział spinający wszystko)
### Pipeline przetwarzania obrazu
- Akwizycja
(próbkowanie + kwantyzacja + szum)
- Wstępne przetwarzanie
(stabilizacja wariancji, filtracja)
- Analiza
(detekcja cech, estymacja)
- Transformacje i kompresja

ten schemat pasuje do wszystkiego
### Autofokus
- ostry obraz → dużo wysokich częstotliwości
- filtracja + miara ostrości
- maksimum = najlepsza ostrość
### Detekcja cech
- krawędzie = duże zmiany jasności
- zawsze po filtracji
- szum → fałszywe detekcje
### ZŁOTA ODPOWIEDŹ PRZEKROJOWA
„Obraz jest próbkowany i kwantyzowany, następnie filtrowany w celu redukcji szumu, analizowany pod kątem cech, a na końcu transformowany i kompresowany do transmisji lub zapisu.”
# Jak jesteś w dupie to chociaż to um
Cyfrowe przetwarzanie obrazów i sygnałów zajmuje się analizą i modyfikacją sygnałów analogowych po ich zamianie na postać cyfrową poprzez **próbkowanie** i **kwantyzację**. Kluczowe znaczenie ma poprawny dobór częstotliwości próbkowania zgodnie z **twierdzeniem Shannona**, ponieważ jego niespełnienie prowadzi do **aliasingu**, który jest nieodwracalny.
W praktycznych systemach sygnały i obrazy są zawsze obarczone **szumem**, często o charakterze **Poissona** wynikającym z akwizycji, dlatego stosuje się **stabilizację wariancji** i **filtrację** z użyciem filtrów splotowych, medianowych lub adaptacyjnych, takich jak **filtr** bilateralny.
Dalsze przetwarzanie często odbywa się w dziedzinie transformacji, np. **Fouriera**, **DCT** lub **falkowej**, które pozwalają uzyskać **kompaktową reprezentację** sygnału i są podstawą **kompresji danych**. W kompresji stratnej, takiej jak **JPEG**, wykorzystuje się również **percepcję wzroku**, rozdzielając jasność i kolor w przestrzeni **YCbCr** oraz stosując **chroma subsampling**.
Cały proces tworzy spójny **pipeline** od akwizycji, przez filtrację i analizę, aż po **kompresję** i **transmisję**, co znajduje zastosowanie m.in. w systemach wizyjnych, monitoringu czy algorytmach takich jak **autofokus**.


**Próbkowanie** polega na zamianie sygnału ciągłego na dyskretny poprzez pobieranie jego wartości w określonych odstępach czasu lub przestrzeni. Jakość próbkowania zależy od częstotliwości próbkowania.

**Kwantyzacja** to proces dyskretyzacji amplitudy sygnału, w którym każda próbka jest zaokrąglana do jednego z dostępnych poziomów. Powoduje nieodwracalny błąd kwantyzacji.

**Twierdzenie Shannona–Nyquista** mówi, że sygnał może być idealnie odtworzony, jeśli częstotliwość próbkowania jest co najmniej dwukrotnie większa od najwyższej częstotliwości sygnału.

**Aliasing** to zjawisko zniekształcenia sygnału wynikające z niedostatecznej częstotliwości próbkowania, powodujące nakładanie się widm. Jest zjawiskiem nieodwracalnym.

**Szum** to losowa, niepożądana składowa sygnału, która nie niesie informacji użytecznej. Występuje we wszystkich rzeczywistych systemach pomiarowych.

**Szum Poissona** wynika z losowego charakteru zliczania fotonów w sensorach obrazu. Jego wariancja zależy od jasności sygnału.

**Stabilizacja wariancji** polega na przekształceniu sygnału tak, aby wariancja szumu była stała. Umożliwia to stosowanie klasycznych algorytmów filtracji.

**Filtracja** to proces przetwarzania sygnału w celu redukcji szumu lub uwydatnienia istotnych cech. Jest kluczowym etapem wstępnym dalszej analizy.

**Filtry splotowe** są filtrami liniowymi opartymi na operacji splotu z maską. Dobrze redukują szum Gaussa, ale są wrażliwe na wartości odstające.

**Filtry medianowe** są filtrami nieliniowymi, które zastępują wartość próbki medianą z jej otoczenia. Są bardzo skuteczne w usuwaniu szumu impulsowego.

**Filtry adaptacyjne** dostosowują swoje działanie do lokalnych właściwości sygnału lub obrazu. Pozwalają lepiej zachować krawędzie i detale.

**Filtr bilateralny** uwzględnia zarówno odległość przestrzenną, jak i różnice jasności między pikselami. Umożliwia redukcję szumu przy zachowaniu krawędzi.

**Transformata Fouriera** rozkłada sygnał na składowe częstotliwościowe. Jest podstawowym narzędziem analizy widmowej sygnałów.

**Transformata kosinusowa (DCT)** wykorzystuje tylko funkcje kosinusowe i skupia energię sygnału w niewielkiej liczbie współczynników. Jest podstawą kompresji JPEG.

**Transformata falkowa** umożliwia analizę sygnału jednocześnie w dziedzinie czasu i częstotliwości. Jest szczególnie skuteczna dla sygnałów nieustacjonarnych.

**Kompaktowa reprezentacja** oznacza, że większość informacji sygnału zawarta jest w niewielkiej liczbie współczynników. Ułatwia to kompresję danych.

**Kompresja** danych polega na zmniejszeniu ilości informacji potrzebnych do zapisu sygnału poprzez usunięcie redundancji. Może być bezstratna lub stratna.

**JPEG** to algorytm kompresji stratnej obrazu wykorzystujący DCT, kwantyzację oraz kodowanie entropijne. Bazuje na właściwościach percepcji wzroku.

**Percepcja wzroku** opisuje sposób, w jaki człowiek postrzega jasność i kolor. Wzrok jest bardziej czuły na jasność niż na barwę.

**YCbCr** to przestrzeń barw rozdzielająca luminancję od chrominancji. Umożliwia efektywną kompresję obrazu.

**Chroma subsampling** polega na zmniejszeniu rozdzielczości informacji o kolorze przy zachowaniu pełnej rozdzielczości jasności. Jest procesem stratnym, ale mało zauważalnym.

**Pipeline** to uporządkowany ciąg etapów przetwarzania danych od akwizycji do końcowego wyniku. Zapewnia spójność całego systemu przetwarzania.

**Kompresja** w pipeline pozwala na efektywne przechowywanie i transmisję danych. Jest niezbędna w systemach przetwarzających obraz i wideo.

**Transmisja** to przesyłanie danych przez kanał komunikacyjny. Kompresja zmniejsza wymagania dotyczące przepustowości.

**Autofokus** to algorytm automatycznego ustawiania ostrości obrazu poprzez maksymalizację miary ostrości. Wykorzystuje filtrację i analizę częstotliwości.
