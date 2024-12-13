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

## Wymagania

- Docker
- Docker Compose

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