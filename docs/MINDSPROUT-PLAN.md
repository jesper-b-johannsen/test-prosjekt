# MindSprout — byggeplan for første mobilprototype

Status: plan, ikke implementert. Arbeidsnavnet er foreløpig og ikke varemerkeklarert.

## 1. Beslutningen vi skal kunne ta

Kan to korte, forståelige og morsomme spill gi en god daglig tenkepause på telefonen?

Første prototype skal gjøre det mulig å vurdere dette uten konto, betaling, reklame eller App Store-installasjon. Den eksisterende Block Meadow-versjonen beholdes som referanse. Nytt arbeid legges separat under `mindsprout/`.

## 2. Produkt og målgruppe

- Foreløpig målgruppe: voksne og eldre ungdommer som liker rolige puslespill. Dette er en arbeidshypotese, ikke en besluttet aldersmerking.
- Beskrivelse: «Din daglige tenkepause. Lek med former, planlegging og hukommelse.»
- Personlighet: varm, rolig, leken og tydelig. Ingen medisinsk innramming eller prestasjonspress.
- Hovedspråk i prototypen: norsk. Alle brukerrettede tekster samles slik at engelsk kan legges til senere.
- Tilgjengelighet: store trykkflater, tydelige kontraster, symboler i tillegg til farger, støtte for redusert bevegelse og tastatur.
- Vi lover ikke høyere IQ, bedre hverdagsfunksjon, demensforebygging eller en dokumentert effekt av en bestemt daglig spilletid.

## 3. Første skjerm og navigasjon

Forsiden viser MindSprout, en kort beskrivelse og to valg:

1. **Dagens tenkepause**: en avgrenset økt med begge spillene.
2. **Spill fritt**: velg Block Meadow eller Husk mønsteret.

En synlig «Fortsett»-knapp vises når en uferdig runde finnes. Hjelp og innstillinger er tilgjengelige uten å starte spill. Ingen automatisk avspilt lyd eller ubedt installasjonsdialog.

Navigasjonsflyt:

Forside → kort introduksjon → første spill → rolig overgang → andre spill → oppsummering → forside eller fri spilling.

Det skal alltid være mulig å gå tilbake. Ved avbrudd lagres fremgang, og brukeren får et klart valg om å fortsette eller starte på nytt.

## 4. Block Meadow

### Fri spilling

Behold kjernen fra eksisterende prototype:

- 8 × 8 ruter, tre klosser om gangen, ingen rotasjon.
- Dra og slipp, samt velg-kloss-og-trykk-på-rute som alternativ.
- Hele rader og kolonner fjernes samtidig; kryssende ruter fjernes én gang.
- Alle tre klosser må brukes før tre nye deles ut.
- Runden slutter når ingen gjenværende kloss får plass.
- Poeng: 1 per plassert rute, 80 per full linje, 40 ekstra per linje etter den første i samme trekk. Påfølgende trekk med linjerydding gir 30 × (kombolengde − 1) i tillegg.
- Ingen skjult endring i vanskelighetsgrad for å fremme kjøp eller annonsevisning.

### Forbedringer som må med

- Lagre brett, gjenværende klosser, poeng og kombo etter hvert fullført trekk.
- Ved gjenopptakelse vises nøyaktig samme brett og klosser.
- Berøringsstyringen må holde klossen synlig over fingeren. Forhåndsvisning og faktisk plassering må stemme overens.
- På små skjermer må klossene være tilgjengelige samtidig som brettet kan brukes. Unngå at spilleren må dra fra en skuff som ligger utenfor skjermen.
- En avbrutt draoperasjon endrer ikke brettet.
- Ny runde under en aktiv runde krever en tydelig bekreftelse.
- Rekord for fri spilling vises separat fra dagsøkten.

### I dagsøkten

En kort variant avsluttes etter 12 gyldige plasseringer, eller tidligere hvis ingen trekk er mulige. Det er ingen nedtelling. Begge utfall leder videre til hukommelsesspillet; brukeren straffes ikke for et fullt brett.

