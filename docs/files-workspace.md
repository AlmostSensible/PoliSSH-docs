# Files workspace / Obszar plików — 0.24.0

## English

Choose **Files** on a host to connect without running a shell or startup snippet. **Terminal / Files / Split** changes presentation without disconnecting. Opening a shell later reuses the SSH connection; SFTP-only servers remain usable when a shell is unavailable.

The two panels identify **This Mac** and the remote host. Each has navigation, a path, refresh, new folder, selection count and a directional transfer button. Switching modes retains browser state in the current session. After reconnecting, refresh checks the server again; disconnected remote listings are explicitly marked out of date. The local panel remains usable.

Select files and choose **Upload →** or **← Download**, or drag them between panels. Review the destination folder before adding the batch to the queue. Existing files go through the existing conflict review; a batch-wide decision applies only to that operation. Moving files within the same panel keeps the existing move/conflict flow.

Keyboard in the file list: Return opens the selected item; F2 renames in list/column views. Tab switches panels, ⌘↑ opens the parent, ⌘R refreshes, ⌘⇧G opens a path, and ⌘Return reviews the transfer. These shortcuts do not apply while typing in an editor or other text field.

**Transfer activity** beneath the panels opens the docked queue; the global toolbar still shows the same queue from any workspace. Pausing prevents queued tasks from starting and lets active tasks finish. Cancelling interrupts a task and may leave partial files. **Retry** rechecks conflicts and can copy from the beginning. Inspect the destination after an error before retrying. Closing a pane, tab, window or application with active/queued transfers asks whether to stay or interrupt them.

The remote editor checks size, modification time and content before saving. If metadata cannot be compared or the file changed, choose reload, explicit overwrite or cancel. Reload requires confirmation before discarding edits. Overwrite retains the server-side content check, temporary-file and recovery-copy safeguards. Failed saves keep your edits in the editor. Metadata/content checks are optimistic: SFTP does not provide a universal atomic compare-and-swap operation.

No new dependencies, credential migrations or MCP tools. This update does not add directory synchronization, cross-server copying, transfer restoration after app restart or new byte-offset resume behavior.

## Polski

Wybierz **Pliki** przy hoście, aby połączyć się bez powłoki i snippetu startowego. Przełącznik **Terminal / Pliki / Podział** zmienia widok bez rozłączania. Późniejsze otwarcie powłoki wykorzystuje to samo połączenie SSH; serwer SFTP-only działa również bez powłoki.

Panele pokazują **Ten Mac** i nazwę hosta, nawigację, ścieżkę, odświeżanie, nowy katalog, liczbę zaznaczonych elementów oraz kierunek transferu. Zmiana trybu zachowuje stan przeglądarki w sesji. Po ponownym połączeniu dane zdalne są odświeżane. Podczas rozłączenia lista zdalna jest oznaczona jako nieaktualna; panel lokalny pozostaje dostępny.

Zaznacz pliki i wybierz **Wyślij →** lub **← Pobierz**, albo przeciągnij je między panelami. Przed dodaniem do kolejki sprawdź katalog docelowy. Kolizje korzystają z dotychczasowego procesu zatwierdzania; decyzja dla całej operacji nie przechodzi na kolejne zadania. Przenoszenie w obrębie panelu zachowuje obecny proces.

Skróty na liście plików: Return otwiera element, F2 zmienia nazwę w widoku listy/kolumn, Tab przełącza panele, ⌘↑ otwiera katalog nadrzędny, ⌘R odświeża, ⌘⇧G otwiera ścieżkę, ⌘Return pokazuje podgląd transferu. Skróty nie przechwytują pisania w polach tekstowych.

**Aktywność transferów** pod panelami otwiera dokowaną kolejkę. Przycisk globalny pokazuje te same dane. Wstrzymanie kolejki zatrzymuje uruchamianie nowych zadań, a trwające kończą się normalnie. Anulowanie może pozostawić niepełne pliki. **Ponów** ponownie sprawdza konflikty i może kopiować od początku. Po błędzie sprawdź plik docelowy. Zamknięcie panelu, karty, okna lub aplikacji z aktywnymi transferami wymaga wyboru: pozostań albo przerwij i zamknij.

Edytor porównuje rozmiar, czas modyfikacji i treść przed zapisem. Przy zmianie lub braku porównywalnych metadanych wybierz wczytanie serwera, świadome nadpisanie albo anulowanie. Wczytanie wymaga potwierdzenia utraty zmian. Nadpisanie zachowuje zabezpieczenia pliku tymczasowego, porównania treści i kopii odzyskiwania. Błąd zapisu nie usuwa tekstu z edytora. SFTP nie zapewnia uniwersalnego atomowego zapisu warunkowego.

Nie dodano synchronizacji katalogów, kopiowania między serwerami ani przywracania kolejki po restarcie. Bez nowych zależności, migracji poświadczeń i narzędzi MCP.

## Test a host before saving / Sprawdź host przed zapisem

In the host editor, enter the address, port, username and authentication profile, then choose **Test connection**. The test authenticates over SSH and opens SFTP using the normal host-key and interactive authentication prompts, including jump hosts. It closes the test connection automatically and does not save the host, add it to Recent, start a shell or run startup commands. You can cancel the test. Editing the host or its authentication profiles clears the previous result. Saving remains available without a successful test. A successful test does not verify administrator privileges or write access to every directory.

W formularzu hosta podaj adres, port, użytkownika i profil uwierzytelniania, następnie wybierz **Sprawdź połączenie**. Test sprawdza logowanie SSH i SFTP, zachowując zatwierdzanie klucza serwera, pytania uwierzytelniania i hosty pośredniczące. Zamyka połączenie po sprawdzeniu. Nie zapisuje hosta, nie dodaje go do ostatnich połączeń i nie uruchamia powłoki ani poleceń startowych. Test można anulować. Zmiana danych lub profili usuwa poprzedni wynik. Zapis nie wymaga udanego testu. Sukces nie potwierdza uprawnień administratora ani możliwości zapisu w każdym katalogu.

## Setup and activity / Konfiguracja i aktywność

Host setup shows field-level validation. Advanced contains administrator access, startup commands, OS appearance and jump-host settings. The docked transfer activity explicitly covers **all hosts**, and its collapsed control shows the active count. Common connection and permission errors include recovery guidance; the transfer row keeps the original error under Technical details.

Formularz hosta pokazuje walidację przy polach. Sekcja **Zaawansowane** zawiera dostęp administratora, polecenie startowe, wygląd systemu i hosta pośredniczącego. Dokowana aktywność obejmuje **wszystkie hosty**, a po zwinięciu nadal pokazuje liczbę aktywnych transferów. Typowe błędy sieci i uprawnień zawierają wskazówki; oryginalny błąd transferu pozostaje w szczegółach technicznych.
