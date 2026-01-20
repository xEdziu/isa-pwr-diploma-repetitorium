<img width="1358" height="1015" alt="image" src="https://github.com/user-attachments/assets/f8a07d04-3d89-4e2d-8ff5-9939776c39b7" />


### 1. Przegląd i definicja Systemu Operacyjnego

System operacyjny (SO) to oprogramowanie (program), które zarządza całym systemem komputerowym, obejmując zarówno sprzęt, jak i oprogramowanie. Jego głównym celem jest udostępnianie zasobów komputera oraz jego funkcji użytkownikowi.

Kluczową funkcją systemu operacyjnego jest tworzenie środowiska, które umożliwia uruchamianie i wykonywanie innych zadań, czyli programów.

### 2. Zadania Systemu Operacyjnego

Prezentacja wymienia osiem głównych zadań realizowanych przez system operacyjny:

1. **Zarządzanie procesami:** Tworzenie, obsługa oraz kontrola procesów.
2. **Planowanie czasu procesora:** Przydzielanie czasu procesora do poszczególnych zadań (procesów).
3. **Synchronizacja i komunikacja:** Zapewnienie mechanizmów synchronizacji procesów oraz komunikacji międzyprocesowej.
4. **Zarządzanie pamięcią:** Przydział pamięci operacyjnej do zadań, a także jej kontrola i obsługa.
5. **Obsługa sprzętu:** Dostarczanie jednolitego interfejsu do obsługi sprzętu (np. poprzez sterowniki).
6. **Zarządzanie plikami:** Obsługa systemów plików.
7. **Obsługa sieci:** Zarządzanie połączeniami i komunikacją w sieci komputerowej.
8. **Bezpieczeństwo:** Zapewnienie bezpieczeństwa danych (pamięć, pliki) oraz autoryzacja dostępu.

### 3. Struktura Systemu Operacyjnego

System operacyjny składa się z czterech podstawowych elementów:

1. **Jądro (kernel)**
2. **Powłoka (shell)**
3. **System plików**
4. **Pozostałe oprogramowanie systemowe**

#### A. Jądro (Kernel)

Jest to podstawowa część systemu operacyjnego. Jądro pracuje w trybie uprzywilejowanym, co oznacza, że ma pełny dostęp do zasobów sprzętowych. Aplikacje użytkownika (w tym powłoka) korzystają z usług jądra poprzez jego API, czyli tzw. **wywołania systemowe**.

Wyróżniamy trzy główne rodzaje jąder (architektury):

**Jądro monolityczne:**
* To pojedynczy obraz w pamięci, który obsługuje „wszystkie” funkcje: od planisty i pamięci, po sieć, sterowniki i systemy plików.
* **Zalety:** Wysoka wydajność, prostota i łatwość komunikacji między elementami jądra.
* **Wady:** Podatność na błędy – awaria jednego modułu może zaważyć na stabilności całego systemu, ponieważ wszystko działa w jednej przestrzeni.
* **Przykłady:** Linux, FreeBSD.

**Mikrojądro:**
* Wykonuje tylko nieliczne, podstawowe funkcje (np. obsługa wątków, IPC, planista).
* Reszta funkcji (np. system plików, sterowniki) jest obsługiwana przez serwery działające w przestrzeni użytkownika.
* **Zalety:** Większa odporność na błędy (awaria sterownika nie musi wywalać całego systemu).
* **Wady:** Niższa wydajność ze względu na narzut komunikacji między modułami.
* **Przykłady:** MINIX, QNX, Mach.

**Jądro hybrydowe:**
* Łączy idee jądra monolitycznego i mikrojądra.
* Jądro składa się z wielu osobnych elementów (obszarów pamięci), co zmniejsza skutki błędów, ale zachowuje dużą wydajność.
* **Przykłady:** Windows, macOS (choć ten ostatni ma specyficzną budowę opartą na Mach).

#### B. Powłoka (Shell)

