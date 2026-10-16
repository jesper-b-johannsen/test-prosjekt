# Block Meadow

Et selvstendig klosspuslespill for nettleseren. Eget navn, utseende og kode; inspirert av sjangeren med klosser som fyller rader og kolonner.

## Spill på Mac eller PC

1. [Last ned Block-Meadow.zip](https://github.com/jesper-b-johannsen/test-prosjekt/raw/refs/heads/main/Block-Meadow.zip).
2. Pakk ut ZIP-filen (på Mac: dobbeltklikk).
3. Dobbeltklikk `Block-Meadow.html`. Spillet åpnes i nettleseren.

Ingen installasjon, konto, nettforbindelse eller betalt tjeneste er nødvendig. På mobil er en publisert nettside enklere enn en lokal HTML-fil. Spillet er responsivt og støtter berøring, men nettsiden er ikke publisert ennå.

## Slik spiller du

- Dra klosser til brettet, eller velg en kloss og klikk/trykk på ruten der klossens øverste venstre hjørne skal være.
- Fyll en hel rad eller kolonne for å fjerne den.
- Bruk alle tre klossene for å få tre nye. Klossene kan ikke roteres.
- Spillet slutter når ingen av de gjenværende klossene får plass.
- Tastatur: velg en kloss med Enter, flytt fokus til brettet med Tab, bruk piltastene og plasser med Enter.

Hver plasserte rute gir 1 poeng, hver linje 80 poeng. Flere linjer i samme trekk gir 40 ekstra poeng per linje etter den første. Påfølgende trekk med linjerydding gir en stigende kombobonus på 30 poeng. Rekorden lagres i nettleseren når lokal lagring er tilgjengelig. En pågående runde lagres ikke.

## Utvikling og kontroll

Kildekoden er samlet i `index.html`, uten eksterne avhengigheter. Åpne filen direkte, eller kjør `python3 -m http.server 8000` fra denne mappen og åpne den lokale siden i nettleseren.

Kontrollert i Chromium med Playwright: plassering med mus og berøring, valg og klikk, grense- og kollisjonskontroll, samtidig fjerning av rader/kolonner, poeng og kombobonus, nye klosser, spillavslutning, omstart og lagring av rekord. Mobiloppsettet er kontrollert med en emulert berøringsenhet; fysiske iOS-/Android-enheter og Safari er ikke testet.
