# Pomoc i odzyskiwanie

## Zgłoś problem

[Utwórz zgłoszenie](https://github.com/AlmostSensible/PoliSSH-docs/issues/new/choose). Podaj wersję i build z PoliSSH — informacje, wersję macOS, model Apple Silicon, język i motyw, kroki, oczekiwany wynik oraz dokładny komunikat. Dla transferów dodaj kierunek, orientacyjny rozmiar, strukturę plików/katalogów i decyzje o konflikcie, anulowaniu lub ponowieniu. Najpierw sprawdź [rozwiązywanie problemów](troubleshooting.md).

Zgłoszenia i załączniki są publiczne. Usuń hasła, tokeny, prywatne adresy, poufne treści terminala i dane osobowe. W miarę możliwości użyj danych testowych. Nie przesyłaj bazy aplikacji ani kluczy prywatnych.

## Instalacja i aktualizacje

Pobierz paczkę z [oficjalnej strony wydań](https://github.com/AlmostSensible/PoliSSH-docs/releases), rozpakuj ZIP i przenieś PoliSSH.app do Aplikacji. Przed zastąpieniem zamknij poprzednią kopię. Uruchamiaj kopię z Aplikacji. Nie potrzebujesz Xcode, Rusta ani Homebrew. Kolejne wersje sprawdzisz przez PoliSSH → Sprawdź aktualizacje…. Nie wyłączaj Gatekeepera ani nie podpisuj ponownie pobranej aplikacji; zgłoś nieoczekiwany błąd bezpieczeństwa.

Przed aktualizacją zakończ transfery i pracę powłoki, zapisz edycje i zamknij pozostałe kopie aplikacji. Aktualizacje zachowują dotychczasową tożsamość i lokalizacje danych. Jeśli sprawdzanie się nie powiedzie, korzystaj z zainstalowanej wersji i spróbuj później lub pobierz oficjalną paczkę ręcznie. Nie obniżaj wersji bazy bez potwierdzonej zgodności.

## Kopia danych i odzyskiwanie

Zamknij PoliSSH przed kopiowaniem. W Finder → Idź → Idź do folderu otwórz `~/Library/Application Support/PoliSSH` i skopiuj **cały folder** w bezpieczne miejsce. Uwzględnij preferencje `~/Library/Preferences/com.polissh.app.plist`, jeśli istnieją, oraz osobno nagrania i eksporty w wybranych przez Ciebie miejscach. Zalecana jest szyfrowana kopia Time Machine lub całego Maca.

Kopia bazy **nie zawiera** haseł, kluczy prywatnych ani chronionych danych administratora z pęku kluczy. Zachowaj oryginalne pliki kluczy i osobno sprawdź kopię Maca/pęku kluczy. Chronione dane lokalne mogą wymagać ponownego wpisania na innym Macu. Eksperymentalna synchronizacja iCloud nie zastępuje kopii zapasowej.

Przy odzyskiwaniu lokalnym zamknij wszystkie kopie aplikacji, najpierw zachowaj aktualny folder, a następnie odtwórz kopię w tej samej lokalizacji. Użyj tej samej wersji aplikacji albo potwierdzonej zgodnej wersji nowszej. Uruchom oficjalną podpisaną aplikację i sprawdź hosty oraz profile przed połączeniem. Nie usuwaj działającej bazy ani nie resetuj pęku kluczy przy diagnozowaniu pustej biblioteki.

## Ograniczenia bety

Zobacz [dostępność](../status.md). Minimalny macOS 14 i synchronizacja iCloud między urządzeniami nadal wymagają osobnej weryfikacji. Przerwany zapis może zostawić częściowy plik zdalny; przed ponowieniem zachowaj lokalną kopię ważnej edycji. Opcjonalne narzędzia AI wymagają oddzielnej konfiguracji i podlegają zasadom dostawców.


Wydawca: **AlmostSensible**. Kontakt w sprawach prywatnych i zgłoszeń bezpieczeństwa: [hello@almostsensible.com](mailto:hello@almostsensible.com).
