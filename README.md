# CKR v1.1 – Centrum Kontroli Rodzicielskiej

Lokalne, bezpieczne i niezwykle lekkie narzędzie dla systemu Windows do zarządzania czasem dzieci przed komputerem.

W przeciwieństwie do oficjalnych rozwiązań firmy Microsoft, CKR działa na tradycyjnych kontach lokalnych. Nie wymaga zakładania dzieciom adresów e-mail, kont online ani podpinania kart płatniczych.

## 🌟 Najważniejsze zalety

- **100% Prywatności (Offline)** – Program nie łączy się z internetem. Żadne dane o aktywności Twojego dziecka nie są wysyłane do chmury.
- **Rozwiązania Systemowe** – Narzędzie bazuje na wbudowanych mechanizmach bezpieczeństwa systemu Windows (usługa systemowa, konta lokalne, `net user`), dzięki czemu działa stabilnie i jest odporne na próby wyłączenia przez dziecko.
- **Brak ukrytych opłat** – Całkowicie darmowy program bez reklam, subskrypcji i zbędnych wymagań.
- **Dwa poziomy zabezpieczeń** – Pozwala na ustawienie sztywnych ram godzinowych (np. zakaz grania w nocy) oraz dziennego limitu minut (np. maksymalnie 2 godziny dziennie).
- **Usługa systemowa** – Kontroler czasu działa w tle jako usługa Windows, niewidoczna dla dziecka i odporna na zamknięcie z poziomu Menedżera zadań.

## 🛠️ Jak to działa?

- **Sztywne ramy godzinowe (Bloki)** – Określasz przedziały czasu, w których dziecko może się zalogować (np. 7:00-12:00 oraz 15:00-21:00). Poza tymi godzinami system Windows nie pozwoli na wejście na konto, a trwające sesje zostaną przerwane.
- **Dzienny licznik czasu** – Usługa działająca w tle zlicza minuty spędzone przy komputerze. Po wyczerpaniu limitu, program automatycznie wyloguje użytkownika lub wyłączy komputer (zależnie od wybranej opcji).
- **Konfiguracja w pliku** – Ustawienia przechowywane są w bezpiecznym katalogu `C:\ProgramData\CKR\timetracker.cfg`, dostępnym tylko dla administratora i systemu.

## 🚀 Instrukcja instalacji i uruchomienia

### Krok 1: Wymagania wstępne

Program współpracuje wyłącznie z **kontami lokalnymi** w systemie Windows. Przed uruchomieniem upewnij się, że Twoje dziecko korzysta z konta lokalnego bez uprawnień administratora (konto standardowe).

### Krok 2: Pobranie plików

Pobierz **oba pliki** z sekcji wydań (Releases) tego repozytorium:

- `CKR.exe` – główny program konfiguracyjny (menu tekstowe)
- `TimeTrackerService.exe` – usługa systemowa odpowiedzialna za monitorowanie czasu

Umieść oba pliki w **tym samym folderze** (np. `C:\CKR\`).

### Krok 3: Uruchomienie instalatora

1. Kliknij na plik `CKR.exe` **PRAWYM PRZYCISKIEM MYSZY** i wybierz **"Uruchom jako administrator"** (jest to niezbędne, aby program mógł zarządzać blokadami systemowymi).
2. W menu wybierz opcję **1** – „Instalator systemu kontroli rodzicielskiej”.
3. Wskaż konto dziecka, dla którego ma działać kontrola.
4. Instalator automatycznie:
   - utworzy katalog `C:\ProgramData\CKR`,
   - wygeneruje plik konfiguracyjny `timetracker.cfg` z domyślnymi ustawieniami (bloki: 8–12 i 16–20, limit: 120 minut, akcja: wylogowanie),
   - skopiuje `TimeTrackerService.exe` do katalogu docelowego,
   - zabezpieczy folder przed dostępem dziecka,
   - zainstaluje i uruchomi usługę `CKR_TimeTracker`.

Po zakończeniu instalacji usługa będzie działać automatycznie przy każdym starcie systemu.

### Krok 4: Dostosowanie ustawień (opcjonalne)

Aby zmienić ramy godzinowe, limit minut lub akcję, możesz:

- skorzystać z opcji **2–4** w menu programu `CKR.exe` (po wybraniu konta dziecka),
- albo ręcznie edytować plik `C:\ProgramData\CKR\timetracker.cfg` (np. Notatnikiem) i zrestartować usługę poleceniem:

```sc stop CKR_TimeTracker & sc start CKR_TimeTracker```


## ⚠️ Ważne informacje dotyczące Antywirusów (False Positive)

Pliki wykonywalne programu (`.exe`) zostały stworzone przy użyciu narzędzi do automatyzacji Windows (Batch i .NET). Z tego powodu niektóre programy antywirusowe (w tym Windows Defender) mogą błędnie oznaczyć program jako zagrożenie (tzw. fałszywy alarm / False Positive).

**Program jest w 100% bezpieczny** i nie zawiera żadnego złośliwego kodu. Jeśli Twój antywirus zablokuje uruchomienie:

1. Wejdź w **historię ochrony** swojego programu antywirusowego.
2. Znajdź zablokowany plik `CKR.exe` oraz `TimeTrackerService.exe`.
3. Wybierz opcję **„Zezwól na urządzeniu”** lub dodaj pliki do **wykluczeń** (wyjątków) antywirusa.

## 📄 Licencja

Program udostępniany jest bezpłatnie do użytku osobistego i domowego. Modyfikowanie kodu źródłowego oraz redystrybucja zmienionych wersji są surowo zabronione. Pełną treść warunków znajdziesz w pliku `LICENSE.md`.
