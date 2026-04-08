# Kalkulator Przedawnienia Zobowiązań Podatkowych / Tax Liability Statute of Limitations Calculator

[🇵🇱 Polski](#polski) | [🇬🇧 English](#english)

---

## <a name="polski"></a>🇵🇱 Wersja Polska

### Spis treści
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


---

## <a name="english"></a>🇬🇧 English Version

### Table of Contents
1. [Application Description](#application-description)
2. [Features](#features)
3. [Technologies](#technologies)
4. [Requirements](#requirements)
5. [Running Instructions](#running-instructions)
6. [Building Docker Image](#building-docker-image)
7. [Project Structure](#project-structure)
8. [Application Usage](#application-usage)
9. [Legal Basis](#legal-basis)
10. [Content Generation Information](#content-generation-information)

## Application Description

The Tax Liability Statute of Limitations Calculator is a simple web application that helps users calculate the expiration date of tax liabilities. The application takes into account Polish tax law provisions, according to which a tax liability expires after 5 years, counting from the end of the calendar year in which the tax payment deadline expired.

## Features

1. Calculating the statute of limitations date for an entered tax event date.
2. Displaying the number of days remaining until expiration.
3. Informing about already expired liabilities.
4. Displaying the date by which all tax liabilities have already expired.

## Technologies

- HTML5
- CSS3
- JavaScript
- Docker
- Nginx (as server in container)
- Claude 3.5 Sonnet

## Requirements

- Docker or Docker Compose

## Running Instructions

1. Clone the repository or copy the project files to a local directory.

2. Make sure you have Docker and Docker Compose installed.

3. Open a terminal and navigate to the project directory.

4. Build and run the Docker container by executing the command:
   ```
   docker-compose up -d --build
   ```

5. The application will be available at `http://localhost:8080` in your web browser.

6. To stop the application, use the command:
   ```
   docker-compose down
   ```

## Building Docker Image

If you want to build the Docker image without using Docker Compose, you can do so as follows:

1. Open a terminal and navigate to the project directory.

2. Build the Docker image using the command:
   ```
   docker build -t tax-calculator .
   ```
   Where `tax-calculator` is the name you give to the image. You can change it according to your preferences.

3. After building the image, you can run it with the command:
   ```
   docker run -d -p 8080:80 tax-calculator
   ```
   This command will run the container in the background (-d) and map port 8080 of the host to port 80 of the container.

4. The application will be available at `http://localhost:8080` in your web browser.

5. To stop the container, first find its ID using the command:
   ```
   docker ps
   ```
   Then stop it using:
   ```
   docker stop <container_id>
   ```

Remember that building the Docker image this way is an alternative to using Docker Compose. In most cases, it is recommended to use Docker Compose, especially when the application becomes more complex or when working with multiple containers.

## Project Structure

```
project/
├── Dockerfile
├── docker-compose.yml
└── index.html
```

- `Dockerfile`: Defines the Docker image for the application.
- `docker-compose.yml`: Docker Compose configuration to run the application.
- `index.html`: Main HTML file containing the application code.

## Application Usage

1. Open the application in your browser (`http://localhost:8080`).
2. Enter the tax event date in the "Enter tax event date" field.
3. Click the "Calculate" button.
4. The application will display:
   - The entered tax event date
   - The current date
   - The liability expiration date
   - The number of days remaining until expiration (if the liability has not yet expired)
   - Information about expiration (if the liability has already expired)
   - The date by which all tax liabilities have already expired

## Legal Basis

The application is based on Article 70 of the Tax Ordinance Act, which regulates the issue of tax liability expiration. The full text of the article is available via the link provided in the application.