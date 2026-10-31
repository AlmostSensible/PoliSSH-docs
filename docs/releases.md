# Release notes / Historia zmian

## 0.21.1 — 31 October / października 2026

English
- Fix MCP initialization with interactive clients such as Codex. Requests now receive responses immediately while the connection remains open.
- MCP remains off by default. Enable it in Settings → Agents and reconnect your client. Shared servers, credentials and approval requirements are unchanged.

Polski
- Poprawiono inicjalizację MCP w interaktywnych klientach, takich jak Codex. Żądania otrzymują teraz odpowiedź od razu, bez zamykania połączenia.
- MCP pozostaje domyślnie wyłączone. Włącz je w Ustawienia → Agenci i połącz klienta ponownie. Udostępnione serwery, poświadczenia i wymagane zgody pozostają bez zmian.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.21.0 — 31 October / października 2026

English
- Connect agents through MCP. Enable it in Settings → Agents, choose shared SSH servers and copy connection setup for Codex or Claude. MCP is off by default and works locally on this Mac.
- Agents can browse and read remote files using their own SSH sessions. File saves, single-file copies and every command require your one-time approval in PoliSSH.
- Review requests and results, revoke individual connections or switch MCP off without closing your own sessions. Cancellation does not roll back remote effects; inspect unknown outcomes before retrying.

Polski
- Połącz agentów przez MCP. Włącz je w Ustawienia → Agenci, wybierz udostępnione serwery SSH i skopiuj konfigurację dla Codex lub Claude. MCP jest domyślnie wyłączone i działa lokalnie na tym Macu.
- Agenci mogą przeglądać i czytać zdalne pliki we własnych sesjach SSH. Zapis plików, kopiowanie pojedynczych plików i każde polecenie wymagają Twojej jednorazowej zgody w PoliSSH.
- Sprawdzaj prośby i wyniki, cofaj dostęp wybranym połączeniom lub wyłącz MCP bez zamykania własnych sesji. Anulowanie nie cofa zmian na serwerze; sprawdź nieznany wynik przed ponowieniem operacji.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.20.0 — 27 October / października 2026

PoliSSH 0.20.0 — public beta / publiczna beta

English
- Create nested host groups, move groups between parents and arrange siblings in your own order.
- Browse a collapsible tree in the sidebar and group manager. Use group menus to create subgroups, edit, move, reorder and delete groups; search groups and select hosts in the editor.
- Deleting a group keeps its hosts and moves its subgroups one level up. Configuration backups and iCloud records preserve hierarchy and order.
- Update all syncing Macs to 0.20.0 before editing groups: older versions can discard hierarchy metadata. Two-Mac synchronization remains experimental. Export a backup before updating.

Polski
- Twórz zagnieżdżone grupy hostów, przenoś je między grupami nadrzędnymi i ustawiaj własną kolejność.
- Korzystaj ze zwijanego drzewa w panelu bocznym i menedżerze grup. Menu grup pozwala tworzyć podgrupy, edytować, przenosić, zmieniać kolejność i usuwać grupy; edytor umożliwia wyszukiwanie grup i wybór hostów.
- Usunięcie grupy zachowuje hosty i przenosi podgrupy poziom wyżej. Kopie konfiguracji i rekordy iCloud zachowują hierarchię i kolejność.
- Przed edycją grup zaktualizuj wszystkie synchronizowane Maki do 0.20.0: starsze wersje mogą zgubić dane hierarchii. Synchronizacja dwóch Maków pozostaje eksperymentalna. Przed aktualizacją wyeksportuj kopię danych.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.19.3 — 24 October / października 2026

PoliSSH 0.19.3 — public beta / publiczna beta

English
- Administrator passwords are saved only after a confirmed root login that actually used the password. Rejected passwords and unused passwords for passwordless sudo are not saved.
- After a failed attempt, choose **Switch to root…** again to enter a replacement, including when an older version saved an incorrect password. If sudo keeps prompting, cancel the attempt or wait for its timeout before retrying.
- Saved administrator passwords remain local to this Mac and require Touch ID or the Mac login password when retrieved. Terminal elevation does not change SFTP permissions.

