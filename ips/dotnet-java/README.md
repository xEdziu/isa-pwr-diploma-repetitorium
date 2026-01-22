# Cechy wspólne i różnice platform programistycznych .Net i Java. Obiektowość w językach Java i C#

> Będzie trochę chaotycznie ale postaram się jak mogę zrobić to jak najkrócej


## Architektura i przenośność platform

### Cechy Wspólne

- **Wirtualna maszyna uruchomieniowa**
    - `CLR` (Common Language Runtime) dla .NET
    - `JVM` (Java Virtual Machine) dla Java
- **Kompilacja do kodu pośredniego**
    - `CIL` (Common Intermediate Language) dla .NET
    - `bytecode` (czyli wynik kompilacji do pliku `.class`) dla Java
- **Garbage Collector (GC)**
- **JIT compiler** (Just-In-Time compilation)
- **Multiplatformowość**
    - Java z natury od samego początku była multiplatformowa, JVM była dostępna wszędzie
    - .NET dopiero od niedawna jest multiplatformowy

### Różnice

#### Java
- zdecydowanie bardziej stabilna niż .NET
- dominuje w androidzie
- kompatybilność wsteczna
#### .NET
- wielojęzykowość (C#, F#)
- open-source od 2016 roku
  

## Obiektowość

### Wspólne fundamenty

Oba języki są bardzo podobne do siebie. Przejście z jednego na drugi nie powinno zająć jakoś specjalnie dużo czasu.

- Są w pełni obiektowe
- Statycznie typowane
- Zorientowanę na klasę
- Obsługują wyjątki
- Posiadają klasy abstrakcyjne i interfejsy
- Zgodne z OOP: Enkapsulacja, Dziedziczenie, Polimorfizm

### Bardziej szczegółowe podobieństwa

- Oba języki wspierają przetwarzanie strumieniowe i filtrację danych
- W obu językach interfejsy są zbliżone, różnice głównie syntaktyczne. C# często stosuje przedrostek „I”.
- abstract i sealed/final mają podobne znaczenie w obu językach, różni się jedynie składnia
- Obie platformy oferują zarówno niskopoziomowy dostęp do bazy, jak i zaawansowane narzędzia ORM (Object Relation Mapping) – pozwalające odwzorować tabele na obiekty klas.
- Obie platformy mają swoje biblioteki do GUI (Graphic User Interface) oraz do technologii webowych

### Różnice w języku programowania

- C# posiada skróconą składnię właściwości (auto-properties), podczas gdy w Javie dominuje podejście z ręcznym tworzeniem getterów/setterów.
- W C# trzeba jawnie zaznaczyć możliwość nadpisania metod słowem virtual. W Javie każda metoda jest domyślnie wirtualna (chyba że ma słówko final).
