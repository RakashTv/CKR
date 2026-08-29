# CKR v1.1 – Centrum Kontroli Rodzicielskiej

Lokalne, bezpieczne i niezwykle lekkie narzędzie dla systemu Windows do zarządzania czasem dzieci przed komputerem.

W przeciwieństwie do oficjalnych rozwiązań firmy Microsoft, CKR działa na tradycyjnych kontach lokalnych. Nie wymaga zakładania dzieciom adresów e-mail, kont online ani podpinania kart płatniczych.

## 🌟 Najważniejsze zalety

- **100% prywatności (Offline)** – Program nie łączy się z internetem. Żadne dane o aktywności Twojego dziecka nie są wysyłane do chmury.
- **Rozwiązania systemowe** – Narzędzie bazuje na wbudowanych mechanizmach bezpieczeństwa systemu Windows (`net user`, usługa Windows), dzięki czemu działa stabilnie i nie obciąża komputera.
- **Brak ukrytych opłat** – Całkowicie darmowy program bez reklam, subskrypcji i zbędnych wymagań.
- **Dwa poziomy zabezpieczeń** – Pozwala na ustawienie sztywnych ram godzinowych (np. zakaz grania w nocy) oraz dziennego limitu minut (np. maksymalnie 2 godziny dziennie).
- **Odporność na obejście** – Strażnik działa jako usługa systemowa (SYSTEM), więc dziecko nie może jej zatrzymać z poziomu Menedżera zadań ani zwykłych uprawnień użytkownika.

## 🛠️ Jak to działa?

### Sztywne ramy godzinowe (Bloki)
Określasz przedziały czasu, w których dziecko może się zalogować (np. 7:00–12:00 oraz 15:00–21:00). Poza tymi godzinami system Windows nie pozwoli na wejście na konto, a trwające sesje zostaną przerwane.

### Dzienny licznik czasu
Strażnik działający w tle (usługa Windows `CKR_TimeTracker`) zlicza minuty spędzone przy komputerze. Po wyczerpaniu limitu program automatycznie wyloguje użytkownika lub wyłączy komputer (zależnie od wybranej akcji w konfiguracji).

## 🚀 Instrukcja instalacji i uruchomienia

### Krok 1: Wymagania wstępne
Program współpracuje wyłącznie z kontami lokalnymi w systemie Windows. Przed uruchomieniem upewnij się, że Twoje dziecko korzysta z konta lokalnego bez uprawnień administratora (konto standardowe).

### Krok 2: Pobranie i uruchomienie instalatora
1. Pobierz plik instalatora `CKR_Setup.exe` (lub paczkę z `TimeTrackerService.exe` i skryptem `CKR.bat`).
2. Kliknij na pobrany plik **PRAWYM PRZYCISKIEM MYSZY** i wybierz **„Uruchom jako administrator”** (jest to niezbędne, aby program mógł zarządzać blokadami systemowymi i usługą).
3. W menu głównym wybierz opcję **1. Instalator systemu kontroli rodzicielskiej**.
4. Wskaż konto dziecka – instalator automatycznie utworzy usługę, zapisze domyślne limity (bloki 8:00–12:00 i 16:00–20:00, limit 120 minut) i uruchomi strażnika.
5. Gotowe! Możesz później zmienić godziny, limit lub akcję, korzystając z menu opcji 2–4. Ustawienia są przechowywane w pliku `C:\ProgramData\CKR\timetracker.cfg`.

### Krok 3: Pierwsze logowanie dziecka
Po instalacji usługa wystartuje automatycznie przy każdym uruchomieniu systemu i będzie kontrolować czas dziecka. Nie są wymagane żadne dodatkowe czynności.

## ⚠️ Ważne informacje dotyczące antywirusów (False Positive)

Plik wykonywalny programu (`.exe`) został stworzony przy użyciu technologii automatyzacji i usług systemowych. Z tego powodu niektóre programy antywirusowe (w tym Windows Defender) mogą błędnie oznaczyć program jako zagrożenie (tzw. fałszywy alarm / False Positive).

**Program jest w 100% bezpieczny i nie zawiera żadnego złośliwego kodu.** Jeśli Twój antywirus zablokuje uruchomienie:

1. Wejdź w historię ochrony swojego programu antywirusowego.
2. Znajdź zablokowany plik.
3. Wybierz opcję **„Zezwól na urządzeniu”** lub dodaj plik do wykluczeń (wyjątków) antywirusa.

## 📄 Licencja

Program udostępniany jest bezpłatnie do użytku osobistego i domowego. Modyfikowanie kodu źródłowego oraz redystrybucja zmienionych wersji są surowo zabronione. Pełną treść warunków znajdziesz w pliku `LICENSE.md`.
