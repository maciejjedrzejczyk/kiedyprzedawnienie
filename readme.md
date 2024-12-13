# Kalkulator Przedawnienia Zobowiązań Podatkowych

## Spis treści
1. [Opis aplikacji](#opis-aplikacji)
2. [Funkcjonalności](#funkcjonalności)
3. [Technologie](#technologie)
4. [Wymagania](#wymagania)
5. [Instrukcja uruchomienia](#instrukcja-uruchomienia)
6. [Budowanie obrazu Docker](#budowanie-obrazu-docker)
7. [Struktura projektu](#struktura-projektu)
8. [Użytkowanie aplikacji](#użytkowanie-aplikacji)
9. [Podstawa prawna](#podstawa-prawna)
10. [Informacja o generowaniu treści](#informacja-o-generowaniu-treści)

## Opis aplikacji

Kalkulator Przedawnienia Zobowiązań Podatkowych to prosta aplikacja webowa, która pomaga użytkownikom obliczyć datę przedawnienia zobowiązań podatkowych. Aplikacja uwzględnia przepisy polskiego prawa podatkowego, zgodnie z którymi zobowiązanie podatkowe przedawnia się z upływem 5 lat, licząc od końca roku kalendarzowego, w którym upłynął termin płatności podatku.

## Funkcjonalności

1. Obliczanie daty przedawnienia dla wprowadzonej daty zdarzenia podatkowego.
2. Wyświetlanie liczby dni pozostałych do przedawnienia.
3. Informowanie o już przedawnionych zobowiązaniach.
4. Wyświetlanie daty, do której wszystkie zobowiązania podatkowe są już niebyłe.

## Technologie

- HTML5
- CSS3
- JavaScript
- Docker
- Nginx (jako serwer w kontenerze)
- Claude 3.5 Sonnet

## Wymagania

- Docker lub Docker Compose

## Instrukcja uruchomienia

1. Sklonuj repozytorium lub skopiuj pliki projektu do lokalnego katalogu.

2. Upewnij się, że masz zainstalowany Docker i Docker Compose.

3. Otwórz terminal i przejdź do katalogu projektu.

4. Zbuduj i uruchom kontener Docker, wykonując polecenie:
   ```
   docker-compose up -d --build
   ```

5. Aplikacja będzie dostępna pod adresem `http://localhost:8080` w przeglądarce internetowej.

6. Aby zatrzymać aplikację, użyj polecenia:
   ```
   docker-compose down
   ```

## Budowanie obrazu Docker

Jeśli chcesz zbudować obraz Docker bez użycia Docker Compose, możesz to zrobić w następujący sposób:

1. Otwórz terminal i przejdź do katalogu projektu.

2. Zbuduj obraz Docker, używając polecenia:
   ```
   docker build -t tax-calculator .
   ```
   Gdzie `tax-calculator` to nazwa, którą nadajesz obrazowi. Możesz ją zmienić według własnych preferencji.

3. Po zbudowaniu obrazu możesz go uruchomić za pomocą polecenia:
   ```
   docker run -d -p 8080:80 tax-calculator
   ```
   To polecenie uruchomi kontener w tle (-d) i zmapuje port 8080 hosta na port 80 kontenera.

4. Aplikacja będzie dostępna pod adresem `http://localhost:8080` w przeglądarce internetowej.

5. Aby zatrzymać kontener, najpierw znajdź jego ID za pomocą polecenia:
   ```
   docker ps
   ```
   A następnie zatrzymaj go, używając:
   ```
   docker stop <container_id>
   ```

Pamiętaj, że budowanie obrazu Docker w ten sposób jest alternatywą dla użycia Docker Compose. W większości przypadków zaleca się korzystanie z Docker Compose, szczególnie gdy aplikacja staje się bardziej złożona lub gdy pracujesz z wieloma kontenerami.

## Struktura projektu

```
projekt/
├── Dockerfile
├── docker-compose.yml
└── index.html
```

- `Dockerfile`: Definiuje obraz Docker dla aplikacji.
- `docker-compose.yml`: Konfiguracja Docker Compose do uruchomienia aplikacji.
- `index.html`: Główny plik HTML zawierający kod aplikacji.

## Użytkowanie aplikacji

1. Otwórz aplikację w przeglądarce (`http://localhost:8080`).
2. Wprowadź datę zdarzenia podatkowego w polu "Wprowadź datę zdarzenia podatkowego".
3. Kliknij przycisk "Oblicz".
4. Aplikacja wyświetli:
   - Wprowadzoną datę zdarzenia podatkowego
   - Aktualną datę
   - Datę przedawnienia zobowiązania
   - Liczbę dni pozostałych do przedawnienia (jeśli zobowiązanie jeszcze się nie przedawniło)
   - Informację o przedawnieniu (jeśli zobowiązanie już się przedawniło)
   - Datę, do której wszystkie zobowiązania podatkowe są już niebyłe

## Podstawa prawna

Aplikacja opiera się na Art. 70. Ordynacji podatkowej, który reguluje kwestię przedawnienia zobowiązań podatkowych. Pełny tekst artykułu jest dostępny pod linkiem umieszczonym w aplikacji.

## Informacja o generowaniu treści

Ten projekt został wykonany przy pomocy sztucznej inteligencji, konkretnie z wykorzystaniem modelu językowego GPT. Oto podstawowe informacje o procesie tworzenia:

- Asystent AI: Claude 3.5 Sonnet
- Język komunikacji: Polski
- Czas trwania konwersacji: Około 2-3 godziny (szacunkowo, na podstawie długości i złożoności wątku)
- Liczba interakcji: Około 15-20 wymian (pytanie-odpowiedź)

Główne etapy tworzenia projektu z pomocą AI:

1. Stworzenie podstawowej struktury aplikacji HTML/CSS/JavaScript
2. Implementacja logiki obliczania dat przedawnienia
3. Dodanie funkcjonalności wprowadzania własnej daty przez użytkownika
4. Stworzenie dokumentacji projektu
5. Przygotowanie plików do konteneryzacji (Dockerfile, docker-compose.yml)
6. Instrukcje dotyczące tworzenia i publikacji repozytorium GitHub
7. Dodanie informacji o licencji (Apache 2.0)
8. Implementacja zastrzeżenia prawnego (disclaimer)

Warto zauważyć, że choć kod i dokumentacja zostały wygenerowane przez AI, ostateczna weryfikacja, testowanie i wdrożenie były wykonywane przez człowieka. AI służyło jako narzędzie wspomagające proces twórczy i implementacyjny, ale nie zastępowało ludzkiego osądu i decyzji.

Projekt ten stanowi przykład współpracy człowieka z AI w tworzeniu aplikacji webowej, demonstrując potencjał takich narzędzi w przyspieszaniu procesu rozwoju oprogramowania.
