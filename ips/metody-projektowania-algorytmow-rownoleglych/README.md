<img width="1024" height="731" alt="mapa-mysli-programowanie-rownolegle" src="https://github.com/user-attachments/assets/3f577763-9f07-4ea1-a7b6-4a2a822b97de" />

#### Projektowanie algorytmu równoległego obejmuje:

1. wybór modelu architektury
2. podział problemu (dane / zadania)
3. minimalizację komunikacji
4. synchronizację tylko tam, gdzie konieczna
5. ocenę jakości (speedup, efektywność)
6. analizę granic skalowalności

# Najważniejsze zagadnienia

## Architektury systemów wieloprocesorowych - od procesorów wielordzeniowych, przez GPU po klastry i superkopmputery. Model PRAM.

### Architektury systemów równoległych

- **Procesory wielordzeniowe (CPU)**
  - kilka rdzeni, wspólna pamięć RAM
  - niski koszt komunikacji
  - typowe mechanizmy: wątki, sekcje krytyczne, semafory
- **GPU**
  - bardzo duża liczba prostych rdzeni
  - model SIMD/SIMT (SIMD – Single Instruction, Multiple Data; SIMT – Single Instruction, Multiple Threads)
  - opłacalne dla obliczeń masowych (macierze, obrazy)
- **Klastry / systemy rozproszone**
  - wiele komputerów połączonych siecią
  - pamięć rozproszona
  - komunikacja jawna (wiadomości)
  - **np. superkomputer w WCSS na PWr**

### Model PRAM (Parallel Random Access Machine)

Model teoretyczny używany do projektowania i analizy algorytmów równoległych.

- zakłada:
  - nieskończoną liczbę procesorów
  - wspólną pamięć
  - brak kosztów komunikacji
- służy do:
  - projektowania algorytmów
  - analizy złożoności czasowej
  - porównywania rozwiązań

Warianty PRAM:

- **EREW** – brak współdzielonego odczytu i zapisu
- **CREW** – współdzielony odczyt, wyłączny zapis
- **CRCW** – współdzielony odczyt i zapis

PRAM nie służy do implementacji, lecz do **projektowania algorytmów**.

## Środowiska z pamięcią współdzieloną i rozproszoną - różnice w programowaniu

### Pamięć współdzielona

- wszystkie wątki/procesy widzą te same dane
- konieczna synchronizacja:
  - lock
  - semafory
  - bariery
- zagrożenia:
  - race condition
  - zakleszczenia
  - wąskie gardła

Przykład: wielowątkowa symulacja (Task, SemaphoreSlim)

### Pamięć rozproszona

- każdy proces ma własną pamięć
- komunikacja przez:
  - komunikaty
  - sieć
- brak wyścigów danych, ale:
  - wysoki koszt komunikacji
  - konieczność dzielenia i scalania danych

Przykład: podział obrazu na fragmenty i przetwarzanie na wielu węzłach

## Miary jakości algorytmów współbieżnych (przyspieszenie, efektywność, koszt)

Zakładając, że p oznacza liczbę jednostek wykonawczych użytych w obliczeniach równoległych np. liczba rdzeni, wątków, procesorów.

### Przyspieszenie (Speedup)

S(p) = T(1) / T(p)

- określa ile razy algorytm równoległy jest szybszy od sekwencyjnego
- idealnie: S(p) = p

### Efektywność (Efficiency)

E(p) = S(p) / p

- informuje jak dobrze wykorzystano procesory
- E = 1 → idealne wykorzystanie
- E < 1 → narzuty komunikacji i synchronizacji

### Koszt obliczeń

C(p) = p × T(p)

- pozwala ocenić opłacalność równoległości
- dobry algorytm ma koszt zbliżony do sekwencyjnego

## Granice zwrównoleglania obliczeń - anomalia przyśpieszenia ponadliniowego

### Prawo Amdahla

- część sekwencyjna ogranicza maksymalne przyspieszenie
- nawet nieskończona liczba procesorów nie daje nieskończonego speedupu

### Prawo Gustafsona

- przy większym problemie równoległość staje się bardziej opłacalna

### Przyspieszenie ponadliniowe

Może wystąpić, gdy:

- lepsze wykorzystanie pamięci cache
- zmiana algorytmu w wersji równoległej
- mniejsze dane lokalne

Nie łamie praw teorii – wynika z architektury sprzętu.

---
# Zagadnienia ważne jeśli będą pytania o konkretne algorytmy - najważniejsze wiedzieć o macierzach i jednym jeszcze przykładzie np quicksorcie

### Równoległe algorytmy grafowe. Wyznaczanie najkrótszych/najdłuższych ścieżek w sieciach

### Problemy grafowe

- BFS
- najkrótsza ścieżka
- najdłuższa ścieżka (DAG)

### Metody równoleglenia

