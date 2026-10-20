# Availability / Dostępność

## Public beta 0.17.0

For Apple Silicon Macs (M1 or later), macOS 14+. Intel is not supported by the current ZIP. No App Store or TestFlight is required. [Download](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.17.0/PoliSSH-0.17.0-arm64.zip), extract and copy the app to Applications. Updates are available from the PoliSSH menu. Version 0.16.1 and earlier require this one-time manual installation.

Dla Maców z Apple Silicon (M1 lub nowszym), macOS 14+. Obecna paczka nie obsługuje procesorów Intel. Nie wymaga App Store ani TestFlight. [Pobierz](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.17.0/PoliSSH-0.17.0-arm64.zip), rozpakuj i przenieś aplikację do Aplikacji. Aktualizacje są w menu PoliSSH. Wersje 0.16.1 i starsze wymagają jednorazowej instalacji ręcznej.

The app source is private; this repository contains public documentation and release downloads. The download is signed and notarized. Notarization does not mean that every feature has been tested on every supported Mac.

Kod aplikacji pozostaje prywatny; to repozytorium zawiera publiczną dokumentację i paczki. Aplikacja jest podpisana i notaryzowana. Notaryzacja nie oznacza przetestowania każdej funkcji na każdym wspieranym Macu.

## Included in 0.17.0 / Dostępne w 0.17.0

Pattern/regex highlighting, paste review, clickable file references, shell integration, command history, completion notifications, the compact editor, direct SFTP and signed updates are available. Their former Unreleased labels in the guides have been removed.

Dostępne są wzorce i regexy, podgląd wklejania, klikane ścieżki, integracja z powłoką, historia poleceń, powiadomienia, kompaktowy edytor, bezpośrednie SFTP i podpisane aktualizacje.

## iCloud

**Experimental.** Optional configuration synchronization uses private CloudKit; passwords/private keys use iCloud Keychain. Requires a provisioned app and enabled iCloud services. End-to-end synchronization between two Macs has not yet been verified. Keep a [backup](en/support.md#backup-and-recovery) before enabling it. Configuration sync status does not prove secrets have arrived on another Mac. Turning sync off retains local data; uninstalling the app is not a cloud-data deletion request.

**Funkcja eksperymentalna.** Konfiguracja korzysta z prywatnego CloudKit, a hasła i klucze prywatne z Pęku kluczy iCloud. Wymaga przygotowanej aplikacji i włączonych usług iCloud. Pełny przepływ między dwoma Macami nie został jeszcze zweryfikowany. Przed włączeniem zachowaj [kopię danych](pl/support.md#kopia-danych-i-odzyskiwanie). Stan konfiguracji nie potwierdza dotarcia sekretów na drugi Mac. Wyłączenie synchronizacji zachowuje dane lokalne; odinstalowanie nie usuwa danych z chmury.

## Known limits / Znane ograniczenia

- Interrupted SFTP writes may leave a partial file. Temporary failures can be retried up to twice; completed files are retained, known partial files restart from the beginning. This is not byte-offset resume. / Przerwany zapis może pozostawić częściowy plik. Błędy przejściowe mogą być ponawiane do dwóch razy; ukończone pliki pozostają, częściowe zaczynają się od początku.
- Remote editor: UTF-8 up to 2 MB; conflict detection is not an atomic server lock. Save a local copy of important edits. / Edytor: UTF-8 do 2 MB, bez atomowej blokady pliku na serwerze. Zachowaj lokalną kopię ważnych zmian.
- Root in a terminal does not elevate SFTP. / Root w terminalu nie zmienia uprawnień SFTP.
- OpenSSH import supports basic fields, not the complete configuration language. No Mosh, Telnet or serial connections. / Import OpenSSH obsługuje podstawowe pola. Brak Mosh, Telnet i połączeń szeregowych.
- Cross-device iCloud, a fresh installation on macOS 14 and all external AI providers on real accounts are not fully verified. / Nie potwierdzono pełnej synchronizacji iCloud, świeżej instalacji na macOS 14 ani wszystkich dostawców AI na rzeczywistych kontach.

[Help / Pomoc](en/support.md) · [Zgłoś problem / Report an issue](https://github.com/AlmostSensible/PoliSSH-docs/issues/new/choose)
