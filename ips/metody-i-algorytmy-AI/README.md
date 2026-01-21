# Metody i algorytmy AI

## 1. Definicje
  * **AI (Sztuczna inteligencja):** dziedzina informatyki skupiająca się na systemach zdolnych do wykonywania zadań wymagających ludzkiej inteligencji.
  * **ML (Uczenie maszynowe):** podzbiór AI skupiony na algorytmach, które na podstawie danych poprawiają swój wynik z każdą iteracją, nie są jawnie zaprogramowane.
  * **DL (Uczenie głębokie):** podzbiór ML skupiony na wielowarstwowych sieciach neuronowych, umożliwiający automatyczne uczenie się złożonych reprezentacji danych na podstawie dużych zbiorów uczących.

## 2. Metody ML

  * **Uczenie nadzorowane:** uczenie na podstawie poetykietowanych danych, z oczekiwanym wyjściem. Używane do klasyfikacji lub regresji.
    ### Przykłady:
      * **Klasyfikacja:** przypisanie jednej z wcześniej zdefiniowanych klas do elementu wejściowego np. określenie na obrazku czy jest pies czy kot. Przykłady algorytmu: Regresja logistyczna, k-najbliższych sąsiadów, SVM, drzewa decyzyjne i lasy losowe.
         * **Regresja logistyczna:** przy pomocy funckji sigmoidalnej przypisuje prawdopodobieństwo, od 0 do 1, przynależności do klasy.
         * **K-najbliższych sąsiadów:** określa klasę przy pomocy k najbliższych sąsiadów. Przykład dla k=5, dodajemy nowy punkt, sprawdzamy odległość tego punktu od każdego punktu, bierzemy 5 punktów z najkrótszą odległością i patrzymy jakie mają klasy punkty, przeważająca klasa wsród punktów zostaje przypisana do nowego punktu. Parametr k ma duże znaczenie, za mały (bardzo nerwowy), za duży (pomija lokalne szczegóły).
         * **SVM (Maszyna wektorów nośnych):** Algorytm szukający optymalnej hiperpłaszczyzny rozdzielającej klasy z zachowaniem maksymalnego marginesu (odstępu). W przypadku danych nieseparowalnych liniowo wykorzystuje tzw. trik jądrowy (kernel trick) do rzutowania ich do przestrzeni o wyższym wymiarze.
         * **Drzewa decyzyjne:** Algorytm oparty na metodzie if-them, algorytm szuka pytania, które najlepiej podzieli zbiór na jednorodne grupy, proces zaczyna się u korzenia i idzie do samego liścia.
         * **Las losowy:** trenujemy dużo drzew decyzyjnych równolegle, każde drzewo widzi tylko część cech, przeważająca ilość drzew wybiera klasę.
      * **Regresja:** przewiduje wartość liczbową z jakiegoś zakresu. Np. przewidywanie cen mieszkań. Przykład: regresja liniowa lub wielomianowa.
  * **Uczenie nienadzorowane:** algorytm sam wykrywa ukryte wzorce w nieetykietowanych danych, najczęściej klaseryzuje, redukuje wymiarowość lub wykrywa anomalie.
    ### Przykłady:
      * **Klasteryzacja:** Grupowanie podobnych obiektów.
        * **K-średnich (K-Means):** Algorytm dzieli dane na k grup. Przypisuje punkty do najbliższego centroidu, a następnie aktualizuje pozycję centroidu jako średnią ze wszystkich punktów w grupie. Proces trwa do momentu stabilizacji.
        * **DBSCAN:** grupuje punkty znajdujące się blisko siebie, tworząc klastry o dowolnych kształtach. Jego unikalną cechą jest zdolność do automatycznego identyfikowania i odizolowywania punktów o niskim zagęszczeniu jako szumu
      * **Redukcja wymiarowości** Zmniejszanie liczby cech przy zachowaniu kluczowych informacji. Dwa sposoby: selekcja cech (wybranie najlepszych cech i usunięcie reszty), ekstrakcja cech (tworzenie nowych sztucznych zmiennych z kombinacji starych)
      * **Wykrywanie anomalii:** Identyfikacja wzorców odbiegających od normy
 
  * **Uczenie półnadzorowane:** algorytm wykorzystuje obydwa powyższe sposoby, mała ilość danych poetykietowanych, duża niepoetykietowanych. Najczęściej propagacja etykiet lub self-trainingu.
    ### Przykłady:
      * **Propagacja etykiet:** bierzemy poetykietowane dane i szukamy danych podobnych do nich i przypisujemy te same etykiety.
      * **Self-training:** Trenujesz model na małej ilości danych etykietowanych (np. 100), wytrenowana sieć etykietuje dane niepoetykietowane, te co mają np. >0.97 prawdopodobieństwa etykiet to używamy ich i tych starych poetykietowanych do ponownego treningu.
  
  * **Uczenie ze wzmocnieniem:** algorytm uczy się w systemie kar i nagród maksymalizując łączną nagrodę w dłuższym czasie. Często używane w grach lub robotyce.
    ### Przykłady:
      * **Gry:** np. szachy, algorytm np. Q-learning (Q==quality). Algorytm uczy się metodą prób i błędów. Dobre ruch nagradzane, złe karane. Wyniki zapisywane w tabelce, algorytm nie popełnia tych samych błędów. DQN (Deep Q-Network): zamiast tabelki sieć neuronowa
      * **Robotyka:** używane do np. uczenia manipulatora podnoszenia przedmiotów albo do systemów sterowania robotem.

