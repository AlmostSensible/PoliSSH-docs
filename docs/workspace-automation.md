# Workspace status, actions and Tailscale — 0.24.0

## English

### Program status and attention

Programs supporting OSC 7501 can report working, waiting for a response, completed, failed and idle states, plus optional progress. PoliSSH displays these in tabs and terminal headers; choose a status to inspect all records. Waiting takes priority over failures, running work and completions. Ordinary commands use the existing opt-in shell integration for start/end tracking; PoliSSH does not infer approval requests from terminal text.

Open **Needs attention** in the workspace sidebar or toolbar to find waiting programs and unread completions/failures. Opening a panel or choosing **Mark as read** acknowledges completed results. Waiting programs remain until they report another state. Status and acknowledgement data stay in memory. Disconnected terminals retain completed results but discard active states.

In **Settings → Terminal → History and notifications**, enable long-command completion notifications or the separate **Notify when a program needs a response** option. Both require macOS notification permission. Alerts are sent only for background panels/windows; completion alerts require at least ten seconds. Repeated reports and overlapping shell/program completion reports are deduplicated. Notifications contain the session name and event type, without program messages or commands.

### Snippets in Quick connect

Press **⌘K** and search snippet names or command text. Select a snippet to review it. **Insert into active terminal** (or Return) inserts its current command without pressing Enter. **Run on hosts…** opens the existing host selection and review flow, limited to ten hosts. Insertion requires a connected terminal that is ready for input. Removed snippets cannot run from an old selection.

### Agents

**Settings → Agents → Access** shows four setup steps: enable MCP, share servers, add an agent app, and receive its first request. The client list distinguishes copied configuration from an actual authenticated request; timestamps describe requests received during this app run, not a persistent transport connection. Preview or copy the agent instructions in settings. No external client configuration or hooks are modified automatically.

Existing MCP permissions apply: agents have their own sessions, changes require approval, and private terminal buffers and panels remain unavailable. The guide covers pagination, exit codes and inspecting remote state before retrying an unknown outcome.

### Tailscale devices

Open **Tailscale devices** in the workspace sidebar. PoliSSH reads the already installed client's `status --json`, automatically on opening and when you choose **Refresh**. It checks the system/user Applications folders and standard Homebrew locations. Use **Choose CLI…** for another executable; PoliSSH runs the selected file, so select only your trusted Tailscale CLI. The selection is local to this Mac.

Search by name, DNS, IP or system and use the online-only filter. Counts and the last successful refresh time stay visible; previous results remain available during refresh. Icons use the reported OS, with hardware hints from device names where available. Green Online, grey Offline and unknown states include text labels.

The CLI runs without a shell, with a ten-second timeout and a combined stdout/stderr limit of 4 MiB. Network discovery stays in memory. **Add as host…** opens the regular host editor with the DNS name (or Tailscale IP), port 22 and an empty login for you to fill in. Existing entries are offered instead of overwritten, matching DNS names or Tailscale IPs.

