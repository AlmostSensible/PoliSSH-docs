# Availability / Dostępność

## Public beta 0.30.0

For Apple Silicon Macs (M1 or later), macOS 14+. Intel is not supported by the current ZIP. No App Store or TestFlight is required. [Download](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.30.0/PoliSSH-0.30.0-arm64.zip), extract and copy the app to Applications. Updates are available from the PoliSSH menu. Version 0.16.1 and earlier require this one-time manual installation.

Dla Maców z Apple Silicon (M1 lub nowszym), macOS 14+. Obecna paczka nie obsługuje procesorów Intel. Nie wymaga App Store ani TestFlight. [Pobierz](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.30.0/PoliSSH-0.30.0-arm64.zip), rozpakuj i przenieś aplikację do Aplikacji. Aktualizacje są w menu PoliSSH. Wersje 0.16.1 i starsze wymagają jednorazowej instalacji ręcznej.

The app source is private; this repository contains public documentation and release downloads. The download is signed and notarized. Notarization does not mean that every feature has been tested on every supported Mac.

Kod aplikacji pozostaje prywatny; to repozytorium zawiera publiczną dokumentację i paczki. Aplikacja jest podpisana i notaryzowana. Notaryzacja nie oznacza przetestowania każdej funkcji na każdym wspieranym Macu.

## New in 0.30.0 / Nowości w 0.30.0

### English

- Add tags under **Organization** and use **Tags** in the library toolbar to filter hosts. Colored pills identify tags across hosts. When a row shows **+N**, select the host to see the remaining tags in Details.
- Click anywhere on a group header to expand or collapse it, including nested groups. Switch between list and tiles, look for the **Root** badge on hosts with configured root access, and use the ellipsis for host actions.
- Find connection, authentication, organization and advanced settings in collapsible sections. Related setup and file dialogs use the same form styling.

### Polski

- Dodawaj tagi w sekcji **Organizacja** i filtruj bibliotekę przez **Tagi** na pasku narzędzi. Kolorowe kapsułki ułatwiają rozpoznanie tych samych tagów na różnych hostach. Gdy wiersz pokazuje **+N**, zaznacz hosta, aby zobaczyć pozostałe tagi w szczegółach.
- Kliknij w dowolne miejsce nagłówka, aby rozwinąć lub zwinąć grupę, także zagnieżdżoną. Przełączaj listę i kafelki, sprawdzaj skonfigurowany dostęp po znaczniku **Root** i otwieraj akcje hosta pod wielokropkiem.
- Dane połączenia, uwierzytelnianie, organizacja i ustawienia zaawansowane mają zwijane sekcje. Powiązane formularze konfiguracji i operacji na plikach mają spójny wygląd.

## New in 0.29.0 / Nowości w 0.29.0

### English

- Run a saved command on up to ten SSH hosts and compare their results in one window. Hosts with matching output and exit codes appear together.
- Expand a group to inspect stdout, stderr and elapsed time. If the connection drops before the server confirms completion, PoliSSH shows an unknown outcome and keeps the output received so far.

### Polski

- Uruchom zapisane polecenie na maksymalnie dziesięciu hostach SSH i porównaj wyniki w jednym oknie. Hosty z identycznym wyjściem i kodem zakończenia pojawią się razem.
- Rozwiń grupę, aby sprawdzić stdout, stderr i czas wykonania. Jeśli połączenie urwie się przed potwierdzeniem zakończenia, PoliSSH pokaże „Wynik nieznany” i zachowa odebrane wyjście.

## New in 0.28.0 / Nowości w 0.28.0

### English

- Filter files by name pattern and review the selected items before an SFTP transfer.
- Ask for a command at the terminal cursor. Inline AI can ask a clarifying question. Enter inserts the suggestion for manual execution.
- Search shared servers by name, address or username in MCP settings and review connected agent apps.

### Polski