## 3. ANN (Sztuczne sieci neuronowe)
  ### 1. Ważne pojęcia:
  * **Wagi:** Parametry liczbowe określające siłę połączenia między neuronami
  * **Bias:** Przesunięcie funkcji aktywacji
  * **Funkcja aktywacji:** oblicza sygnał wyjściowy neuronu z wagi i biasu. Dodaje nieliniowość. Najpopularniejsze funkcje aktywacji: Sigmoid (0,1), Tanh (-1,1),Softmax(prawdopodobieństwo np. 0.3, 0.2, 0.5), ReLU (0,x)
  * **Warstwy:** poziomy sieci z neuronami przetwarzające informacje
  * **Funkcja straty:** ocenia jak bardzo sieć neuronowa się pomyliła np. Cross-entropy dla klasyfikacji (każe mocno za duży błąd, słabo za mały)
  * **Wsteczna propagacja:** mechanizm uczenia sieci, informuje od końca do początku, które wagi są do zmiany przy pomocy gradientu.
  * **Optymalizator** Optymalizuje w jaki sposób zmienić wagę, przykłady SGD, SGD Momentum RMSprop, Adam.
  * **Epoka:** Pełny cykl treningowy ze wszystkimi danymi
  * **Batch:** liczba danych na jedna iteracje treningu
  * **Over/under fitting (Przeuczenie/niedouczenie):** Przeuczony model nie generalizuje, uczy się na pamięć, niedouczony zgaduje odpowiedzi nawet treningowe.
  * **Transfer learning:** douczanie ostatnich warstw wytrenowanej sieci innymi danymi

  ### 2. Rodzaje:
  * **Perceptron** najprostszy rodzaj sztucznego neuronu, binarny klasyfikator
  * **MLP (Percepteron wielowarstwowy)** wiele neuronów, warstwa wejściowa i wyjściowa, warstwa ukryta. Umie robić rzeczy nieliniowe.
  * **CNN (Konwolucyjne sieci neuronowe)** do obraxzów, filtry splotowe, pooling zmniejsza rozmiar danych.
  * **RNN (Rekurencyjne sieci neuronowe)** do danych sekwencyjnych, sprzężenie zwrotne daje informację z przeszłości.
---
  * **Transformery**
  DODATKOWE: Używane w LLM, mechanizm uwagi.
---
## 4. Metryki jakości:
* **Dokładność (Accurancy):** Ogólny procent poprawnych trafień modelu.
* **Precyzja (Precision):** Wiarygodność wskazań – ile z oznaczonych jako "pozytywne" faktycznie nimi było
* **Czułość (Recall):** Skuteczność wykrywania – ile z faktycznie istniejących przypadków model zdołał wyłapać
* **F1-Score:** średnia między precyzją a czułością; przydatny przy nierównych klasach
* **MSE (błąd średniokwadratowy):** Średnia kwadratów błędów, bardzo surowo karze duże pomyłki.
* **MAE (Średni błąd bezwzględny):** Średnia różnica między wynikiem a prawdą, mówi, o ile średnio myli się model.
* **Macierz pomyłek:** tabela pokazująca co z czym pomylił model (TP, TN, FP, FN).







