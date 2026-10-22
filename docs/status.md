# Availability / Dostępność

## Public beta 0.19.2

For Apple Silicon Macs (M1 or later), macOS 14+. Intel is not supported by the current ZIP. No App Store or TestFlight is required. [Download](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.19.2/PoliSSH-0.19.2-arm64.zip), extract and copy the app to Applications. Updates are available from the PoliSSH menu. Version 0.16.1 and earlier require this one-time manual installation.

Dla Maców z Apple Silicon (M1 lub nowszym), macOS 14+. Obecna paczka nie obsługuje procesorów Intel. Nie wymaga App Store ani TestFlight. [Pobierz](https://github.com/AlmostSensible/PoliSSH-docs/releases/download/v0.19.2/PoliSSH-0.19.2-arm64.zip), rozpakuj i przenieś aplikację do Aplikacji. Aktualizacje są w menu PoliSSH. Wersje 0.16.1 i starsze wymagają jednorazowej instalacji ręcznej.

The app source is private; this repository contains public documentation and release downloads. The download is signed and notarized. Notarization does not mean that every feature has been tested on every supported Mac.

Kod aplikacji pozostaje prywatny; to repozytorium zawiera publiczną dokumentację i paczki. Aplikacja jest podpisana i notaryzowana. Notaryzacja nie oznacza przetestowania każdej funkcji na każdym wspieranym Macu.

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
