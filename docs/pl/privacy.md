# Prywatność

Aktualizacja: 20 października 2026. Dotyczy publicznej bety PoliSSH. Opcjonalne usługi opisano oddzielnie poniżej.

Wydawca i kontakt w sprawach prywatności: **AlmostSensible**, [hello@almostsensible.com](mailto:hello@almostsensible.com).

## Dane na Macu

Adresy hostów, nazwy użytkowników, grupy, tagi, polecenia, tunele i metadane profili uwierzytelniania są przechowywane lokalnie w SQLite. Hasła, klucze prywatne i ich frazy zabezpieczające trafiają do Pęku kluczy macOS. Preferencje aplikacji pozostają lokalne. Zapamiętane odciski serwerów służą do sprawdzania kolejnych połączeń.

Historia ekranu i poleceń pozostaje w pamięci sesji. Po włączeniu nagrywania sesji jej wyjście trafia do wybranego lokalnego katalogu logów. Logi i eksportowane pliki mogą zawierać poufne informacje. Zapisane hasła administratora do sudo/su korzystają z chronionych wpisów lokalnego pęku kluczy i nie podlegają synchronizacji iCloud.

## Połączenia i uprawnienia

SSH/SFTP łączy się z wybranymi przez Ciebie serwerami. Serwery i operatorzy sieci widzą metadane połączenia; serwery przetwarzają wysłane polecenia i pliki. Lokalny terminal działa z uprawnieniami Twojego konta na Macu. Aplikacja jest dystrybuowana poza App Store bez App Sandbox. macOS może poprosić o dostęp do plików, powiadomień lub uwierzytelniania. Odmowa może ograniczyć daną funkcję.

## Opcjonalny iCloud — funkcja eksperymentalna

Po włączeniu synchronizacji w przygotowanej kompilacji konfiguracja trafia do prywatnej bazy Apple CloudKit, a odpowiednie dane uwierzytelniania korzystają z Pęku kluczy iCloud. Usługi obsługuje Apple zgodnie z własną [polityką prywatności](https://www.apple.com/legal/privacy/). Pełny przepływ między urządzeniami nie został jeszcze sprawdzony. Synchronizacja jest opcjonalna; wyłączenie zachowuje lokalne dane i nie usuwa automatycznie danych z chmury. Nie zastępuje kopii zapasowej.

## Opcjonalne AI

Modele Apple na urządzeniu i obsługiwane lokalne konfiguracje Ollama/LM Studio działają na Macu; instalacja lub logowanie w zewnętrznych narzędziach odbywa się osobno. W przypadku zewnętrznych dostawców CLI wysłany tekst może trafić do wybranego dostawcy przez Twoje istniejące konto. Obowiązują jego zasady prywatności, przechowywania danych, planu i limitów. PoliSSH nie dołącza automatycznie sekretów z pęku kluczy ani całej historii terminala do żądań generowania poleceń przy kursorze. Samodzielnie wysłany tekst lub kontekst nadal może zawierać dane poufne. Sprawdzaj prompty i proponowane polecenia przed użyciem.

## Aktualizacje i strona

Sparkle sprawdza publiczny kanał aktualizacji na GitHub Pages i pobiera podpisane paczki z GitHub Releases. Automatyczne sprawdzanie jest domyślnie włączone; można je wyłączyć w Ustawienia → Ogólne → Aktualizacje. Automatyczna instalacja i przesyłanie profilu systemowego Sparkle są wyłączone. Zapytanie ujawnia hostingowi zwykłe metadane sieciowe, np. adres IP. Stronę i pliki obsługuje GitHub zgodnie ze swoim [oświadczeniem o prywatności](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

## Pomoc, kopie i usuwanie

Zgłoszenia GitHub są publiczne. Przed wysłaniem usuń hasła, klucze prywatne, tokeny, prywatne adresy i dane osobowe z logów oraz zrzutów ekranu. [Pomoc i odzyskiwanie](support.md) opisuje lokalizacje danych i ograniczenia kopii. Odinstalowanie aplikacji nie usuwa bazy, wpisów pęku kluczy, nagrań ani danych chmurowych. Usuń je osobno dopiero po zachowaniu potrzebnej kopii. Pytania i prośby dotyczące prywatności kieruj na [hello@almostsensible.com](mailto:hello@almostsensible.com). Nie wysyłaj haseł ani kluczy prywatnych.