- Filtruj pliki według maski nazwy i przejrzyj zaznaczone elementy przed transferem SFTP.
- Poproś o polecenie przy kursorze terminala. AI może zadać pytanie pomocnicze. Enter wstawia propozycję do samodzielnego wykonania.
- W ustawieniach MCP wyszukuj udostępniane serwery po nazwie, adresie lub użytkowniku i przeglądaj aplikacje agentów.

## New in 0.27.5 / Nowości w 0.27.5

Host context menus keep the list steady. Host forms offer searchable choices, and terminal actions reflect the current session state.

Menu kontekstowe hosta zachowuje pozycję listy. Formularze hostów mają wyszukiwalne listy wyboru, a akcje terminala uwzględniają stan sesji.

## New in 0.27.4 / Nowości w 0.27.4

The host library and connection view show the jump host used for a connection.

Lista hostów i widok połączenia pokazują serwer pośredniczący.

## New in 0.27.3 / Nowości w 0.27.3

The local terminal can display larger Kitty graphics, including the KymaOS desktop on Retina displays.

Lokalny terminal wyświetla większe obrazy Kitty, w tym pulpit KymaOS na ekranach Retina.

## New in 0.27.2 / Nowości w 0.27.2

The selected terminal view stays open after an SSH connection drops and reconnects.

Wybrany widok terminala pozostaje otwarty po zerwaniu i ponownym nawiązaniu połączenia SSH.

## New in 0.27.1 / Nowości w 0.27.1

Resume interrupted uploads with verification of files that already reached the server. Review the selected items and destination in a compact transfer confirmation sheet and find errors above the file list.

Wznawiaj przerwane wysyłanie z weryfikacją plików, które dotarły na serwer. Nowe okno potwierdzenia pokazuje wybrane elementy i miejsce docelowe. Błędy są widoczne nad listą plików.

## New in 0.27.0 / Nowości w 0.27.0

Resume SFTP transfers after restarting PoliSSH, replace files with recovery paths when needed, compare folders and edit files in batches. Download large files faster over high-latency links and copy folders with fewer requests.

Wznawiaj transfery SFTP po restarcie PoliSSH, zastępuj pliki z możliwością odzyskania, porównuj katalogi i wykonuj operacje grupowe. Pobieraj duże pliki szybciej na łączach o dużym opóźnieniu i kopiuj katalogi z mniejszą liczbą żądań.

## New in 0.26.2 / Nowości w 0.26.2

SSH prompts such as `[Y/n]` now appear in Needs attention. Enable response notifications to receive macOS alerts from background sessions.

Pytania SSH takie jak `[Y/n]` pojawiają się w widoku Wymaga uwagi. Włącz powiadomienia o potrzebie odpowiedzi, aby otrzymywać alerty macOS z sesji w tle.

## New in 0.26.1 / Nowości w 0.26.1

Detect 1Password, Bitwarden and Strongbox SSH agent sockets and choose a detected provider without pasting a path. Existing choices are preserved. The host authentication selector layout is fixed.

Wykrywanie gniazd agentów SSH 1Password, Bitwarden i Strongbox oraz wybór dostawcy bez wklejania ścieżki. Dotychczasowy wybór pozostaje bez zmian. Poprawiony układ wyboru sposobu logowania.

## New in 0.26.0 / Nowości w 0.26.0