Polski
- Hasło administratora jest zapisywane dopiero po potwierdzonym wejściu na roota z jego użyciem. Błędne hasła i nieużyte hasła przy sudo bez hasła nie są zapisywane.
- Po nieudanej próbie ponownie wybierz **Przejdź na root…**, aby podać nowe hasło, także gdy starsza wersja zapisała błędne. Jeśli sudo nadal pyta o hasło, anuluj próbę albo poczekaj na upłynięcie limitu czasu przed ponowieniem.
- Zapisane hasła administratora pozostają lokalne na tym Macu, a odczyt wymaga Touch ID lub hasła logowania do Maca. Przejście terminala na root nie zmienia uprawnień SFTP.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.19.2 — 22 October / października 2026

PoliSSH 0.19.2 — public beta / publiczna beta

English
- Fixed password and Duo/PAM sign-in by preferring keyboard-interactive authentication when supported, matching OpenSSH. Avoids a failed password-only attempt before the interactive flow.
- Reuse the saved password once for a single hidden Password prompt. Verification codes and other prompts still require your response; an outdated password can be corrected interactively.
- Acknowledge empty authentication rounds without showing a blank sign-in dialog.
- Verified MIT SSH sign-in, reconnect and SFTP directory listing over VPN. Other MFA providers have not been verified live.

Polski
- Poprawiono logowanie hasłem z Duo/PAM: gdy serwer je udostępnia, aplikacja wybiera logowanie keyboard-interactive, tak jak OpenSSH. Pomija wcześniejszą nieudaną próbę samym hasłem.
- Zapisane hasło jest używane jeden raz przy pojedynczym ukrytym pytaniu Password. Kody i pozostałe pytania nadal wymagają odpowiedzi; nieaktualne hasło można poprawić podczas logowania.
- Puste rundy uwierzytelniania są potwierdzane bez wyświetlania pustego okna.
- Sprawdzono logowanie SSH, ponowne połączenie i listę katalogu SFTP MIT przez VPN. Innych dostawców MFA nie sprawdzono na żywo.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.19.1 — 21 October / października 2026

PoliSSH 0.19.1 — public beta / publiczna beta

English
- Fixed configuration export failing when a saved host has incomplete connection details, such as an empty username or whitespace in its address. Backups now preserve those entries without changing their values; they still need correction before connecting.
- Export results now appear beside the Export button, with the saved file path and Show in Finder. Errors are clearly labelled as export failures.
- Verified saving to Downloads, reading the resulting backup and preserving incomplete hosts during restore. Existing IDs are still skipped and never overwritten.

Polski
- Poprawiono błąd eksportu konfiguracji przy zapisanych hostach z niekompletnymi danymi połączenia, np. pustym użytkownikiem lub białym znakiem w adresie. Kopia zachowuje takie wpisy bez zmiany ich wartości; przed połączeniem nadal trzeba je poprawić.
- Wynik eksportu jest teraz przy jego przycisku, ze ścieżką pliku i opcją Pokaż w Finderze. Błędy są jednoznacznie opisane jako błędy eksportu.
- Sprawdzono zapis do Downloads, odczyt utworzonej kopii i zachowanie niekompletnych hostów przy przywracaniu. Istniejące ID nadal są pomijane i nigdy nie są nadpisywane.

Limits / Ograniczenia
- Configuration backups do not include passwords, private keys, passphrases, server trust, recordings or app preferences. JSON is not encrypted: protect host addresses and commands, and back up your keys separately.
- Kopie konfiguracji nie zawierają haseł, kluczy prywatnych, fraz kluczy, zaufania do serwerów, nagrań ani preferencji. JSON nie jest szyfrowany: chroń adresy i polecenia, a klucze zabezpiecz osobno.
- iCloud synchronization remains experimental. / Synchronizacja iCloud pozostaje eksperymentalna.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.19.0 — 21 October / października 2026

