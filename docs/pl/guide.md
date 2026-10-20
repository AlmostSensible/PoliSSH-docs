# Instrukcja obsługi

Instrukcja dla macOS 14+ i Apple Silicon. Funkcje oznaczone jako **Niewydane** mogą być nieobecne w Twojej kompilacji. Zobacz [dostępność](../status.md).

## Aktualizacje poza App Store

Od wersji 0.17.0 natywna aplikacja ma **PoliSSH → Sprawdź aktualizacje…**. W **Ustawienia → Ogólne → Aktualizacje** można włączyć lub wyłączyć automatyczne sprawdzanie. Instalacja wymaga potwierdzenia i ponownego uruchomienia aplikacji; wcześniej zakończ sesje i transfery.

Wersje 0.16.1 i starsze nie zawierają aktualizatora. Pierwszą wersję z aktualizacjami zainstaluj ręcznie: rozpakuj oficjalną paczkę ZIP i skopiuj `PoliSSH.app` do katalogu Aplikacje, zastępując poprzednią aplikację po jej zamknięciu. Późniejsze wydania można instalować przez aktualizator. Dostępne paczki opisuje [strona dostępności](../status.md). Wersja deweloperska SwiftPM nie zawiera aktualizatora.

## Pierwsze połączenie

1. Otwórz aplikację i wybierz **Nowy host**.
2. Nadaj rozpoznawalną nazwę. Wpisz adres serwera, port SSH (zwykle `22`) i nazwę użytkownika.
3. Wybierz profil uwierzytelniania albo dodaj go w sekcji **Uwierzytelnianie**.
4. Zapisz i otwórz hosta.
5. Przy pierwszym połączeniu porównaj odcisk klucza SSH ze znaną, zaufaną wartością otrzymaną od administratora serwera.
6. Odpowiedz na pytania o hasło, passphrase klucza lub uwierzytelnianie interaktywne.

Po połączeniu wybierz **Terminal**, **Pliki** albo **Terminal + pliki**. Przełączanie widoku zachowuje połączenie i stan paneli plików.

Szybkie połączenie otworzysz przez `⌘K`. Przykład:

```text
ssh user@example.com -p 2222
```

Możesz też podać `user@example.com` lub wyszukać zapisany host albo sesję. Zapisany host korzysta ze swojego profilu. **Połącz bez zapisywania** korzysta z ssh-agent i nie dodaje hosta do biblioteki. `example.com` jest przykładowym adresem — zastąp go własnym serwerem.

## Hosty i uwierzytelnianie

Porządkuj hosty przy użyciu grup, tagów i ulubionych. Biblioteka ma widok listy oraz kafelków. Wyszukiwanie obejmuje nazwy, adresy, grupy i tagi. Otwarcie hosta z działającą sesją przechodzi do tej sesji.

Profile w sekcji **Uwierzytelnianie** można przypisywać do wielu hostów:

| Metoda | Co przygotować |
| --- | --- |
| Hasło | Hasło konta SSH. |
| Klucz OpenSSH | Klucz prywatny i jego passphrase, jeśli jest zaszyfrowany. Aplikacja może wygenerować klucz Ed25519 i wyeksportować jego część publiczną. |
| ssh-agent | Działający agent z wczytanym odpowiednim kluczem. |
| Keyboard-interactive | Odpowiedzi na pytania serwera, w tym obsługiwane pytania 2FA. |

Hasła i klucze prywatne są zapisywane w pęku kluczy macOS. Usuwanie profilu pokazuje zależne hosty i wymaga potwierdzenia. Hosty pozostają zapisane, ale przed kolejnym połączeniem trzeba wybrać inne uwierzytelnianie. Otwarte sesje pozostają aktywne.

Sekcja **Znane hosty** pokazuje zapamiętane odciski serwerów. Zapomnienie odcisku wymaga potwierdzenia i powoduje ponowne pytanie przy następnym połączeniu. Zmieniony klucz nie jest akceptowany automatycznie.

### Import konfiguracji OpenSSH

W menu **…** biblioteki hostów wybierz **Importuj konfigurację SSH…**. Wskaż plik konfiguracji UTF-8 lub wklej jego treść, sprawdź podgląd i ostrzeżenia, a następnie wybierz **Importuj zaznaczone**. Istniejące hosty pozostają zapisane, a duplikaty są pomijane.

