#<img width="1024" height="768" alt="Mobilki" src="https://github.com/user-attachments/assets/fe5bb450-b925-4cde-a285-2e897adf7744" />

 Czym są nowoczesne platformy mobilne
Nowoczesne platformy mobilne to systemy operacyjne i środowiska sprzętowo-programowe przeznaczone głównie na:
- smartfony
- tablety
- urządzenia ubieralne (smartwatche)

Najważniejsze cechy:
- praca na ograniczonych zasobach (energia, pamięć)
- obsługa interfejsu dotykowego
- silna integracja z czujnikami (GPS, kamera, akcelerometr)
- wysoki nacisk na bezpieczeństwo i prywatność

# Najważniejsze platformy mobilne
Android
- najpopularniejszy system mobilny na świecie
- oparty na jądrze Linux
- otwarty ekosystem (AOSP)
- duża liczba producentów i urządzeń

iOS
- system mobilny firmy Apple
- zamknięty ekosystem
- działa tylko na urządzeniach Apple
- silny nacisk na bezpieczeństwo i spójność

# Architektura systemu Android
Android ma warstwową architekturę, np.:
- jądro Linux (zarządzanie sprzętem)
- biblioteki systemowe
- środowisko uruchomieniowe (ART)
- framework aplikacji
- aplikacje użytkownika

Dzięki temu:
- aplikacje są izolowane od siebie
- system jest stabilny i bezpieczny

# Architektura systemu iOS
iOS ma warstwową architekturę systemu, podobnie jak Android, np.:
- jądro XNU (Unix-based) (zarządzanie procesami, pamięcią, sprzętem)
- warstwa Core OS (niskopoziomowe usługi systemowe, bezpieczeństwo, sandboxing)
- warstwa Core Services (podstawowe usługi systemowe, np. obsługa sieci, plików, baz danych)
- warstwa Media (grafika 2D/3D, audio, wideo)
- warstwa Cocoa Touch (framework aplikacji, interfejs użytkownika, obsługa zdarzeń)
- aplikacje użytkownika

Dzięki temu:
- aplikacje są uruchamiane w izolowanych środowiskach (sandbox)
- system ma wysoki poziom bezpieczeństwa
- Apple ma pełną kontrolę nad sprzętem i oprogramowaniem
- aplikacje działają stabilnie i przewidywalnie

# Różnice: system mobilny vs komputerowy
Najważniejsze różnice:
- sterowanie dotykiem zamiast myszy i klawiatury
- cykl życia aplikacji (aplikacja może być wstrzymana lub zabita)
- ograniczenia baterii
- większe znaczenie optymalizacji
- inne podejście do wielozadaniowości

To wymusza inne podejście do projektowania aplikacji.

# Cechy nowoczesnych aplikacji mobilnych
- reagują na zmianę orientacji ekranu
- obsługują różne rozmiary urządzeń
- wykorzystują czujniki i multimedia
- są energooszczędne
- komunikują się z internetem i API