Vis «Trekk 4 av 12», ikke en intelligensvurdering. Samme lokale dato gir samme opprinnelige klossrekkefølge på samme algoritmeversjon. Vi påstår ikke global konkurranselikhet eller manipulasjonssikkerhet i denne prototypen.

## 5. Husk mønsteret

### Spilleregel

1. Spilleren trykker «Vis mønster» når vedkommende er klar.
2. Noen ruter på et lite brett markeres med både farge og et blad-symbol.
3. Mønsteret vises i 3 sekunder og skjules deretter. Kort overgang gjør faseskiftet tydelig.
4. Spilleren markerer rutene som ble vist. Et nytt trykk fjerner en markering.
5. «Sjekk svar» blir tilgjengelig når riktig antall ruter er valgt. Det er ingen tidsfrist på svaret.
6. Riktig svar gir en rolig bekreftelse. Ved feil vises både manglende og feilvalgte ruter, med ulike symboler og forklaring.
7. Spilleren trykker selv «Neste». Ingen automatisk overgang mens spilleren leser tilbakemeldingen.

### Vanskelighetsgrad

- Start med 3 markerte ruter på et 3 × 3-brett.
- Minimum 2 og maksimum 6 markerte ruter.
- 2–4 markerte ruter bruker 3 × 3-brett; 5–6 bruker 4 × 4-brett.
- Vurder siste fem besvarte oppgaver på gjeldende nivå. Minst fire riktige øker nivået med ett. To feil på rad senker nivået med ett.
- Nullstill vurderingsvinduet etter et nivåskifte, slik at én gammel feilserie ikke utløser flere nedjusteringer.
- Ingen doble ruter i samme mønster. En feil endrer ikke forklaringen eller reglene midt i oppgaven.
- Brukeren kan velge et lettere nivå manuelt. Det merkes som et valg, ikke som et nederlag.
- En øvingsoppgave med forklaring teller ikke i resultatet.

### Lengde og visning

Dagsøkten har seks besvarte oppgaver. Fri spilling tilbys i bolker på seks med et valgfritt «Spill seks til». Vis «4 av 6 mønstre gjenskapt», aldri «hukommelsen din er forbedret med X prosent» eller «hjernealder».

Hjelpefunksjonen «Vis igjen» kan brukes i fri øving. Oppgaven merkes da som øving og telles ikke som et selvstendig riktig svar.

## 6. Dagens tenkepause og avslutning

- Består av 12 klossplasseringer og seks hukommelsesoppgaver, med mulighet til å ta pause eller avslutte når som helst.
- Vi måler faktisk øktlengde i brukertest før vi beskriver den som eksempelvis «5–10 minutter». Ingen tidslengde er en dokumentert helsedose.
- Et fullført forsøk i begge spill fullfører dagsøkten uansett poengsum. En utfordring kan hoppes over; oppsummeringen viser da hva som faktisk er gjennomført, og markerer økten som delvis fullført.
- Én enkel planteillustrasjon gis for fullført dagsøkt. Ingen butikk eller større hagebygger i første versjon.
- Fullføringsbelønningen gis høyst én gang per lokal dato. Spilleren kan likevel spille mer eller gjenta økten.
- Ingen tapt fremgang, visnende planter eller skamtekst hvis en dag hoppes over.
- Oppsummering: gjennomførte deler, faktisk poengsum/riktige oppgaver, eventuell plante og valg mellom «Ferdig for i dag» og «Spill fritt».

## 7. Lagring, personvern og teknisk ramme

- Første versjon er en statisk nettside med HTML, CSS og JavaScript. Ingen serverkonto, betalingssystem eller eksterne analyse-/reklamebiblioteker.
- Ingen eksterne skrifttyper eller bilder er nødvendige for spilling.
- Lokal lagring får en versjonert struktur med validering av typer, grenser og brettstørrelse.
- Lagre innstillinger, fri spillrunde, hukommelsesprogresjon, lokal dagsdato, dagsøktens fremgang og opptjente planteillustrasjoner.
- Delvise animasjoner skal ikke lagres som uferdige spillhandlinger. Et gjenopptatt brett skal allerede ha fjernet fullførte linjer og oppdatert poeng riktig.
- Ved skadet lagring: behold alt som kan valideres, forklar at en runde måtte nullstilles, og tilby ny runde uten krasj.
- Ved blokkert/full lokal lagring: spillet fortsetter i minnet med tydelig beskjed om at fremgang ikke kan bevares.
- Lokal lagring følger nettleser og nettadresse. Ingen løfter om synkronisering mellom Mac, telefon eller ulike domener.
- Vi samler ikke inn testdata automatisk. Første brukerinnsikt hentes gjennom frivillig tilbakemelding.
- En fremtidig personvernerklæring må også ta hensyn til valgt vertstjenestes logger. «Ingen analysebiblioteker» betyr ikke nødvendigvis at vertstjenesten behandler null data.