Choose saved keys, SSH agents or password/interactive profiles in the host form. Inspect public identities and pin one agent key to a profile; missing or rejected pinned keys stop the connection. Configure a custom socket locally, validate encrypted imports and explicitly load saved keys into the system agent. SSH success and unavailable SFTP are reported separately. See the [authentication guide](en/guide.md#hosts-and-authentication). Certificates, FIDO2 and agent forwarding remain unsupported.

Wybierz zapisany klucz, agenta SSH albo profil hasła/logowania interaktywnego w formularzu hosta. Przeglądaj publiczne tożsamości i przypisz jeden klucz agenta do profilu; jego brak lub odrzucenie zatrzymuje połączenie. Ustaw własne lokalne gniazdo, sprawdzaj zaszyfrowany import i świadomie dodawaj zapisane klucze do systemowego agenta. Poprawne SSH i niedostępne SFTP mają osobne wyniki. Zobacz [instrukcję uwierzytelniania](pl/guide.md#hosty-i-uwierzytelnianie). Certyfikaty, FIDO2 i przekazywanie agenta pozostają nieobsługiwane.

## New in 0.25.0 / Nowości w 0.25.0

Compact connection tabs, unified Activity and searchable open sessions, clearer Needs attention, consistent terminal controls, visible host actions and a shared connection-test footer. Android devices have a recognizable Tailscale icon.

Kompaktowe karty połączeń, wspólna Aktywność i wyszukiwane otwarte sesje, czytelniejszy widok Wymaga uwagi, spójne akcje terminala, widoczne przyciski hostów i wspólny pasek testu połączenia. Android ma rozpoznawalną ikonę na liście Tailscale.

## New in 0.24.0 / Nowości w 0.24.0

Open Files directly, review transfer destinations and use the docked queue. Test SSH and SFTP before saving a host. Discover Tailscale devices with search, online filtering and system icons. Program status, Needs attention, snippet search and agent setup guidance are also included. See the [files guide](files-workspace.md) and [workspace guide](workspace-automation.md) for usage and limitations. Online does not guarantee SSH access; full program status requires OSC 7501 support.

Otwieraj Pliki bezpośrednio, sprawdzaj katalogi docelowe i korzystaj z dokowanej kolejki. Testuj SSH i SFTP przed zapisaniem hosta. Wyszukuj urządzenia Tailscale z filtrem online i ikonami systemów. Dodano też status programów, Wymaga uwagi, wyszukiwanie snippetów i instrukcję konfiguracji agentów. Zobacz [instrukcję plików](files-workspace.md) i [obszaru roboczego](workspace-automation.md). Online nie potwierdza dostępu SSH; pełne statusy wymagają wsparcia OSC 7501.

## New in 0.23.0 / Nowości w 0.23.0

Follow agents in workspace tabs or open the resizable session monitor from the compact MCP toolbar button (Shift-Command-M). A sidebar and read-only console show commands, output and file-operation events live. Recent closed sessions remain in memory until quitting. Commands and writes still require one-time approval.

Śledź agentów na kartach lub otwórz skalowalny podgląd sesji małym przyciskiem MCP w pasku (Shift-Command-M). Lista sesji i konsola tylko do odczytu pokazują polecenia, wyniki i zdarzenia operacji na plikach na żywo. Ostatnio zamknięte sesje pozostają w pamięci do zamknięcia aplikacji. Polecenia i zapis nadal wymagają jednorazowej zgody.

## New in 0.22.0 / Nowości w 0.22.0

Open MCP activity from the workspace indicator: see sessions, operations, approval requests and results. Settings → Agents now separates Access, Agent apps and Servers. Command output appears after completion. Local MCP connections also handle replies more reliably on macOS.

Otwórz aktywność MCP ze wskaźnika w obszarze roboczym: zobacz sesje, operacje, prośby o zgodę i wyniki. Ustawienia → Agenci mają teraz osobne zakładki Dostęp, Aplikacje agentów i Serwery. Wyniki poleceń pojawiają się po zakończeniu. Poprawiono też niezawodność lokalnych odpowiedzi MCP na macOS.

## New in 0.21.2 / Nowości w 0.21.2

Shared hosts show an MCP badge in the connection list and tiles. Badges update immediately when MCP is enabled/disabled or sharing changes in Settings → Agents.

Udostępnione serwery mają oznaczenie MCP na liście i kafelkach połączeń. Oznaczenia zmieniają się od razu po włączeniu/wyłączeniu MCP lub zmianie udostępnienia w Ustawienia → Agenci.

## New in 0.21.1 / Nowości w 0.21.1

Fixed MCP initialization with interactive clients such as Codex. Update PoliSSH and reconnect the client; existing connection setup stays valid.

Poprawiono inicjalizację MCP w interaktywnych klientach, takich jak Codex. Zaktualizuj PoliSSH i połącz klienta ponownie; dotychczasowa konfiguracja pozostaje ważna.

## New in 0.21.0 / Nowości w 0.21.0

Enable local MCP in Settings → Agents, choose shared SSH servers and copy setup for Codex or Claude. MCP is off by default. Agents use separate sessions; saves, single-file copies and every command require one-time approval in PoliSSH. Revoke access or turn MCP off at any time. Cancellation does not roll back remote effects.

Włącz lokalne MCP w Ustawienia → Agenci, wybierz udostępnione serwery SSH i skopiuj konfigurację dla Codex lub Claude. MCP jest domyślnie wyłączone. Agenci używają osobnych sesji; zapis, kopiowanie pojedynczych plików i każde polecenie wymagają jednorazowej zgody w PoliSSH. W każdej chwili możesz cofnąć dostęp lub wyłączyć MCP. Anulowanie nie cofa zmian na serwerze.

## New in 0.20.0 / Nowości w 0.20.0

Nested host groups, parent selection, moving groups and sibling ordering, with a collapsible tree and contextual menus. Deleting a group keeps its hosts and promotes its subgroups. Update every syncing Mac to 0.20.0 before editing hierarchy: older versions can discard hierarchy metadata. Two-Mac iCloud synchronization remains experimental.

Podgrupy hostów, wybór grupy nadrzędnej, przenoszenie i kolejność grup, ze zwijanym drzewem i menu kontekstowym. Usunięcie grupy zachowuje hosty i przenosi podgrupy poziom wyżej. Przed edycją hierarchii zaktualizuj wszystkie synchronizowane Maki do 0.20.0: starsze wersje mogą utracić metadane hierarchii. Synchronizacja iCloud między dwoma Makami pozostaje eksperymentalna.

## New in 0.19.3 / Nowości w 0.19.3

Root passwords are saved only after successful elevation and only when the password was actually used. After a rejected password, the next attempt opens the password dialog so it can be corrected. Root access in the terminal does not change SFTP permissions.

Hasło roota jest zapisywane dopiero po udanym podniesieniu uprawnień i tylko wtedy, gdy zostało użyte. Po odrzuceniu hasła następna próba otwiera okno pozwalające je poprawić. Root w terminalu nie zmienia uprawnień SFTP.

## New in 0.19.2 / Nowości w 0.19.2

Password profiles prefer the server's interactive password/MFA flow. The saved password is reused once, verification remains interactive, and empty Duo/PAM rounds no longer show a blank dialog. MIT SSH and SFTP were verified; other MFA providers have not been checked on live servers.

Profile z hasłem preferują interaktywne logowanie z MFA oferowane przez serwer. Zapisane hasło jest używane raz, drugi składnik pozostaje interaktywny, a puste rundy Duo/PAM nie wyświetlają pustego okna. Sprawdzono SSH i SFTP MIT; innych dostawców MFA nie testowano na rzeczywistych serwerach.

## New in 0.19.1 / Nowości w 0.19.1

Configuration export now preserves saved hosts with incomplete connection details. Export results appear beside the button, with the saved path and Show in Finder. Saving to Downloads and restoring incomplete entries were verified. Correct their connection details before connecting.

Eksport zachowuje teraz zapisane hosty z niekompletnymi danymi połączenia. Wynik pojawia się przy przycisku, ze ścieżką pliku i opcją Pokaż w Finderze. Sprawdzono zapis do Downloads i przywracanie niekompletnych wpisów. Przed połączeniem popraw ich dane.

## New in 0.19.0 / Nowości w 0.19.0

An offline Polish/English What’s New window introduces each new app version and can be reopened from the PoliSSH menu. Fixed a macOS accessibility crash in configuration backup status. File export, restore into an empty library, duplicate skipping and persistence after restart were verified.

Okno Co nowego działa offline po polsku i angielsku, przedstawia nową wersję i jest dostępne w menu PoliSSH. Poprawiono awarię dostępności macOS w komunikacie kopii konfiguracji. Sprawdzono eksport do pliku, odtworzenie w pustej bibliotece, pomijanie duplikatów i dane po restarcie.

## Included in 0.18.0 / Dostępne w 0.18.0

Configuration backup and add-only restore, richer SSH config import and recovery copies for remote editor saves. See [release notes](releases.md) for details and limitations.

Kopia konfiguracji i przywracanie nowych wpisów, rozszerzony import SSH oraz kopie do odzyskania przy zapisie edytora zdalnego. Szczegóły i ograniczenia w [historii zmian](releases.md).

## Included in 0.17.0 / Dostępne w 0.17.0

Pattern/regex highlighting, paste review, clickable file references, shell integration, command history, completion notifications, the compact editor, direct SFTP and signed updates are available. Their former Unreleased labels in the guides have been removed.

Dostępne są wzorce i regexy, podgląd wklejania, klikane ścieżki, integracja z powłoką, historia poleceń, powiadomienia, kompaktowy edytor, bezpośrednie SFTP i podpisane aktualizacje.

## iCloud

**Experimental.** Optional configuration synchronization uses private CloudKit; passwords/private keys use iCloud Keychain. Requires a provisioned app and enabled iCloud services. End-to-end synchronization between two Macs has not yet been verified. Keep a [backup](en/support.md#backup-and-recovery) before enabling it. Configuration sync status does not prove secrets have arrived on another Mac. Turning sync off retains local data; uninstalling the app is not a cloud-data deletion request.

**Funkcja eksperymentalna.** Konfiguracja korzysta z prywatnego CloudKit, a hasła i klucze prywatne z Pęku kluczy iCloud. Wymaga przygotowanej aplikacji i włączonych usług iCloud. Pełny przepływ między dwoma Macami nie został jeszcze zweryfikowany. Przed włączeniem zachowaj [kopię danych](pl/support.md#kopia-danych-i-odzyskiwanie). Stan konfiguracji nie potwierdza dotarcia sekretów na drugi Mac. Wyłączenie synchronizacji zachowuje dane lokalne; odinstalowanie nie usuwa danych z chmury.

## Known limits / Znane ograniczenia

- Interrupted SFTP writes may leave a partial file. Temporary failures can be retried up to twice; completed files are retained, known partial files restart from the beginning. This is not byte-offset resume. / Przerwany zapis może pozostawić częściowy plik. Błędy przejściowe mogą być ponawiane do dwóch razy; ukończone pliki pozostają, częściowe zaczynają się od początku.
- Remote editor: UTF-8 up to 2 MiB. Saves retain the previous file as a recovery copy; a disconnect between the two renames may require manual recovery. No atomic server lock; ACLs and extended attributes are not copied to the replacement. Recovery copies require manual cleanup. / Edytor: UTF-8 do 2 MiB. Zapis zachowuje poprzedni plik jako kopię; zerwanie połączenia między zmianami nazwy może wymagać ręcznego odzyskania. Bez atomowej blokady; nowy plik nie przejmuje ACL ani rozszerzonych atrybutów. Kopie usuwa się ręcznie.
- Root in a terminal does not elevate SFTP. / Root w terminalu nie zmienia uprawnień SFTP.
- OpenSSH import supports basic fields, not the complete configuration language. No Mosh, Telnet or serial connections. / Import OpenSSH obsługuje podstawowe pola. Brak Mosh, Telnet i połączeń szeregowych.
- Cross-device iCloud, a fresh installation on macOS 14 and all external AI providers on real accounts are not fully verified. / Nie potwierdzono pełnej synchronizacji iCloud, świeżej instalacji na macOS 14 ani wszystkich dostawców AI na rzeczywistych kontach.

[Help / Pomoc](en/support.md) · [Zgłoś problem / Report an issue](https://github.com/AlmostSensible/PoliSSH-docs/issues/new/choose)
