# MindSprout — mobilprototype 0.2

[Åpne prototypen](https://jesper-b-johannsen.github.io/test-prosjekt/)

To spill og én valgfri dagsøkt. Gratis, ingen konto, ingen analysebiblioteker eller reklame. All spillfremgang lagres lokalt i nettleseren, ikke mellom enheter. Nettstedets vertstjeneste kan føre vanlige tilgangslogger.

## Innhold

- **Block Meadow:** 8 × 8 klosspuslespill, mus, tastatur og berøring; poeng, kombo og lagring av pågående runde.
- **Husk mønsteret:** valgfri øvingsoppgave, tre sekunders visning og ubegrenset svartid. Seks oppgaver med 2–6 blader og et nivå som justeres mellom oppgavene. «Vis igjen» i fri spilling gjør svaret til øving, uten poeng.
- **Dagens tenkepause:** inntil 12 klossplasseringer etterfulgt av seks mønstre. Fullfør begge for én plante per lokal dato. Du kan hoppe over en del, men får da ikke dagens plante.
- **Lagring:** stabile trekk og svar lagres fortløpende. Ved avbrutt mønstervisning starter visningsfasen på nytt. Gyldig fremgang forsøkes beholdt hvis en lagret del er skadet. En beskjed vises hvis lagring er utilgjengelig.
- **Tilgjengelighet:** markeringer med symboler, synlig tastaturfokus, alternativ til dra-og-slipp og redusert bevegelse.

Spillresultatene er ikke en måling av intelligens, helse eller forbedret hukommelse utenfor spillet. Arbeidsnavnet er ikke varemerkeklarert. Dagsøkten har ikke en dokumentert helseeffekt eller foreskrevet tidslengde.

## Kjør lokalt

Fra prosjektroten:

```sh
python3 -m http.server 8000 --directory mindsprout
```

Åpne serveren i nettleseren. JavaScript-modulene må serveres via HTTP; denne versjonen skal ikke åpnes direkte med `file://`.

## Test

```sh
node tests/engine.test.mjs
node tests/browser.cjs
```

Logikktestene bruker bare Node.js. Nettlesertestene krever Playwright og Chromium. De bruker en lokal server på port 8899, lagrer skjermbilder i systemets midlertidige mappe og endrer ikke produksjonsdata. Sett eventuelt `CHROMIUM_EXECUTABLE` til nettleserens kjørbare fil. I dette utviklingsmiljøet er Playwright og systemets Chromium tilgjengelige; prosessbegrensningene krever at nettlesertesten kjøres med godkjent tilgang utenfor sandkassen.

Testomfang: linjer/kolonner, kombo, kollisjoner, deling av klosser, slutt på runde, mønstergenerering, tilpasning av nivå, gjenopptakelse, dagsbytte og én belønning per dag. Nettlesertesten spiller begge spill, bruker tastatur og simulert berøring, kontrollerer øving, avbrudd, utilgjengelig/skadet lagring og mobilgeometri.

Den nye versjonen må også prøves på en fysisk iPhone/Safari og Android/Chrome. Bekreftelsen på at den tidligere Block Meadow-versjonen virket på eierens telefon er ikke en test av de nye funksjonene.

## Publisering

`gh-pages` er nettstedets publiseringsgren. Den skal bare inneholde `index.html`, `style.css`, `app.mjs`, `engine.mjs`, `.nojekyll` og eventuelt den gamle klossversjonen under `classic/`. Kildekode, tester og planer vedlikeholdes på `main`. Ingen videofiler eller øvrige prosjektmapper skal følge med nettstedet.

GitHub Pages kan bruke litt tid på å oppdatere etter opplasting. Kontroller den faktiske HTTPS-adressen før publisering rapporteres som fullført. Vi har ikke API-tilgang til Pages-status i dette miljøet.

## Kjente begrensninger

- Fremgang er knyttet til denne nettleseren og domenet. Ingen skysynkronisering.
- Ingen installert app, frakoblet hurtigbuffer, lyd eller vibrasjon ennå.
- Plantesamlingen er en enkel illustrasjonsrekke, ikke en hagebygger.
- Lokal dato og lokalt lagrede resultater er ikke manipulasjonssikre; ingen globale konkurranser.
- Svært korte skjermer bruker mindre brett. Brettets små ruter må vurderes videre gjennom fysiske brukertester.
