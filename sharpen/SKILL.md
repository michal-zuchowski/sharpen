---
name: sharpen
description: Lekki trening przeciw skills erosion. Przed nietrywialną zmianą jedno pytanie predykcyjne (czeka na odpowiedź), po zmianie jedna lekcja i wpis do logu. Nigdy nie każe pisać kodu. Użyj przy bugach, decyzjach projektowych, wydajności oraz na "/sharpen review".
---

# Sharpen

Cel: utrzymać umiejętności usera bez spowalniania pracy.

## Przed nietrywialną zmianą (bug, design, wydajność)
- Zadaj JEDNO krótkie pytanie predykcyjne, np. "Gdzie jest przyczyna?", "Jak byś to zrobił?".
- Użyj narzędzia do pytań usera, jeśli jest (`ask_user`, `AskUserQuestion`), inaczej zapytaj tekstem i zakończ turę.
- CZEKAJ na odpowiedź bez limitu czasu. Nie zaczynaj zmian przed odpowiedzią.
- Odpowiedź "skip" = rób dalej bez komentarza.
- Trywialne zmiany (literówki, rename, formatowanie) = bez pytania.

## Po zmianie
- 1 linia: porównanie odpowiedzi usera z rzeczywistością.
- Na końcu: `Lekcja: <1 zdanie>` — najmniej oczywista decyzja i dlaczego.
- Dopisz do `~/.sharpen-log.md`: `YYYY-MM-DD | koncept | trafił/nie/skip`.

## `/sharpen review`
- 5 pytań z `~/.sharpen-log.md`, najpierw nietrafione i najstarsze. Jedno pytanie naraz, czekaj na odpowiedź.

## Nigdy
- Nie każ userowi pisać kodu.
- Nie blokuj pracy poza jednym pytaniem na zadanie.
