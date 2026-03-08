# Quiz_Web

Najlepszy stack
Na start polecałbym Ci FastAPI zamiast Django, bo jest prostsze do nauki, nowoczesne i ma wbudowane wsparcie dla WebSocketów w dokumentacji, co bardzo pasuje do quizu 1 na 1.
Do tego dobry zestaw będzie wyglądał tak:
    • Frontend: HTML, CSS, JavaScript.
    • Stylowanie: Bootstrap albo zwykły CSS.
    • Backend: Python + FastAPI.
    • Komunikacja realtime: WebSocket.
    • Baza danych: SQLite na start, później PostgreSQL.
    • ORM: SQLAlchemy.
    • Serwer aplikacji: Uvicorn.
    • Reverse proxy i domena: Nginx.
    • Wdrożenie: Docker opcjonalnie, ale warto.
Frontend
Frontend powinien być prosty, bo najważniejsza logika będzie po stronie backendu. Wystarczy Ci strona logowania lub wejścia do pokoju, widok lobby, ekran quizu, licznik czasu, pytanie z odpowiedziami i ekran wyniku.
Na frontendzie ucz się w tej kolejności:
    1. HTML — struktura strony.
    2. CSS lub Bootstrap — wygląd.
    3. JavaScript — kliknięcia, pobieranie danych z API, obsługa WebSocket.
Minimalnie frontend powinien umieć:
    • utworzyć pokój quizowy,
    • dołączyć drugiego gracza po kodzie pokoju,
    • wyświetlać pytania,
    • wysyłać odpowiedzi,
    • pokazywać wynik na żywo,
    • reagować na zdarzenia z serwera, np. „gracz 2 dołączył” albo „koniec rundy”.
Backend w Pythonie
Backend będzie sercem całej aplikacji. FastAPI obsłuży klasyczne endpointy HTTP, np. tworzenie pokoju, logowanie, pobranie pytań, a WebSocket obsłuży komunikację na żywo między dwoma graczami.
Tu warto podzielić aplikację na moduły:
    • użytkownicy,
    • pokoje quizowe,
    • pytania i kategorie,
    • rozgrywka,
    • wyniki,
    • komunikacja WebSocket.
Przykładowe zadania backendu:
    • utworzenie pokoju z unikalnym kodem,
    • przypisanie 2 graczy do jednego quizu,
    • pilnowanie stanu gry na serwerze,
    • sprawdzanie poprawności odpowiedzi,
    • naliczanie punktów,
    • synchronizacja czasu rundy,
    • zapis wyników do bazy danych.​​
Baza danych
Na początek użyj SQLite, bo jest bardzo prosta i nie musisz nic osobno instalować. Gdy aplikacja zacznie działać dobrze, możesz przejść na PostgreSQL, który lepiej nadaje się do wdrożenia na serwerze.​
Najważniejsze tabele:
    • users,
    • quiz_rooms,
    • questions,
    • answers,
    • matches,
    • match_results.​
Do nauki w Pythonie przyda Ci się:
    • SQLAlchemy do modeli bazy,
    • Pydantic do walidacji danych wejściowych,
    • Alembic do migracji bazy, jeśli zechcesz robić to bardziej profesjonalnie.​
Wdrożenie
Skoro masz już serwer i domenę, końcowy układ może wyglądać tak: użytkownik wchodzi przez domenę, Nginx odbiera ruch, przekazuje aplikację do FastAPI/Uvicorn, a aplikacja łączy się z bazą danych.
Przy WebSocketach ważne jest, żeby reverse proxy poprawnie przekazywało połączenia upgrade, bo bez tego komunikacja realtime może nie działać.​
Kolejność prac proponuję tak:
    1. Zrób frontend jednej strony quizu bez backendu.
    2. Zrób backend FastAPI z prostym REST API.
    3. Dodaj SQLite i zapis pytań/wyników.
    4. Dodaj WebSocket dla pokoju 2-osobowego.
    5. Zrób logikę punktacji i timer.
    6. Wystaw aplikację przez Uvicorn + Nginx na domenie.
    7. Na końcu dopracuj wygląd i testy.
Co wybrałbym na Twoim miejscu
Jeśli chcesz się nauczyć Pythona i nie komplikować sobie życia, to wybrałbym taki zestaw: FastAPI + HTML/CSS/JS + SQLite + SQLAlchemy + WebSocket + Nginx. Taki stack jest wystarczająco prosty na inżynierkę, a jednocześnie wygląda nowocześnie i daje Ci realny projekt do pokazania.
Proponowany temat pracy może brzmieć tak: „Projekt i implementacja webowej aplikacji quizowej w Pythonie z rozgrywką w czasie rzeczywistym dla dwóch użytkowników”.
Ja bym Ci też polecił taki zakres funkcjonalny:
    • rejestracja lub gra jako gość,
    • tworzenie pokoju i dołączanie kodem,
    • quiz 1 vs 1,
    • timer odpowiedzi,
    • ranking i historia gier,
    • panel admina do dodawania pytań.
Najprostsza wersja MVP:
    • 2 graczy,
    • 1 pokój,
    • 10 pytań,
    • 4 odpowiedzi,
    • punkty i wynik końcowy,
    • jeden admin dodający pytania ręcznie.​
Dobra ścieżka nauki dla Ciebie:
    • najpierw Python podstawy,
    • potem FastAPI,
    • potem HTML/CSS/JS,
    • potem baza danych,
    • potem WebSocket,
    • na końcu wdrożenie na serwer.