## 8. Mobiltilgang — første avhengighet før videre bygging

Målet er en vanlig HTTPS-adresse som kan åpnes på telefonen. Vi skal ikke igjen bruke interne filstier som om de var leveringslenker.

Undersøkt i dette miljøet:

- Prosjektet ligger på GitHub: `jesper-b-johannsen/test-prosjekt`.
- Opplasting av filer via Git har fungert tidligere i samtalen.
- Leseforsøk mot GitHub API med `gh api repos/jesper-b-johannsen/test-prosjekt` svarte `Forbidden`.
- Repositoryets synlighet, GitHub Pages-status og tilgjengelige Pages-rettigheter er derfor ikke bekreftet. Dette beviser ikke at brukerens konto mangler rettigheter eller abonnement.
- Ingen egen publiserings-/hosting-integrasjon er tilgjengelig i denne samtalen.

Første alternativ: GitHub Pages, dersom repositorytype, abonnement og innstillinger tillater det. Alternativ: en statisk vertstjeneste brukeren allerede har eller ønsker å opprette.

Fremgangsmåte:

1. Avklar tilgjengelig vertstjeneste og eventuell konto-/kostnadsforutsetning. Ikke endre repositoryet fra privat til offentlig.
2. Lag publiseringsfilene for valgt løsning og vis konkret hva som blir tilgjengelig. Bare spillmappen skal publiseres; video og andre prosjektfiler skal ikke følge med som nettstedinnhold.
3. Få brukerens godkjenning før første publisering og før eventuelle kostnader.
4. Publiser via tilgjengelig, godkjent tilgang. Hvis en brukerhandling i innstillinger kreves, gi én kort og presis oppgave når brukeren har anledning.
5. Kontroller den faktiske HTTPS-adressen: siden lastes, begge spill starter, ressursene finnes og gjenopptakelse fungerer.
6. Be brukeren åpne den på sin telefon. Påstå ikke at mobiltilgangen er løst før dette er bekreftet.

En ZIP-fil kan brukes som PC-reserve, men er ikke løsningen på mobiltilgang. App Store, domene og årsabonnement er ikke nødvendig for den første prototypetesten.

## 9. Krav for å kalle prototypen ferdig

### Funksjon

- Begge spill kan startes, spilles ferdig, avsluttes og startes på nytt.
- Klosspillet avviser overlapping og plassering utenfor brettet uten å forbruke en kloss.
- Rader/kolonner, kombopoeng, nye klosser og spillavslutning stemmer med reglene.
- Hukommelsesspillet viser og skjuler mønstre i riktig rekkefølge, gir korrekt tilbakemelding og følger nivåreglene.
- Dagsøkten registrerer begge delene riktig, og belønning kan ikke gis dobbelt samme lokale dato ved omlasting.
- Fortsett etter omlasting gir samme stabile spilltilstand og ingen doble poeng.

### Bruk og tilgjengelighet

- Spillbart ved 320, 390 og 430 pikslers mobilbredde uten horisontal rulling.
- Kontroller for spillet har som hovedregel minst 44 × 44 CSS-piksler trykkflate. Selve rutenettet må være kompakt nok til å få plass og testes derfor særskilt for feiltrykk.
- Dra-og-slipp og alternativ trykkplassering fungerer. Ingen funksjon er avhengig av hover.
- Farge er ikke eneste informasjonsbærer i den nye hukommelsesoppgaven.
- Hjelp er tilgjengelig fra spillet. Tastaturfokus er synlig og dialoger kan lukkes.
- Test på Chromium i miljøet; test på fysisk iPhone/Safari og Android/Chrome før en bred mobilklar-påstand.
- Ingen uventede JavaScript-feil under start, runder, avbrudd, gjenopptakelse eller ødelagt lagring.