Importer odczytuje konkretne wpisy `Host` z `HostName`, `User` i `Port`. Nie stosuje wzorców, dziedziczonych ustawień, kluczy ani pozostałych dyrektyw. Importowane hosty używają ssh-agent; przed połączeniem sprawdź ich ustawienia i w razie potrzeby przypisz profil uwierzytelniania.

## Terminal

Otwieraj wiele kart połączeń. `⌘T` tworzy lokalny terminal. Przycisk podziału pozwala umieścić panele obok siebie albo nad sobą. Kliknij panel, aby kierować do niego akcje terminala i wstawiane polecenia.

`⌘F` wyszukuje w wyjściu terminala. Czcionkę, kursor, historię ekranu i zachowanie myszy zmienisz w **Ustawienia → Terminal**. Wyłącz **Używaj Option jako Meta**, jeśli chcesz wpisywać polskie znaki z Option.

W menu **…** wybierz **Zapisuj sesję**, aby wskazać miejsce zapisu logu. To samo menu pozwala zatrzymać nagrywanie. Log zawiera wyjście terminala i może obejmować treść poleceń.

### Ponowne połączenie

Automatyczne wznawianie SSH jest domyślnie włączone. Po utracie transportu aplikacja pokazuje odliczanie z możliwością anulowania. Wykonuje do pięciu prób po 2, 4, 8, 16 i 30 sekundach. **Połącz ponownie** rozpoczyna próbę od razu.

Wznowienie otwiera nową powłokę w tej samej karcie, zachowując widoczną historię. Nie powtarza poleceń startowych i nie wznawia automatycznie transferów, tuneli ani nagrywania. Początkowe błędy uwierzytelniania i tożsamości serwera nie są automatycznie ponawiane. Aby proces zdalny przetrwał utratę połączenia, potrzebuje odpowiedniego środowiska na serwerze, np. osobno skonfigurowanej sesji tmux.

## Nowe narzędzia terminala — niewydane

Poniższych kontrolek może nie być w starszej kompilacji. Jeśli nie podano inaczej, dotyczą terminali lokalnych oraz SSH.

### Podświetlanie wzorców i regexy

Otwórz **Ustawienia → Terminal → Podświetlanie wzorców**. Każda reguła ma przełącznik, wzorzec, kolor i dwie opcje:

- **Regex** interpretuje wzorzec jako wyrażenie regularne. Po wyłączeniu szuka tekstu dosłownie.
- **Aa** rozróżnia wielkość liter.

Przykłady:

| Wzorzec | Regex | Efekt |
| --- | --- | --- |
| `ERROR` | Wyłączony | Dopasowuje także fragment dłuższego słowa. |
| `\bERROR\b` | Włączony | Dopasowuje całe słowo `ERROR`. |
| `\b(ERROR|WARNING)\b` | Włączony | Dopasowuje jeden z dwóch poziomów komunikatu. |
| `\b(?:\d{1,3}\.){3}\d{1,3}\b` | Włączony | Podświetla tekst podobny do IPv4; nie sprawdza poprawności zakresów adresu. |
| `\bsuccess\b` | Włączony | Dopasowuje `success`, ale pomija fragment nazwy `.sudo_as_admin_successful`. |

Nowe reguły domyślne dopasowują całe słowa. Wcześniej zapisane reguły literalne pozostają literalne. Limit to 12 reguł po 128 znaków. Dopasowanie działa w poszczególnych widocznych wierszach i nie łączy tekstu przez zawinięcie linii. Puste dopasowania są pomijane. Błędny regex pokazuje komunikat. Reguła przekraczająca limit czasu zostaje wstrzymana z ostrzeżeniem do czasu edycji reguł.

Podświetlenie nie zmienia wyjścia terminala, kopiowanego tekstu ani atrybutów ANSI. Nakładka pomija wiersze z tekstem dwukierunkowym.

### Podgląd wklejania

**Sprawdzaj wklejanie wielu wierszy** jest domyślnie włączone. Wklejenie znaków końca linii lub sterujących otwiera podgląd — przez klawiaturę, menu kontekstowe lub skonfigurowane wklejanie prawym przyciskiem.

**Anuluj** niczego nie wysyła. **Wklej** wysyła dokładnie przejrzaną zawartość schowka. Zależnie od obsługi bracketed paste przez powłokę, znaki końca linii mogą wykonać polecenia. Rozłączenie unieważnia otwarty podgląd.

### Klikalne pliki i błędy

Przytrzymaj `⌘` i kliknij wykryte odwołanie, np.:

