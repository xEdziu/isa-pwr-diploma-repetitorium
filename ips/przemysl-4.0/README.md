<img width="1024" height="768" alt="protokoły transmisji" src="https://github.com/user-attachments/assets/afd7aa9c-4907-4a0b-b59e-eb9bf5018337" />

# Protokoły transmisji cyfrowej w przemyśle 4.0

Protokoły komunikacyjne umożliwiają płynną wymianę danych między maszynami, czujnikami, systemami IT oraz operatorami. Bez skutecznych protokołów wymiany danych implementacja systemów IoT, predykcyjnego utrzymania ruchu czy auto-matyzacji procesów byłaby niemożliwa.

> [!NOTE]
> **Zasada M2M**
> Zasada Machine-to-Machine to w pełni automatyczna wymiana danych między urządzeniami, która redukuje potrzebę interwencji człowieka, optymalizuje procesy produkcyjne oraz skraca czas reakcji na nieprzewidziane sytuacje.


## Rodzaje protokołów komunikacyjnych

### Lokalne

Sieci przemysłowe Ethernet - przeznaczone do bezpośredniej komunikacji między urządzeniami w zakładach produkcyjnych, z niskim opóźnieniem i wysoką niezawodnością (Profinet, EtherCAT, Modbus TCP/IP)

|Cecha|EtherCAT|Profinet|Modbus TCP|
|:---:|:---:|:---:|:---:|
|Czas Reakcji|µs|ms|ms|
|Deterministyczność|bardzo wysoka|średnia|niska|
|Synchronizacja Zegarów|tak|częściowa|brak|
|Zastosowania|robotyka, CNC|automatyka|monitoring|


#### EtherCAT

*Ethernet for Control Automation Technology*, EtherCAT to przemysłowy protokół komunikacyjny opracowany przez firmę Beckhoff do transmisji danych w czasie rzeczywistym; jest to zmodyfikowany *Ethernet*, zoptymalizowany pod kątem przemysłowych aplikacji kontrolnych.

___

### Dedykowane dla IoT

Zapewniają wymianę danych między rozproszonymi urządzeniami, optymalne dla sieci o ograniczonych zasobach (MQTT, CoAP)

#### MQTT

*Message Query Telemetry Transport*, czyli MQTT, to lekki protokół publikowania i subskrybowania (pub/sub), zaprojektowany do komunikacji między urządzeniami o niskiej mocy, doskonały do zastosowań IoT.

Najnowsza wersja tego protokołu to **MQTTv5.0**

___

### Integrujące różne systemy

Umożliwiają połączenie systemów operacyjnych i produkcyjnych z systemami zarządzania (OPC UA)

#### OPC UA

*Open Platform Communications Unified Architecture*, OPC UA to otwarty standard komunikacyjny zaprojektowany do ujednoliconej wymiany danych między różnymi systemami automatyki, niezależnie od ich dostawców. Standard nie tylko obsługuję wymianę danych, ale także ich modelowanie, co umożliwia pełną integrację systemów operacyjnych i IT.

___


### Wysokiej niezawodności i bezpieczeństwie

Wykorzystywane w sektorach wymagających bezpiecznego przesyłu danych (AMQP).

#### AMQP

*Advanced Message Queuing Protocol*, AMQP to otwarty protokół komunikacyjny, głównie dla aplikacji wymagających wysokiej niezawodności i bezpieczeństwa. AMQP jest powszechnie używany w aplikacjach biznesowych, gdzie ważne jest śledzenie i potwierdzanie dostarczania wiadomości. Protokół wspiera zaawansowane kolejkowanie wiadomości, co pozwala na zachowanie integralności danych nawet w przypadku awarii systemu.

## Bezpieczeństwo w komunikacji przemysłowej

- **TLS/SSL** - szyfrowanie kanału, np. MQTT over TLS
- **Uwierzytalnianie certyfikatami X.509**
- **Role użytkowników w OPC UA** - User Access Control
- **Segmentacja Sieci** - strefy i DMZ

### Dobór protokołu

- **MQTT** - lekki protokół typu pub/sub, idealny do IoT, gdzie ważna jest efektywna wymiana danych między rozproszonymi urządzeniami przy niskim poborze energii.
- **EtherCAT** - *Ethernet* przemysłowy, zapewnia wysoką przepustowość i niskie opóźnienia, doskonały do aplikacji wymagającej precyzyjnej synchronizacji i kontroli w czasie rzeczywistym.
- **OPC UA** - protokół umożliwiający integrację systemów produkcyjnych z IT, zapewniający bezpieczeństwo i skalowalność oraz wspierający zaawansowane modelowanie danych.
- **AMQP** - protokół o wysokiej niezawodności i bezpieczeństwie, wykorzystywany głównie w aplikacjach biznesowych, takich jak bankowość i telekomunikacja, dzięki obsłudze kolejek i potwierdzeń dostarczenia