PoliSSH 0.19.0 — public beta / publiczna beta

English
- New offline What’s New window in Polish and English. It opens once for each new app version, including first installation, and can be reopened from PoliSSH → What’s New. Includes recent release highlights and a link to the full release history.
- Fixed a macOS accessibility crash when reading the status after configuration export or restore. Verified export to a file, restoration into an empty library, duplicate skipping and persistence after restarting.

Polski
- Nowe okno Co nowego, dostępne offline po polsku i angielsku. Pokazuje się raz dla nowej wersji, także przy pierwszej instalacji. Można wrócić do niego przez PoliSSH → Co nowego. Zawiera ostatnie zmiany i link do pełnej historii wydań.
- Poprawiono awarię dostępności macOS przy odczycie komunikatu po eksporcie lub przywróceniu konfiguracji. Sprawdzono eksport do pliku, odtworzenie w pustej bibliotece, pomijanie duplikatów i zachowanie danych po restarcie.

Limits / Ograniczenia
- Configuration backups add missing entries; they do not overwrite existing IDs. Passwords, private keys, passphrases, server trust, recordings and app preferences are not included. JSON is not encrypted: protect host addresses and commands, and back up your keys separately.
- Kopia konfiguracji dodaje brakujące wpisy; nie nadpisuje istniejących ID. Nie zawiera haseł, kluczy prywatnych, fraz kluczy, zaufania do serwerów, nagrań ani preferencji. JSON nie jest szyfrowany: chroń adresy i polecenia, a klucze zabezpiecz osobno.
- Remote editor recovery copies require manual cleanup. SFTP saves use two renames, not an atomic transaction or server lock; a disconnect between them may require manual recovery. / Kopie odzyskiwania w edytorze usuwa się ręcznie. Zapis SFTP używa dwóch zmian nazwy, bez atomowej transakcji i blokady; zerwanie między nimi może wymagać ręcznego odzyskania.
- iCloud synchronization remains experimental. / Synchronizacja iCloud pozostaje eksperymentalna.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.18.0 — 20 October / października 2026

PoliSSH 0.18.0 — public beta / publiczna beta

English
- Back up configuration from Settings → Backup. Preview and restore hosts, groups, credential profile metadata, snippets and tunnels without overwriting existing entries. Passwords and private keys are not included; protect the exported file because addresses and commands may be sensitive.
- Import more of your OpenSSH configuration: basic Host patterns and negation, bounded Include files, quoted IdentityFile paths and a single named ProxyJump. Importing private keys into Keychain requires explicit selection. ProxyCommand and Match exec are never executed.
- Remote editor saves retain the previous file as a recovery copy, preserve owner/group and POSIX permissions, and reject detected conflicts, symlinks and unwritable originals. Failed replacements attempt recovery while the server remains reachable.

Polski
- Kopia konfiguracji w Ustawienia → Kopia danych. Podejrzyj i przywróć hosty, grupy, metadane profili logowania, snippety i tunele bez nadpisywania istniejących wpisów. Hasła i klucze prywatne nie trafiają do kopii; chroń plik, ponieważ adresy i polecenia mogą być poufne.
- Rozszerzony import OpenSSH: podstawowe wzorce Host i negacja, ograniczona obsługa Include, ścieżki IdentityFile w cudzysłowach oraz pojedynczy nazwany ProxyJump. Import kluczy prywatnych do Pęku kluczy wymaga osobnego zaznaczenia. ProxyCommand i Match exec nigdy nie są wykonywane.
- Edytor zdalny zachowuje poprzedni plik jako kopię do odzyskania, utrzymuje właściciela, grupę i uprawnienia POSIX oraz odrzuca wykryte konflikty, dowiązania symboliczne i pliki bez prawa zapisu. Przy błędzie podejmuje próbę przywrócenia, jeśli serwer jest nadal dostępny.

