# CKR v1.1 – Centrum Kontroli Rodzicielskiej

Lokalne, bezpieczne i niezwykle lekkie narzędzie dla systemu Windows do zarządzania czasem dzieci przed komputerem.

W przeciwieństwie do oficjalnych rozwiązań firmy Microsoft, CKR działa na tradycyjnych kontach lokalnych. Nie wymaga zakładania dzieciom adresów e-mail, kont online ani podpinania kart płatniczych.

## 🌟 Najważniejsze zalety

- **100% Prywatności (Offline)** – Program nie łączy się z internetem. Żadne dane o aktywności Twojego dziecka nie są wysyłane do chmury.
- **Rozwiązania Systemowe** – Narzędzie bazuje na wbudowanych mechanizmach bezpieczeństwa systemu Windows, dzięki czemu działa stabilnie i nie obciąża komputera.
- **Brak ukrytych opłat** – Całkowicie darmowy program bez reklam, subskrypcji i zbędnych wymagań.
- **Dwa poziomy zabezpieczeń** – Pozwala na ustawienie sztywnych ram godzinowych oraz dziennego limitu minut.
- **Usługa systemowa** – Kontroler czasu działa w tle jako usługa Windows, niewidoczna dla dziecka i odporna na zamknięcie z poziomu Menedżera zadań.

## 🛠️ Jak to działa?

- **Sztywne ramy godzinowe (Bloki)** – Określasz przedziały czasu, w których dziecko może się zalogować (np. 7:00-12:00 oraz 15:00-21:00). Poza tymi godzinami system Windows nie pozwoli na wejście na konto, a trwające sesje zostaną przerwane.
- **Dzienny licznik czasu** – Usługa działająca w tle zlicza minuty spędzone przy komputerze. Po wyczerpaniu limitu program automatycznie wyloguje użytkownika lub wyłączy komputer.
- **Prosta konfiguracja** – Wszystkie ustawienia zmienisz wygodnie w menu programu, bez zaglądania do plików systemowych.

## 🚀 Instrukcja instalacji i uruchomienia

### Krok 1: Wymagania wstępne

Program współpracuje wyłącznie z **kontami lokalnymi** w systemie Windows. Przed uruchomieniem upewnij się, że Twoje dziecko korzysta z konta lokalnego bez uprawnień administratora.

### Krok 2: Pobranie plików

Pobierz **oba pliki** z sekcji wydań (Releases):

- `CKR.exe` – główny program konfiguracyjny
- `TimeTrackerService.exe` – usługa systemowa monitorująca czas

Umieść oba pliki w **tym samym folderze** (np. `C:\CKR`).

### Krok 3: Uruchomienie instalatora

1. Kliknij na plik `CKR.exe` **PRAWYM PRZYCISKIEM MYSZY** i wybierz **„Uruchom jako administrator”**.
2. W menu wybierz opcję **1 – Instalator systemu kontroli rodzicielskiej**.
3. Wskaż konto dziecka, dla którego ma działać kontrola.
4. Instalator automatycznie:
   - utworzy bezpieczny katalog `C:\ProgramData\CKR`,
   - zapisze domyślne ustawienia (bloki: 8–12 i 16–20, limit: 120 minut, akcja: wylogowanie),
   - skopiuje `TimeTrackerService.exe`,
   - zabezpieczy folder przed dostępem dziecka,
   - zainstaluje i uruchomi usługę `CKR_TimeTracker`.

Po zakończeniu instalacji usługa będzie działać automatycznie przy każdym starcie systemu.

### Krok 4: Dostosowanie ustawień

Aby zmienić ramy godzinowe, limit minut lub akcję, uruchom ponownie `CKR.exe` jako administrator i skorzystaj z opcji **2–4** w menu. Program sam zapisze zmiany i zrestartuje usługę.

## ⚠️ Ważne informacje dotyczące Antywirusów (False Positive)

Pliki wykonywalne programu (`.exe`) zostały stworzone przy użyciu narzędzi do automatyzacji Windows. Z tego powodu niektóre programy antywirusowe (w tym Windows Defender) mogą błędnie oznaczyć program jako zagrożenie (tzw. fałszywy alarm).

**Program jest w 100% bezpieczny** i nie zawiera żadnego złośliwego kodu. Jeśli Twój antywirus zablokuje uruchomienie:

1. Wejdź w **historię ochrony** swojego programu antywirusowego.
2. Znajdź zablokowany plik `CKR.exe` oraz `TimeTrackerService.exe`.
3. Wybierz opcję **„Zezwól na urządzeniu”** lub dodaj pliki do **wykluczeń**.

## 📄 Licencja

Program udostępniany jest bezpłatnie do użytku osobistego i domowego. Modyfikowanie kodu źródłowego oraz redystrybucja zmienionych wersji są surowo zabronione. Pełną treść warunków znajdziesz w pliku `LICENSE.md`.
