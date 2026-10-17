# MindSprout — mobilprototype 0.3

[Åpne prototypen](https://jesper-b-johannsen.github.io/test-prosjekt/)

To spill, en valgfri dagsøkt og en egen læringsquiz. Gratis, ingen konto, ingen analysebiblioteker eller reklame. All spillfremgang lagres lokalt i nettleseren, ikke mellom enheter. Nettstedets vertstjeneste kan føre vanlige tilgangslogger.

## Innhold

- **Block Meadow:** 8 × 8 klosspuslespill, mus, tastatur og berøring; poeng, kombo og lagring av pågående runde.
- **Husk mønsteret:** valgfri øvingsoppgave, tre sekunders visning og ubegrenset svartid. Seks oppgaver med 2–6 blader og et nivå som justeres mellom oppgavene. «Vis igjen» i fri spilling gjør svaret til øving, uten poeng.
- **Dagens tenkepause:** inntil 12 klossplasseringer etterfulgt av seks mønstre. Fullfør begge for én plante per lokal dato. Du kan hoppe over en del, men får da ikke dagens plante.
- **Dagens nysgjerrighet:** fem spørsmål per runde, fire temaer eller blandet, forklaringer etter alle svar og kildelenker. 24 håndskrevne pilotspørsmål finnes på norsk og engelsk; quizgrensesnittet har separate språkressurser. Appen vises fortsatt på norsk. Quiz er foreløpig en egen aktivitet og kreves ikke for dagsplanten.
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
node tests/quiz.test.mjs
node tests/quiz-browser.cjs
```

Logikktestene bruker bare Node.js. Nettlesertestene krever Playwright og Chromium. De bruker en lokal server på port 8899, lagrer skjermbilder i systemets midlertidige mappe og endrer ikke produksjonsdata. Sett eventuelt `CHROMIUM_EXECUTABLE` til nettleserens kjørbare fil. I dette utviklingsmiljøet er Playwright og systemets Chromium tilgjengelige; prosessbegrensningene krever at nettlesertesten kjøres med godkjent tilgang utenfor sandkassen.

Testomfang: linjer/kolonner, kombo, kollisjoner, deling av klosser, slutt på runde, mønstergenerering, tilpasning av nivå, gjenopptakelse, dagsbytte og én belønning per dag. Nettlesertesten spiller begge spill, bruker tastatur og simulert berøring, kontrollerer øving, avbrudd, utilgjengelig/skadet lagring og mobilgeometri.

Den nye versjonen må også prøves på en fysisk iPhone/Safari og Android/Chrome. Bekreftelsen på at den tidligere Block Meadow-versjonen virket på eierens telefon er ikke en test av de nye funksjonene.

## Publisering

`gh-pages` er nettstedets publiseringsgren. Den skal bare inneholde `index.html`, `style.css`, `app.mjs`, `engine.mjs`, `quiz.mjs`, `quiz-engine.mjs`, `quiz-data.mjs`, `.nojekyll` og eventuelt den gamle klossversjonen under `classic/`. Kildekode, tester og planer vedlikeholdes på `main`. Ingen videofiler eller øvrige prosjektmapper skal følge med nettstedet.

GitHub Pages kan bruke litt tid på å oppdatere etter opplasting. Kontroller den faktiske HTTPS-adressen før publisering rapporteres som fullført. Vi har ikke API-tilgang til Pages-status i dette miljøet.

## Kjente begrensninger

- Fremgang er knyttet til denne nettleseren og domenet. Ingen skysynkronisering.
- Ingen installert app, frakoblet hurtigbuffer, lyd eller vibrasjon ennå.
- Plantesamlingen er en enkel illustrasjonsrekke, ikke en hagebygger.
- Lokal dato og lokalt lagrede resultater er ikke manipulasjonssikre; ingen globale konkurranser.
- Svært korte skjermer bruker mindre brett. Brettets små ruter må vurderes videre gjennom fysiske brukertester.

## Quiz: læringsmodell og begrensninger

- Repetisjon styres per spørsmål og lagres i en separat, versjonert nøkkel (`mindsprout-quiz-v1`), slik at tidligere spillfremgang bevares.
- Feil svar planlegges til neste lokale dato. Riktige første svar planlegges etter henholdsvis 3, 7, 14, 30 og maksimalt 60 dager etter stigende antall riktige gjensyn. Bare første forsøk per spørsmål per dato påvirker denne planen; gjentatte runder samme dag blåser ikke opp mestringsnivået.
- Forfalte spørsmål innen valgt tema prioriteres, deretter nye. Den lille spørsmålsbanken kan ikke alltid fylle fem plasser med bare nye eller forfalte spørsmål; ekstra plasser kan derfor inneholde kjente spørsmål som ennå ikke er forfalt. Dette er forklart i appen.
- Intervallene er produktvalg. De er ikke klinisk validert, ikke dokumentert optimalt tilpasset den enkelte, og quizresultatet er ingen intelligensmåling.
- Forskningsreferanse i appen: Dunlosky mfl. (2013), *Improving Students’ Learning With Effective Learning Techniques*, DOI 10.1177/1529100612453266. Oversikten støtter gjenhenting og fordelt øving som læringsteknikker, ikke en effektpåstand om denne prototypen.
- Faktaspørsmålene er nyskrevne og lenker til NASA, NOAA, OpenStax og andre oppgitte fagkilder. Kildelenkene og forskningsreferansen kunne ikke åpnes fra utviklingsmiljøet (nettverksproxy svarte 403). Live innhold, alle lenkemål og samsvar med kildeavsnitt må derfor gjennomgås før en offentlig kvalitets-/forskningsgaranti gis. Datatestene kontrollerer struktur og fasitkobling, ikke vitenskapelig sannhet.
- Neste innholdsarbeid: faktagjennomgang, større spørsmålsbank, nivåvalg og fullstendig engelsk grensesnitt. Engelsk quizinnhold er forberedt; resten av appen er ikke oversatt ennå.
