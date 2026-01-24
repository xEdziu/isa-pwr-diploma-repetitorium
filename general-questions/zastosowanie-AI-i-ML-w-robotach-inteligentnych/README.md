<img width="1024" height="768" alt="AI i ML" src="https://github.com/user-attachments/assets/bcb1d043-1ffd-487c-9570-5c2c9a147ba3" />

# Zastosowanie AI i ML w Robotach Inteligentnych

## 1. Kluczowe Definicje

*   **Sztuczna Inteligencja (AI):** Zdolność systemu do działania w sposób "dalekowzroczny" i prawidłowy w danym otoczeniu.
*   **System Autonomiczny (AS):** System typu inteligentnego, zdolny do niezależnego wyboru działania na podstawie zgromadzonej wiedzy i rozumienia otoczenia, reagujący na sytuacje nieprzewidziane przez konstruktora.
*   **Robot:** System fizyczny (ciało, czujniki, napędy), który podejmuje w sposób autonomiczny lub pół-automatyczny przy współpracy z człowiekiem. Aktualnie uczenie robota to najczęściej sterowanie adaptacyjne z uczeniem przez wzmacnianie.
*   **Poziomy Autonomii:** Wyróżnia się różne stopnie zaangażowania komputera – od braku wsparcia (człowiek decyduje o wszystkim), przez sterowanie nadzorowane, aż po pełną autonomię, gdzie robot ignoruje interwencje operatora.

## 2. Siedem Obszarów AI w Robotyce
Zastosowanie AI w robotach obejmuje siedem kluczowych sfer:
1.  **Reprezentacja wiedzy:** Sposób kodyfikacji informacji o robocie i jego otoczeniu. Robot pozyskuje dzięki AI wiedzę ogólną. Buduję bazę faktów, programista nie musi wpisywać ręcznie reguł, że np. robot przynosząc mleko dzięki temu wie, że to żywność przechowywana w lodówce -> wie gdzie po nie iść.
2.  **Rozumienie języka naturalnego (NLP):** Komunikacja z maszyną i rozumienie kontekstu poleceń.
3.  **Uczenie się (Learning):** Nabywanie nowej wiedzy i wykrywanie wzorców w danych.
4.  **Planowanie działań:** Wyznaczanie ścieżek do celu i ich aktualizacja w razie problemów.
5.  **Wnioskowanie (Inference):** Generowanie odpowiedzi przy niekompletnych informacjach.
6.  **Przeszukiwanie wiedzy:** Efektywne przeglądanie bazy danych w celu podjęcia decyzji.
7.  **Wizja (Vision):** Dominująca forma percepcji, pozwalająca na wyczuwanie przedmiotów w otoczeniu.

## 3. Uczenie Maszynowe (ML) i Uczenie przez Wzmacnianie (RL)
Uczenie robotów to dziś najczęściej połączenie sterowania adaptacyjnego z uczeniem przez wzmacnianie.