- przetwarzanie warstwowe (frontier-based)
- równoległe relaksacje krawędzi
- synchronizacja po każdej iteracji

Trudność:

- nieregularny dostęp do danych
- zależności między wierzchołkami

### Równoległe algorytmy sortowania. Sortowanie "parzyste-nieparzyste". Równoległy algorytm quicksort.

### Sortowanie parzyste–nieparzyste

- algorytm iteracyjny
- w każdej fazie:
  - równoległe porównania parzyste
  - potem nieparzyste
- prosta synchronizacja
- dobra ilustracja fazowości algorytmu

### Równoległy quicksort

- równoległy podział danych
- rekurencyjne wywołania mogą działać współbieżnie
- problemy:
  - nierówny podział
  - obciążenie procesorów

### Równoległe rozwiązywania układów równań liniowych. Algorytmy macierzowe.

### Algorytmy macierzowe

- mnożenie macierzy
- eliminacja Gaussa
- dekompozycje (LU)

### Metody równoleglenia

- podział macierzy na bloki
- każdy wątek/proces liczy fragment
- synchronizacja po etapach

Szczególnie efektywne na:

- GPU
- systemach wielordzeniowych

--- 
# Zagadnienia uzupełniające

## Programowanie w klastrze – biblioteka MPI

### Charakter zagadnienia
- MPI to standard komunikacji w systemach z pamięcią rozproszoną
- programista jawnie:
  - przesyła dane
  - synchronizuje procesy

### Związek z metodami projektowania
- wymusza:
  - dekompozycję danych
  - minimalizację komunikacji
- silnie eksponuje koszty przesyłania danych

### Znaczenie dla projektowania
- algorytmy projektowane dla pamięci rozproszonej:
  - muszą redukować liczbę komunikatów
  - muszą dobrze dzielić dane

MPI nie definiuje metody algorytmicznej, ale **ujawnia konsekwencje złego projektu algorytmu**.

## Programowanie urządzeń GPU – CUDA

### Charakter zagadnienia
- CUDA to platforma programistyczna dla GPU
- oparta na modelu SIMT

### Związek z projektowaniem algorytmów
- wymusza:
  - bardzo drobnoziarnisty podział problemu
  - regularny dostęp do danych
- nie każdy algorytm da się efektywnie zrównoleglić na GPU

### Ograniczenia projektowe
- koszt transferu danych CPU ↔ GPU
- problem rozbieżności wątków (branch divergence)

CUDA nie jest metodą projektowania algorytmu, lecz **specyficznym środowiskiem wykonawczym**, które wpływa na sposób implementacji.

## Programowanie MIC – OpenMP

### Charakter zagadnienia
- OpenMP to model programowania dla pamięci współdzielonej
- opiera się na dyrektywach (pragma)

### Związek z projektowaniem
- umożliwia szybkie:
  - równoleglenie pętli
  - eksperymenty z liczbą wątków
- nie zmusza do zmiany struktury algorytmu

### Ograniczenia
- łatwo uzyskać:
  - niską efektywność
  - wąskie gardła
- nadmierna synchronizacja obniża skalowalność

OpenMP realizuje algorytmy współbieżne i równoległe, ale **nie definiuje metod ich projektowania**.

## Wybrane algorytmy równoległe – metaheurystyki

### Charakter zagadnienia
- algorytmy przybliżone
- stosowane do problemów NP-trudnych

### Równoleglenie metaheurystyk
- równoległa:
  - ewaluacja rozwiązań
  - przegląd sąsiedztwa
  - operacje na populacji

### Związek z metodami projektowania
- wykorzystują klasyczne techniki:
  - dekompozycję zadań
  - brak zależności danych
- są przykładem zastosowania metod, a nie ich źródłem

Metaheurystyki ilustrują użycie metod projektowania, ale same nimi nie są.

## Równoległy i rozproszony algorytm tabu search oraz symulowanego wyżarzania

### Charakter zagadnienia
- algorytmy lokalnego przeszukiwania
- silnie sekwencyjne w swojej naturze

### Możliwości równoleglenia
- równoległa analiza sąsiedztwa
- równoległa ewaluacja funkcji celu
- wersje wyspowe (rozproszone)

### Ograniczenia projektowe
- zależności między iteracjami
- ograniczona skalowalność

Algorytmy te pokazują **granice zwrównoleglania**, co jest istotne koncepcyjnie.

## Równoległe algorytmy genetyczne i poszukiwanie rozproszone

### Charakter zagadnienia
- algorytmy populacyjne
- naturalnie podatne na równoleglenie

### Modele równoległe
- model master–slave
- model wyspowy
- model globalnej populacji

### Związek z projektowaniem algorytmów
- dobre przykłady:
  - dekompozycji danych
  - ograniczania synchronizacji
- jednak silnie dziedzinowe

Algorytmy genetyczne są **zastosowaniem metod projektowania algorytmów równoległych**, a nie ich fundamentem.