```text
/var/log/nginx/error.log
config.php:42
config.php:42:7
```

Zdalny plik UTF-8 otworzy się w edytorze SFTP. Numer wiersza i opcjonalnej kolumny ustawią kursor w odpowiednim miejscu. Ścieżki absolutne działają bez znajomości katalogu. Ścieżki względne wymagają zgłoszenia bieżącego katalogu przez integrację z powłoką albo OSC 7; aplikacja nie zgaduje go ze znaku zachęty. Linki mają subtelne podkreślenie i kursor wskazującej dłoni. Pliki lokalne otwierają się w domyślnej aplikacji macOS.

### Integracja z powłoką i historia poleceń

Przy **gotowym znaku zachęty zsh albo Bash 4.4+** wybierz **… → Włącz integrację z powłoką…** i przeczytaj opis. Nie włączaj jej wewnątrz edytora ani działającego programu.

Integracja dodaje tymczasowe hooki do bieżącej powłoki, bez zmiany plików startowych. **… → Bloki poleceń** otwiera panel ostatnich 100 komend wraz z katalogiem, czasem i kodem wyjścia. Zaznacz wpis, aby skopiować komendę albo znaleźć ją w terminalu. Wynik pozostaje w terminalu — zaznacz go tam do kopiowania lub wyjaśnienia z AI.

`⌘⌥↑` / `⌘⌥↓` przechodzą między znacznikami promptów w historii ekranu. **Wyczyść** usuwa zakończone i przerwane wpisy, zachowując działające polecenie. **Wyłącz integrację z powłoką** usuwa dodane hooki zsh albo przywraca poprzednie ustawienia promptu Bash.

Historia pozostaje w pamięci sesji i nie jest synchronizowana z iCloud. Po wznowieniu połączenia włącz integrację ponownie. Zagnieżdżone powłoki i przekazywanie znaczników przez tmux/screen nie są inicjalizowane automatycznie. Gdy powłoka nie przekaże znacznika końca, aplikacja nie wymyśla kodu wyjścia; rozłączenie oznacza niezakończone polecenie jako przerwane.

### Powiadomienia o zakończeniu

W **Ustawienia → Terminal** włącz **Powiadom o zakończeniu długiego polecenia** i zezwól na powiadomienia macOS. Polecenie trwające co najmniej 10 sekund może powiadomić, gdy sesja jest w tle. Wiadomość zawiera host/sesję, czas i kod wyjścia bez treści komendy. Kliknięcie wybiera sesję, jeśli nadal jest otwarta. Tryb skupienia macOS może odroczyć dostarczenie.

## Pliki i transfery SFTP

Wybierz **Pliki** albo **Terminal + pliki**. Panel lokalny i zdalny pokazują własne bieżące katalogi. Korzystaj z okruszków ścieżki oraz przycisków wstecz/dalej. Menu **…** panelu zawiera odświeżanie, sortowanie, opcje widoku, ukryte pliki, nowy plik/katalog i **Przejdź do katalogu…**. Ulubione foldery znajdziesz w menu ścieżki.

Możesz wybrać listę, ikony albo kolumny. Dwuklik otwiera katalog. `⌘` i `⇧` służą do zaznaczania wielu pozycji. **Return/Enter** rozpoczyna zmianę nazwy zaznaczonego elementu; kolejny Enter zapisuje, a Escape anuluje. **Delete** otwiera potwierdzenie trwałego usunięcia.

Przeciągnięcie z panelu lokalnego do zdalnego wysyła pliki; w przeciwną stronę je pobiera. Upuszczenie na katalog wybiera go jako cel. Przeciągnięcie wewnątrz jednego panelu przenosi elementy do wybranego folderu. Te same operacje są dostępne z menu kontekstowego.

Panel **Transfery** otworzysz przyciskiem ze strzałkami góra/dół w pasku aplikacji. Pokazuje operacje ze wszystkich połączeń, postęp, stan, anulowanie i ponowienie. Pauza zatrzymuje zadania oczekujące; rozpoczęte kończą się normalnie. Globalny limit równoległości jest w **Ustawienia → SFTP**. Po błędzie lub anulowaniu w celu mogą pozostać pliki częściowe; ponowienie wymaga osobnej akcji.

### Konflikty nazw

