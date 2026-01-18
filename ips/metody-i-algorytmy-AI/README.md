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
      * **Klasteryzacja:** 
      * **Redukcja wymiarowości**
      * **Wykrywanie anomalii:**
 
  * **Uczenie półnadzorowane:** algorytm wykorzystuje obydwa powyższe sposoby, mała ilość danych poetykietowanych, duża niepoetykietowanych. Najczęściej propagacja etykiet lub self-trainingu.
    ### Przykłady:
      * **Propagacja etykiet:**
      * **Self-training:**
  
  * **Uczenie ze wzmocnieniem:** algorytm uczy się w systemie kar i nagród maksymalizując łączną nagrodę w dłuższym czasie. Często używane w grach lub robotyce.
    ### Przykłady:
      * **Gry:**
      * **Robotyka:** 



## 3. ANN (Sztuczne sieci neuronowe)
  ### 1. Ważne pojęcia:
  * **Wagi:**
  * **Bias:**
  * **Funkcja aktywacji:**
  * **Warstwy:**
  * **Funkcja straty:**
  * **Wsteczna propagacja:**
  * **Optymalizator**
  * **Epoka:**
  * **Batch:**
  * **Over/under fitting (Przeuczenie/niedouczenie):**
  * **Transfer learning:**

  ### 2. Rodzaje:
  * **Perceptron**
  * **MLP (Percepteron wielowarstwowy)**
  * **CNN (Konwolucyjne sieci neuronowe)**
  * **RNN (Rekurencyjne sieci neuronowe)**
---
  * **Transformery**
---
## 4. Metryki jakości:
* **Dokładność (Accurancy):**
* **Precyzja (Precision):**
* **Czułość (Recall):**
* **F1-Score:**
* **MSE (błąd średniokwadratowy):**
* **MAE (Średni błąd bezwzględny):**
* **Macierz pomyłek:**