### Levering

- Én verifisert HTTPS-adresse, ikke en intern filsti.
- Brukeren har åpnet og prøvd begge spill på sin egen telefon.
- Kjent testdekning, begrensninger og utestående feil er oppgitt.

## 10. Første brukertest

Start med eieren og deretter rundt fem frivillige. En større test med 15–20 personer er aktuelt etter at grunnleggende problemer er rettet. Dette er brukertesting, ikke forskning på kognitiv effekt.

Observer uten å forklare først:

1. Forstår personen hva som kan trykkes på?
2. Kan personen plassere tre klosser uten hjelp?
3. Forstår personen husk/se/svar-fasene og tilbakemeldingen?
4. Hvor oppstår feiltrykk, venting eller frustrasjon?
5. Ønsker personen en ny runde, og hvorfor/hvorfor ikke?

Spør etterpå: «Hva var morsomst?», «Hva var uklart?» og «Ville du selv åpnet dette igjen?». Ikke forveksle et hyggelig svar med faktisk tilbakekomst. Spør eventuelt senere om de brukte det igjen, uten å samle inn mer personinformasjon enn nødvendig.

## 11. Forskning og påstander

Følgende etablerte oversikter er utgangspunkt, ikke bevis for effekt av MindSprout. Direkte kildeoppslag ble blokkert i dette miljøet; innhold og nyere forskning må gjennomgås før forskningspåstander brukes i markedsføring.

- Simons mfl. (2016), *Do “Brain-Training” Programs Work?* https://doi.org/10.1177/1529100616661983
- Bediou mfl. (2018), metaanalyse av actionspill og perseptuelle, oppmerksomhetsmessige og kognitive ferdigheter. https://doi.org/10.1037/bul0000130 — spilltype og oppgaver er ikke direkte sammenlignbare med denne appen.
- Dunlosky mfl. (2013), *Improving Students’ Learning With Effective Learning Techniques*. https://doi.org/10.1177/1529100612453266 — handler om læringsteknikker, ikke dokumentert generell intelligensøkning fra puslespill.

Vi beskriver oppgavene som utfordringer for planlegging, romlig problemløsing og visuell korttidshukommelse. Vi bruker ikke forbedret spillscore som bevis på overføring til hverdagen. En slik effektpåstand krever en egnet studie med aktiv sammenligningsgruppe, uavhengige utfallsmål og relevant faglig bistand.

## 12. Arbeidsfordeling og rekkefølge

### Assistenten

1. Ferdigstiller denne planen og undersøker leveringsmulighetene.
2. Når mobiltilgangen er avklart: bygger forside, lokal lagring, forbedret klosspill, hukommelsesspill og dagsøkt i små, testbare trinn.
3. Tester logikk og berøringsflyt, forbereder konkret publisering og rapporterer ærlig hva som er og ikke er kontrollert.
4. Retter de viktigste problemene fra brukerprøving før mer innhold legges til.

### Produkteieren

- Gir korte tilbakemeldinger om opplevelsen. Ingen programmering kreves.
- Hjelper med nødvendig konto-/innstillingshandling når mobilhosting er valgt og det passer å gjøre det.
- Godkjenner første publisering og eventuelle kostnader; ingen abonnement skal kjøpes automatisk.
- Prøver på sin egen telefon og kan senere invitere noen få testere.

### Utenfor første versjon

Betaling, reklame, abonnement, brukerkontoer, skysynkronisering, vennelister, globale topplister, pushvarsler, omfattende hagebygger, flere nye spillmoduser, App Store-publisering og påstander om medisinsk eller generell kognitiv effekt.

### Neste konkrete milepæl

Avklart mobilhosting og deretter en spillbar, testet MindSprout-versjon med to spill som eieren faktisk kan åpne på telefonen. Ingen fast leveringstid eller effektgaranti gis før omfang, tilgang og testing er avklart.