| Decyzja | Co się stanie |
| --- | --- |
| Scal | Dla konfliktu dwóch folderów: zachowuje elementy istniejące tylko w celu i pyta o konflikty dzieci. |
| Zastąp | Zastępuje istniejący element. W przypadku folderu może zastąpić całą zawartość folderu docelowego. |
| Zachowaj oba | Nadaje przychodzącemu elementowi wolną nazwę z numerem. |
| Pomiń | Pozostawia ten element docelowy bez zmian. |
| Zatrzymaj | Zatrzymuje pozostałe elementy bieżącej partii; rozpoczęte transfery kontynuują pracę. |

**Zastosuj do wszystkich** dotyczy bieżącej partii, z osobnymi decyzjami dla plików i folderów. Wysyłanie i pobieranie zachowują źródła. Jeśli odtworzenie poprzedniego celu po błędzie zastąpienia nie powiedzie się, komunikat zawiera ścieżkę odzyskiwania.

## Edytor plików zdalnych

Dwuklik zdalnego pliku tekstowego UTF-8 albo **Edytuj plik** otwiera edytor. Obsługiwane są pliki do 2 MB. Można wybrać składnię, włączyć zawijanie, śledzić wiersz i kolumnę oraz korzystać z automatycznego wcięcia, także dla tabulatorów i CRLF.

Po edycji użyj **Zapisz na serwerze** (`⌘S`). Do czasu zapisu zmiany pozostają w edytorze. Aplikacja sprawdza zmianę zawartości zdalnej przed wysłaniem i pyta przed zamknięciem niezapisanych zmian. Możesz wyeksportować lokalną kopię wersji oryginalnej lub edytowanej. Błąd wysyłania zachowuje obie wersje do odzyskania. Kontrola konfliktu nie blokuje równoległego zapisu przez inne aplikacje.

**Kompaktowy edytor — niewydany:** nagłówek zawiera **Zapisz**, a **…** udostępnia ponowne wczytanie i zapis lokalnej kopii. Pasek stanu zawiera składnię, zawijanie, kodowanie oraz pozycję kursora. Aktywny wiersz jest podświetlony na całej szerokości.

Edycja SFTP korzysta z uprawnień pierwotnego konta SSH, także po przejściu terminala na root.

## Biblioteka poleceń

Otwórz **Polecenia** w panelu bocznym. Zaznacz wpis, aby zobaczyć pełny tekst. Możesz wyszukiwać, kopiować oraz edytować i usuwać pozycje przez menu akcji. Usuwanie wymaga potwierdzenia.

Dla bieżącego, połączonego terminala:

- **Wstaw** umieszcza tekst w powłoce do edycji, bez Enter.
- **Wykonaj** wysyła polecenie i Enter.

**Uruchom na hostach…** pozwala wybrać do dziesięciu hostów, przejrzeć komendę i adresy, a następnie uruchomić ją w osobnych nowych terminalach. Żaden cel nie jest domyślnie zaznaczony. Uwierzytelnianie i sprawdzanie odcisku nadal obowiązują. Stan „Polecenie wysłane” potwierdza dostarczenie, a nie sukces. Nie ma automatycznego ponowienia ani wykonywania poleceń startowych tych hostów.

Host może mieć jawnie zatwierdzone polecenie startowe. Jego zmiana wymaga ponownego zatwierdzenia; automatyczne wznowienie połączenia go nie powtarza.

## Tunele i host pośredniczący

Utwórz profil w sekcji **Tunele** i uruchom go przez aktywne połączenie SSH:

| Typ | Przykładowe zastosowanie |
| --- | --- |
| Przekierowanie lokalne | Dostęp do usługi zdalnej przez port na Macu. |
| Przekierowanie zdalne | Udostępnienie usługi osiągalnej lokalnie przez nasłuch na serwerze. |
| Dynamiczny SOCKS5 | Użycie SSH jako proxy SOCKS dla skonfigurowanego klienta. |

Przed uruchomieniem sprawdź adres nasłuchu, porty i cel. „Lokalne” oraz „zdalne” opisują stronę nasłuchującą. Serwer SSH może ograniczać forwarding.

Jeśli łączysz się przez bastion, ustaw pojedynczego **Hosta pośredniczącego** w edycji hosta docelowego. Połączenie pośrednie ma własne uwierzytelnianie i sprawdzanie tożsamości.

## Dostęp administratora

Użyj **… → Przejdź na root…** albo jawnie włącz przejście po nowym połączeniu w ustawieniach hosta. Wybierz sudo lub su. Zapisane hasło administratora znajduje się w osobnym, lokalnym wpisie pęku kluczy; odczyt wymaga Touch ID lub hasła logowania do Maca. Hasło nie trafia do iCloud ani eksportu.

