Dlaczego kopiowanie zasobów lokalizacyjnych lub fragmentów xml/html do programu Excel jest uważane za złą praktykę?

1. Ponieważ są one dostosowane do narzędzi CAT. Typowe narzędzia CAT mogą obsługiwać powszechne treści przydatne dla zasobów UI, stron internetowych lub dokumentacji. Jeśli używasz jakichkolwiek zmiennych, CAT chroni je przed tłumaczeniem. Excel nie potrafi tego zrobić.
2. Ponieważ tłumacze potrzebują pełnego kontekstu, aby właściwie przetłumaczyć zasoby. Pliki JSON lub YAML *ukrywają* wiele przydatnych informacji, takich jak komentarze, identyfikatory kluczy lub informacje pochodzące z sekwencji ciągów w pliku (np. gdy etykiety przycisków są grupowane razem). Nie przenoś ciągów do programu Excel - można w ten sposób pozbawić je kontekstu.
3. Ponieważ po skopiowaniu do programu Excel możesz dodać dwa kroki: sortowanie ciągów alfabetycznie i usuwanie duplikatów. Nie rób tego - możesz pozbawić ciągi ich naturalnego kontekstu (patrz powyżej). Możesz usunąć dobrą redundancję, która pozwala na tłumaczenie tego samego słowa w różnych kontekstach.
4. Ponieważ możesz spowodować błędy - niekompletne eksportowanie lub importowanie, problemy z kodowaniem, pomyłki między polskim a portugalskim lub chińskim tradycyjnym a uproszczonym. Nie próbuj tego.

**Jak zatem przetłumaczyć zasoby?**

1. Najpierw spróbuj wyeksportować je z Twojego systemu zarządzania treścią lub narzędzia programistycznego w pierwotnej formie. Wyślij próbkę eksportu do doświadczonego tłumacza lub dostawcy usług tłumaczeniowych (LSP) i zapytaj, czy format jest przyjazny dla narzędzi CAT.
2. Jeśli nie jest, sprawdź możliwości innych formatów eksportu dostępnych w Twoim narzędziu: JSON, PO, XLIFF?
3. Użyj programu Excel (lub CSV) tylko wtedy, gdy żaden z powyższych nie działa.  
Jak to zrobić prawidłowo:
- Włączaj klucze i komentarze wraz z tekstem do tłumaczenia - jako oddzielne kolumny i wiersze(!);
- Nie sortuj - nie zmieniaj struktury zawartości;
- Nie usuwaj duplikatów - tłumacze również z nich korzystają!
- Sprawdź, czy nie ma błędów, takich jak ciągi podzielone na kilka wierszy, konwersja waluty na datę itp.