*   **Przykłady uczenia maszynowego:**
    *    Uczenie nadzorowane (uczenie z danymi (dataset), z ingerecją człowieka, oczekiwane wyjście)
    *    Uczenie nienadzorowane (uczenie bez danych, brak oczekiwanego wyjścia, bez ingerncji człowieka)
    *    Uczenie przez wzmacnianie
    *    Uczeie częściowo nadzorowane ( mała ilość danych oznaczonych (np. etykietami), duża ilość danych bez etykiet.  

*   **Uczenie przez wzmacnianie (RL):** Robot (agent) uczy się poprzez interakcję ze środowiskiem, dążąc do maksymalizacji nagrody.
    *   **Przykłady:** Mistrz szachowy podejmujący decyzje intuicyjne, robot odkurzający decydujący o powrocie do bazy na podstawie stanu baterii i doświadczeń z przeszłości. Przykład algorytmu Q-learning, Q==quality, przy wykonaniu ruchu algorytm dostaje nagrodę lub karę.
*   **Uczenie Federacyjne (Federated Learning):** Wiele robotów współdzieli wiedzę, co pozwala na szybszą naukę (np. 5 robotów po 20 prób zamiast jednego robota wykonującego 100 prób).
*   **Deep Learning:** Coraz częściej wkorzystywany do tzw. prymitywów ruchu, np. nauki chwytania nieznanych przedmiotów.

## 4. Percepcja i Widzenie Maszynowe
Systemy wizyjne są kluczowe dla inteligentnej interakcji robota z otoczeniem.

*   **Nowe definicje:**
    *   **Deep learning:** Podzbiór uczenia maszynowego, głębokie sieci neuronowe posiadają strukturę warstwową. Warstwa wejściowa, warstwa/y ukryte, gdzie są przetwarzane dane oraz warstwa wyjściowowa. Przykłady DL to CNN (sieci konwolucyjne), sieci warstwowe czy sieci rekurencyjne
    *   **Bardzo uproszczone definicje:**
       *   **Sieci konwolucyjne (CNN):** Stosowane do analizy obrazu (klasyfikacja lub detekcja). Filtry w warstwach ukrytych szukają cech (najpierw słabsze cechy np. krawędzie, im dalej tym wiecej np. patterny czy całe obiekty). 
       *   **Sieci wielowarstwowe (MLP):** Stosowane głównie do danych tabelarycznych (prosta klasyfikacja lub przewidywanie wartości). Informacja przepływa tylko w jedną stronę ("każdy z każdym"), gdzie kolejne warstwy uczą się łączyć proste dane wejściowe w bardziej złożone zależności.
       *   **Sieci rekurencyjne (RNN):** Stosowane do danych sekwencyjnych, ułożonych w czasie (analiza tekstu, mowy, giełda). Posiadają wewnętrzną "pamięć" (pętlę), dzięki której interpretacja aktualnego słowa lub wartości zależy od tego, co pojawiło się wcześniej.
      

*   **Zadania systemów wizyjnych:** Detekcja obiektów, wyznaczanie ich położenia, detekcja podłoża, unikanie przeszkód, klasyfikacja, segmentacja semantyczna (przypisanie każdego piksela do jakiejś kategorii) oraz odczytywanie ludzkich intencji (HMI).
*   **Zaawansowane algorytmy:**
    *   **OpenPose:** Detekcja postury człowieka przy użyciu sieci neuronowych.
    *   **Object Detection (np. YOLO):** Wykrywanie i nazywanie obiektów (osoby, samochody, znaki).
*   **Fuzja sensoryczna:** Łączenie danych z różnych czujników (np. wizja, LIDAR, IMU (Inertial Measurement Unit: żyroskop, akcelerometr)) w celu uzyskania dokładniejszego obrazu rzeczywistości.

## 5. Nawigacja i SLAM
Inteligentne roboty mobilne muszą potrafić poruszać się w nieznanym środowisku.

*   **SLAM (Simultaneous Localisation and Mapping):** Proces jednoczesnej lokalizacji robota i tworzenia mapy otoczenia.
*   **Typy nawigacji:**
    *   **Topologiczna (jakościowa):** Opis świata jako grafu relacji (punkty orientacyjne, skrzyżowania).
    *   **Metryczna (ilościowa):** Oparta na współrzędnych, odległościach i siatkach regularnych.

## 6. Inteligentne Algorytmy Sterowania
W odróżnieniu od algorytmów klasycznych (np. PID), algorytmy inteligentne wykorzystują:
*   **Sztuczne Sieci Neuronowe (ANN):** Uproszczony model mózgu, służący do przetwarzania nieliniowego, samoorganizacji i generalizacji wiedzy.
*   **Logikę Rozmytą (Fuzzy Logic):** Pozwala na reprezentację wiedzy eksperckiej za pomocą reguł „jeżeli–to” (fuzyfikacja, wnioskowanie, defuzyfikacja).

## 7. Robotyka 4.0 i Systemy Wielorobotowe (MRS)
Współczesna robotyka zmierza w stronę inteligentnych ekosystemów.

*   **Robotyka 4.0:** Integracja AI, Internetu Robotów (IoR), 5G oraz Brain-on-Cloud (BoC).
*   **AMR vs AGV:** Tradycyjne wózki AGV wymagają sztywnej infrastruktury (taśmy, markery). Autonomiczne roboty mobilne **AMR** nawigują za pomocą czujników pokładowych i dynamicznie omijają przeszkody.
*   **Systemy wielorobotowe (MRS):** Grupy robotów współpracujących nad wspólnym celem (np. roje robotów), co podnosi odporność na błędy i efektywność pracy.

---
## 8. Podsumowanie
Na ogół pytanie w śmieszny sposób sformułowane. Treść zrobiona na podstawie prezentacji z wykładów. 