Jest to oprogramowanie pośredniczące między użytkownikiem a systemem operacyjnym. Może przyjmować różne formy interfejsu:

* **CLI (Command-Line Interface):** Wiersz poleceń, np. `bash`, `zsh`, `sh`.
* **GUI (Graphical User Interface):** Interfejs graficzny.
* **TUI (Text User Interface):** Interfejs tekstowy.

W wąskim znaczeniu powłoka to interpreter komend.

#### C. System Plików

**Definicja i rola:**

* Jest to warstwa odpowiedzialna za **zarządzanie plikami**.
* Organizuje sposób zapisu danych na nośnikach pamięci masowej, umożliwiając ich gromadzenie, pobieranie i aktualizację.

**Porównanie systemów plików (FAT32 vs NTFS):**

| Cecha | **FAT32** | **NTFS** |
| --- | --- | --- |
| **Zastosowanie** | Mniejsze dyski, karty pamięci, pendrive'y, urządzenia wbudowane. | Większe dyski twarde, partycje systemowe Windows. |
| **Wydajność** | Dobra dla małych partycji. Niewydajny dla dużych partycji. | Efektywny dla dużych dysków i dużych plików. Niewydajny dla bardzo małych partycji (<400MB). |
| **Ograniczenia** | Posiada limity dotyczące maksymalnego rozmiaru pojedynczego pliku (4GB) oraz rozmiaru partycji. | Obsługuje bardzo duże pliki i partycje. |
| **Bezpieczeństwo** | Brak rozbudowanych funkcji zabezpieczeń. | Zaawansowane funkcje: uprawnienia do plików (ACL), szyfrowanie, funkcje naprawy systemu (journaling). |
| **Kompatybilność** | **Wysoka (Uniwersalny).** Działa na większości systemów (Windows, macOS, Linux, konsole). | Specyficzny dla Windows. Inne systemy (np. macOS) mogą mieć problem z zapisem na partycjach NTFS (często tylko odczyt). |

### D. Pozostałe Oprogramowanie Systemowe

Jest to czwarty element składowy systemu operacyjnego wymieniony w strukturze SO. Obejmuje ono programy i biblioteki, które nie są częścią jądra, ale są niezbędne do funkcjonowania systemu i pracy użytkownika.

1. **Biblioteki systemowe (np. `glibc`, `libpthread`):**
* Stanowią warstwę pośrednią między aplikacjami a jądrem systemu.
* Aplikacje użytkownika rzadko wywołują funkcje jądra bezpośrednio; zamiast tego korzystają z "wrapperów" (funkcji pakujących) dostępnych w bibliotekach.
* Przykład: Funkcja `printf` w języku C korzysta z wywołania systemowego `write`, ale programista używa biblioteki standardowej, a nie bezpośrednio jądra.


2. **Demony (Daemons):**
To procesy działające w tle, które wykonują zadania systemowe bez bezpośredniej interakcji z użytkownikiem.
* Przykłady wymienione w prezentacji:
* `init` (lub `systemd`): Pierwszy proces w systemie (PID 1), rodzic wszystkich innych procesów.
* `kerneld`: Demon do automatycznego ładowania modułów jądra.
* `cron`: Demon do harmonogramowania zadań (uruchamianie skryptów o określonej porze).

3. **Programy narzędziowe i systemowe:**
* Narzędzia do zarządzania plikami i procesami, które użytkownik uruchamia z poziomu powłoki.
* Przykłady: `ls`, `cp`, `ps`, `top`, kompilatory, edytory tekstu.
* Mimo że są kluczowe dla pracy, działają one w **przestrzeni użytkownika** (User Space), a nie w przestrzeni jądra.

**Podsumowanie struktury pod egzamin:**

1. **Jądro** (zarządza sprzętem).
2. **Powłoka** (interfejs dla użytkownika).
3. **System plików** (organizacja danych).
4. **Pozostałe oprogramowanie systemowe** (biblioteki, demony, narzędzia).