Limits / Ograniczenia
- Remote text editing supports UTF-8 up to 2 MiB. SFTP replacement uses two renames, not an atomic transaction or server lock. A disconnect between renames may require recovering the original from its backup path. Recovery copies require manual cleanup; replacement does not copy ACLs or extended attributes.
- Edytor obsługuje UTF-8 do 2 MiB. Zapis SFTP korzysta z dwóch zmian nazwy, bez atomowej transakcji i blokady serwera. Zerwanie połączenia pomiędzy nimi może wymagać odzyskania oryginału ze ścieżki kopii. Kopie usuwa się ręcznie; nowy plik nie przejmuje ACL ani rozszerzonych atrybutów.
- iCloud synchronization remains experimental. / Synchronizacja iCloud pozostaje eksperymentalna.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.17.1 — 20 October / października 2026

PoliSSH 0.17.1 — public beta / publiczna beta

English
- Added a Beta badge in the workspace and public beta information in About PoliSSH.
- Added bundled third-party license texts and Help menu access.
- Added Help, Privacy and bug-report links.
- Marked iCloud synchronization as experimental pending verification between two Macs.
- Updated Polish/English installation, backup, troubleshooting and release documentation.

Polski
- Dodano etykietę Beta w oknie aplikacji i informację o publicznej becie w panelu O PoliSSH.
- Dodano licencje bibliotek w paczce i dostęp do nich w menu Pomoc.
- Dodano odnośniki do instrukcji, prywatności i zgłaszania błędów.
- Synchronizację iCloud oznaczono jako eksperymentalną do czasu sprawdzenia na dwóch Macach.
- Uaktualniono polskie i angielskie instrukcje instalacji, kopii danych, diagnostyki i historii zmian.

Apple Silicon · macOS 14+. Finish active sessions and transfers before updating.
Apple Silicon · macOS 14+. Przed aktualizacją zakończ sesje i transfery.

## 0.17.0 — 20 October / października 2026

Public beta for Apple Silicon, macOS 14+. [Download and installation](index.md).

- Signed, notarized distribution outside the App Store and signed Sparkle updates; manual checks and optional automatic checks in Polish and English.
- Direct SFTP without a shell, grouped transfers and automatic retries of temporary failures. Completed files are kept; known partial files restart from the beginning.
- Inline AI command suggestions with ⌘I, reviewed before insertion and never automatically executed. Optional provider discovery and model selection.
- Terminal text-size shortcuts, pattern/regex highlighting, paste review, clickable file references, shell integration, history and completion notifications.
- Compact remote editor with syntax detection and local-copy export; refinements to snippets, dialogs, transfer activity and narrow layouts.

Publiczna beta na Apple Silicon, macOS 14+.

- Podpisana i notaryzowana aplikacja poza App Store oraz podpisane aktualizacje Sparkle; ręczne i opcjonalne automatyczne sprawdzanie w PL/EN.
- Bezpośrednie SFTP bez powłoki, grupowanie transferów i ponawianie błędów przejściowych. Ukończone pliki pozostają; częściowe zaczynają się od początku.
- Sugestie poleceń AI przy kursorze przez ⌘I: najpierw przegląd, potem wstawienie bez automatycznego wykonania. Wykrywanie opcjonalnych dostawców i wybór modelu.
- Skróty rozmiaru tekstu, wzorce i regexy, podgląd wklejania, klikane ścieżki, integracja powłoki, historia i powiadomienia.
- Kompaktowy edytor z wykrywaniem składni i lokalną kopią; usprawnienia poleceń, dialogów, aktywności transferów i wąskich układów.

The beta's [known limits](status.md) apply, including experimental iCloud. / Obowiązują [ograniczenia bety](status.md), w tym eksperymentalny iCloud.

## 0.16.1 — 11 October / października 2026

Searchable snippets with a separate preview, explicit execution controls and deletion confirmation. / Wyszukiwalna biblioteka poleceń z osobnym podglądem, jawnymi akcjami wykonania i potwierdzeniem usunięcia.

This version has no automatic updater. Install the current beta manually once. / Ta wersja nie ma aktualizatora; jednorazowo zainstaluj bieżącą betę ręcznie.
