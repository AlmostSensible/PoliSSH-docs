# Rozwiązywanie problemów

| Objaw | Co sprawdzić |
| --- | --- |
| Nie można połączyć się z serwerem | Adres, port, dostępność sieci/VPN i działanie SSH. Nie traktuj timeoutu jako dowodu błędnego hasła. |
| Hasło lub klucz jest odrzucany | Nazwę konta i profil uwierzytelniania; dla ssh-agent sprawdź `ssh-add -l`. |
| Zmienił się odcisk serwera | Ustal przyczynę z administratorem przed zaakceptowaniem nowego klucza. |
| Pliki działają, terminal nie | Serwer może udostępniać wyłącznie SFTP. Korzystaj z widoku Pliki. |
| Brak uprawnień do zapisu pliku | Uprawnienia konta SFTP. Root w terminalu nie zmienia tych uprawnień. |
| Edytor zgłasza konflikt | Plik zmienił się od wczytania. Najpierw zachowaj lokalną kopię edycji, potem wczytaj i porównaj aktualną wersję. |
| Transfer został przerwany | Sprawdź plik docelowy. Błędy przejściowe są domyślnie ponawiane do dwóch razy; pliki ukończone pozostają, a częściowe zaczynają się od początku. Anulowane transfery ponów jawnie. Brak wznowienia od ostatniego bajtu. |
| Zamiast polskich liter działają skróty Meta | Wyłącz Używaj Option jako Meta w ustawieniach terminala. |
| Reguła podświetla część nazwy pliku | Włącz Regex i użyj granic słów, np. `\bsuccess\b`. |
| Brak historii poleceń | Włącz integrację przy gotowym zsh/Bash 4.4+, ponownie po reconnect. Sprawdź informację o wersji. |
| Brak powiadomienia | Włącz opcję, sprawdź zgodę macOS i tryb skupienia. Polecenie musi trwać ≥10 sekund, a sesja być w tle. |
| Apple AI nie jest dostępne | Sprawdź wersję systemu, Apple Intelligence i pobrany model. Codex wymaga osobnej konfiguracji; aplikacja nie przełącza dostawcy za Ciebie. |

Więcej wskazówek diagnostycznych znajdziesz w [Troubleshooting](../en/troubleshooting.md). Przy zgłoszeniu błędu podaj wersję aplikacji, macOS, kroki, oczekiwany efekt i widoczny komunikat. Usuń hasła, klucze prywatne i prywatne adresy z udostępnianych logów.