Nagrywanie zatrzymuje się przed wymianą hasła administratora. `exit` opuszcza podwyższoną powłokę. Przejście terminala na root nie podnosi uprawnień SFTP. Automatyczne wznowienie połączenia nie ponawia początkowego przejścia na root.

## Asystent AI

Wybierz **AI**, aby przygotować polecenie. Aby wyjaśnić wynik, zaznacz tekst i wybierz **Wyjaśnij** z menu kontekstowego. Przejrzyj lub popraw tekst przed wysłaniem. Asystent zwraca odpowiedź, ale nie wykonuje komend.

**Apple** jest domyślnym dostawcą działającym na urządzeniu. Wymaga macOS 26+, dostępnego Apple Intelligence i pobranego modelu. Aplikacja pokazuje dostępność; brak obsługi polskiego może wymagać zapytania po angielsku.

**Codex CLI** jest opcjonalny i wymaga osobno zainstalowanego CLI z zapisanym logowaniem. Ścieżkę programu i opcjonalny model ustawisz w **Ustawienia → AI**. Zapytanie może trafić do dostawcy modelu. Aplikacja używa zapytań efemerycznych, read-only, bez narzędzi i automatycznego wykonywania. Nie dołącza sekretów z Keychain ani całej historii sesji. Nie przełącza dostawcy automatycznie. Przejrzyj wygenerowane komendy przed użyciem.

## Ustawienia i dane

| Karta ustawień | Co zmienia |
| --- | --- |
| Ogólne | Język polski/angielski i motyw ciemny/jasny/systemowy. |
| SFTP | Lokalny katalog startowy i globalny limit równoległych transferów. Katalog startowy dotyczy nowych paneli lokalnych. |
| AI | Dostawca, ścieżka Codex i model. |
| Terminal | Czcionka, paleta, kursor, klawiatura/mysz, wznowienie, historia ekranu i dzwonek; nowsze wersje dodają wzorce, podgląd wklejania i powiadomienia. |
| iCloud | Opcjonalna synchronizacja, jeśli aplikacja została do niej przygotowana i podpisana. |
| Skróty | Lista skrótów klawiaturowych. |

Konfiguracja hostów znajduje się w SQLite w `~/Library/Application Support/PoliSSH`; sekrety przechowuje pęk kluczy macOS. Opcjonalny iCloud wymaga przygotowania przez programistę i jest domyślnie wyłączony w standardowym buildzie. Zobacz [dostępność iCloud](../status.md#icloud). Stan synchronizacji konfiguracji sam w sobie nie potwierdza synchronizacji sekretów.

## Skróty klawiaturowe

| Skrót | Akcja |
| --- | --- |
| `⌘K` | Szybkie połączenie i wyszukiwanie hosta/sesji. |
| `⌘T` | Nowy lokalny terminal. |
| `⌘W` | Zamknięcie aktywnej karty połączenia. |
| `⌘F` | Wyszukiwanie hostów lub wyjścia terminala, zależnie od widoku. |
| `⌃⌘S` | Pokaż/ukryj panel boczny. |
| `⌘N` | Dodaj hosta z biblioteki hostów. |
| `⇧⌘N` | Nowe okno. |
| `⌘,` | Ustawienia. |
| Return / Escape | Zapisz/anuluj zmianę nazwy pliku. |
| `⌘S` | Zapisz w edytorze zdalnym. |
| `⌘⌥↑` / `⌘⌥↓` | Poprzedni/następny znacznik promptu — niewydane. |

Zobacz [rozwiązywanie problemów](troubleshooting.md), jeśli napotkasz błąd.

## Obecne ograniczenia

To wersja rozwojowa bez instalatora z notaryzacją Apple. Nie zaimplementowano Mosh, Telnet ani połączeń szeregowych. Import OpenSSH obejmuje podstawowe pola hosta, a nie cały język konfiguracji. Transfery nie wznawiają automatycznie plików częściowych; dowiązania symboliczne i pliki specjalne są odrzucane przed zapisem. Edytor obsługuje UTF-8 do 2 MB. Root w terminalu nie zmienia uprawnień SFTP. Integracja z powłoką dotyczy bieżącej sesji i nie konfiguruje trwałości tmux.

Dostępność funkcji opisuje [informacja o wersji](../status.md).