Online status does not guarantee SSH access. Connections use the existing SSH/SFTP engine, credentials and host-key verification. PoliSSH does not install/start Tailscale, log in, change network policies, embed a VPN, or enable the separate Tailscale SSH authentication mode. The CLI JSON format can change; unsupported responses show an error. See [Tailscale CLI documentation](https://tailscale.com/docs/reference/tailscale-cli).

## Polski

### Statusy i uwaga

Programy obsługujące OSC 7501 zgłaszają pracę, oczekiwanie na odpowiedź, zakończenie, błąd lub bezczynność oraz opcjonalny postęp. Statusy widać na kartach i w nagłówkach terminali; kliknięcie pokazuje szczegóły wszystkich rekordów. Priorytet: oczekiwanie → błąd → praca → zakończenie → bezczynność. Zwykłe polecenia korzystają z istniejącej, opcjonalnej integracji powłoki. PoliSSH nie zgaduje próśb o zgodę z tekstu terminala.

Widok **Wymaga uwagi**, dostępny w panelu bocznym i pasku narzędzi, zbiera oczekujące programy oraz nieprzeczytane zakończenia i błędy. Otwarcie panelu lub **Oznacz jako przeczytane** potwierdza odczyt wyniku. Oczekiwanie pozostaje do zmiany stanu programu. Dane są przechowywane w pamięci; rozłączenie usuwa aktywne statusy i zachowuje zakończone wyniki.

W **Ustawienia → Terminal → Historia i powiadomienia** można włączyć powiadomienia o długich poleceniach lub osobno **Powiadom, gdy program wymaga odpowiedzi**. Wymagana jest zgoda macOS. Alerty dotyczą paneli i okien w tle; zakończenie wymaga co najmniej dziesięciu sekund pracy. Powtarzane raporty oraz zakończenie zgłoszone jednocześnie przez program i powłokę nie dublują alertów. Powiadomienie zawiera nazwę sesji i rodzaj zdarzenia, bez komendy ani komunikatu programu.

### Snippety i agenci

W **⌘K** wyszukaj nazwę snippetu lub fragment komendy. Po wyborze zobaczysz podgląd. **Wstaw do aktywnego terminala** lub Return wstawia aktualną komendę bez wykonania. **Uruchom na hostach…** otwiera dotychczasowy wybór i podgląd dla maksymalnie dziesięciu hostów. Wstawianie wymaga połączonego terminala gotowego na dane.

**Ustawienia → Agenci → Dostęp** pokazują etapy konfiguracji i rzeczywiste odebranie pierwszego żądania. Skopiowanie konfiguracji nie potwierdza połączenia. Daty dotyczą żądań odebranych podczas działania aplikacji, a nie stałego połączenia klienta. Instrukcję dla agenta można przeczytać i skopiować w ustawieniach. Konfiguracja i hooki innych aplikacji nie są zmieniane. Dotychczasowe zasady zatwierdzania i prywatności pozostają w mocy.

### Tailscale

Wybierz **Urządzenia Tailscale** w panelu bocznym. Lista pochodzi z lokalnego `status --json`; odświeża się przy otwarciu i po kliknięciu **Odśwież**. Aplikacja szuka CLI w katalogach Applications i Homebrew. **Wybierz CLI…** pozwala wskazać inne położenie zaufanego pliku wykonywalnego. Wybór jest lokalny dla tego Maca.

Proces ma limit dziesięciu sekund i 4 MiB odpowiedzi. **Dodaj jako host…** otwiera zwykły formularz z nazwą DNS lub adresem Tailscale i portem 22; uzupełnij login oraz poświadczenia. Istniejące hosty nie są nadpisywane. Stan online nie potwierdza działania SSH. Połączenia korzystają ze zwykłego SSH/SFTP i weryfikacji klucza serwera. PoliSSH nie instaluje VPN, nie loguje do Tailscale, nie zmienia polityk i nie włącza osobnego trybu Tailscale SSH. Nieobsługiwana odpowiedź CLI jest zgłaszana jako błąd.

Tailscale devices can be searched by name, DNS, IP or OS and filtered to online devices. Refresh retains existing results and shows the last successful update time. Device artwork uses the reported OS; Apple hardware hints come from names and may be generic when no model is supplied. These hints do not verify hardware or SSH support.

Urządzenia Tailscale można wyszukiwać po nazwie, DNS, IP lub systemie i filtrować do urządzeń online. Odświeżanie zachowuje poprzednie wyniki i pokazuje czas ostatniego udanego odczytu. Ikony korzystają ze zgłoszonego systemu; typ urządzenia Apple jest podpowiadany na podstawie nazwy i może być ogólny. Nie jest to weryfikacja sprzętu ani dostępności SSH.

Na liście Tailscale szukaj po nazwie, DNS, IP lub systemie i użyj filtra urządzeń online. Widać liczniki i czas ostatniego udanego odświeżenia; odświeżanie zachowuje poprzednią listę. Ikony korzystają z systemu oraz wskazówek w nazwie sprzętu, a stan ma kolor i etykietę tekstową.
