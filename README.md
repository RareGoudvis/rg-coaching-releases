# RG Coaching

RG Coaching is een gratis Windows-programma voor jeugd- en amateurvoetbaltrainers. Het heeft vier onderdelen: **Training** (oefeningen tekenen en in een bibliotheek bewaren), **Matchplan** (opstelling, wissels en eerlijke speeltijd, de affiche voor de ouders en je seizoenskalender), **Videoanalyse** (wedstrijden taggen, clips maken en tonen) en **Bord** (een tactisch bord met dia's). Alles werkt op je eigen computer: je hebt geen account nodig en je gegevens verlaten je pc niet.

Op deze pagina haal je de app op. Het programma zelf en de broncode staan niet hier; zie [Privacy](#privacy).

## Downloaden en installeren

Ga naar de [nieuwste uitgave](https://github.com/RareGoudvis/rg-coaching-releases/releases/latest) en kies onder **Assets** een van de twee bestanden:

- **`RG.Coaching_<versie>_x64-setup.exe`** is de gewone installer. Dubbelklik, volg de stappen, klaar. Hij installeert alleen voor jouw Windows-gebruiker, dus je hebt geen beheerdersrechten nodig.
- **`RG.Coaching_<versie>_x64-portable.zip`** is de versie zonder installatie (er is er een sinds 0.7.0). Pak de zip uit en start `RG Coaching.exe`. Je kan de map verplaatsen of op een USB-stick zetten. Je werk staat ook bij de portable niet naast het programma, maar in `Documenten\RG Coaching`.

### Windows waarschuwt voor een onbekende maker

Bij het starten van de installer (of van de portable) kan Windows SmartScreen melden dat de maker onbekend is. Het bestand is niet ondertekend met een certificaat, en dat is het enige wat die melding zegt. Kies **Meer info** en daarna **Toch uitvoeren**.

### Wat heb je nodig

- Windows 10 of 11, 64-bit.
- Het onderdeel *Microsoft Edge WebView2 Runtime*. Dat zit op elke Windows 11 en op Windows 10 met Edge. Ontbreekt het toch, installeer het dan via Microsoft.
- Voor Videoanalyse is niets extra nodig: ffmpeg (om clips te maken en lastige videobestanden om te zetten) zit in de app.

## Bijwerken

Als er een nieuwere versie is, zegt de app het zelf: bovenaan verschijnt een balkje met een knop die je naar deze pagina brengt. Je downloadt de nieuwe installer en installeert die gewoon over de oude heen. Het balkje is weg te klikken. De app kijkt bij het opstarten en telkens als je terugkomt naar het venster, hoogstens één keer per uur.

- **Je werk blijft staan.** Een update raakt je map met trainingen, wedstrijdplannen en analyses niet aan, en bestanden van vorige versies openen gewoon.
- **Bètaversies** zie je alleen als je dat wil. Zet het aan bij **Instellingen → App → Versie en updates → Bètaversies aanbieden bij updates**. Draai je zelf een bètaversie, dan staat het standaard aan; zet je het uit, dan krijg je de volgende stabiele versie zodra die er is.
- **Deel je je bibliotheek met een tweede computer** (bijvoorbeeld via OneDrive)? Werk dan alle computers samen bij. Een pc die nog op een oudere versie draait, schrijft anders bestanden op de verkeerde plek naast de nieuwe indeling.

## Waar staat je werk

Standaard staat alles in `Documenten\RG Coaching`. Je oefeningen, tags, leerplannen en coachingswoorden staan daar gedeeld. Sinds 0.9 heeft elke ploeg een eigen map onder `ploegen\<ploeg>\`, met haar wedstrijdplannen, analyses, borden en affiches. Een ploeg die je verwijdert, gaat naar `ploegen\_prullenbak` en is dus niet weg.

De bestanden zijn gewone, leesbare tekstbestanden (JSON). Je kan ze dus altijd terugvinden en kopiëren.

Wil je de bibliotheek ergens anders? Dat kan bij **Instellingen → App → Bibliotheek → Kies map…**, bijvoorbeeld in een map die OneDrive, Google Drive of Dropbox synchroniseert, zodat je laptop en je pc uit dezelfde bibliotheek werken. Twee dingen om te weten:

- De app verplaatst niets uit zichzelf. Kopieer je bestaande bibliotheek eerst naar de nieuwe map; kies je een lege map, dan is je bibliotheek daar leeg.
- Werk je op twee computers tegelijk aan hetzelfde plan, dan zet de synchronisatie er een tweede bestand naast. Vervelend, maar je werk is niet weg.

Een reservekopie maak je door de map `RG Coaching` te kopiëren, zeker voor je een grote nieuwe versie installeert. Doe dat bij voorkeur ergens buiten OneDrive.

## Privacy

RG Coaching bewaart alles lokaal. Er is geen account, geen telemetrie en geen statistiek over hoe je de app gebruikt.

Het enige wat de app via het internet doet, is vragen of er een nieuwere versie is: een gewone, anonieme GET naar `https://api.github.com/repos/RareGoudvis/rg-coaching-releases/releases`. Daarbij verstuurt hij niets over jou: geen versienummer, geen gebruiker, geen gegevens.

**Waarom een aparte repo?** De broncode van de app staat in een privérepo. Een app kan de nieuwste versie alleen zonder aanmelding opvragen als de uitgaven publiek staan, dus staan de installers hier, in een aparte publieke repo zonder broncode.

## Wijzigingen

Per stabiele versie, de nieuwste bovenaan. De volledige notities per uitgave staan onder [Releases](https://github.com/RareGoudvis/rg-coaching-releases/releases).

### 0.10.0 — 5 oktober 2026

Het veld op één plek, nieuw gras en instelbare zones, en het bericht op elke affiche.

- **Nieuw:** alles over het veld staat onder één knop, **Veld** (de knoppen Weergave en Bijsnijden zijn weg), met rechts een voorbeeld en daaronder de uitsnede: het hele veld, een helft of een kwart.
- **Nieuw:** gras als Strepen, Ruiten, Effen of Zwart-wit voor de printer. Bij Strepen en Ruiten laat je de vakken uitlijnen op de lijnen van het veld (2, 3 of 6 m) of op het speelveld zelf (elke maat van 2 tot 12 m).
- **Nieuw:** zones: kanalen (flank, halfspace, centrale zone) en derden (opbouw, middenveld, afwerking) zet je apart aan of uit, met lijnen, kleur en labels. Versleep de lijnen als jouw zones anders liggen.
- **Nieuw:** het bericht op de affiche staat nu ook op een definitieve affiche, in alle vijf de formaten, en in de WhatsApp-tekst.
- **Rechtgezet:** de Wedstrijddag kaart, de Opstelling op het veld (bij een volle bank) en de Foto-achtergrond verloren onderaan tekst. Trainingen met een kwart veld of een 3v3/2v2-veld gingen niet meer open; dat lukt weer.

### 0.9.6 — 4 oktober 2026

- **Rechtgezet:** "vastzittende" spelers in de trainingseditor. Een vergrendelde vorm draagt nu altijd een klein hangslotje, de zweefbalk kan niet meer per ongeluk vergrendelen en toont bij een vergrendelde vorm enkel "Ontgrendelen". Kopieën zijn nooit vergrendeld.

### 0.9.5 — 4 oktober 2026

De eerste gewone uitgave na de bètareeks 0.9.0-beta.1 tot en met beta.6. Kom je van 0.8.x: maak eerst een kopie van `Documenten\RG Coaching` buiten OneDrive. De app zet je bestanden bij de eerste start om naar één map per ploeg, met een reservekopie in `_reservekopie-v08` en een verslag in `ploegen\MIGRATIE.txt`. Terug naar 0.8 kan door die reservekopie terug te zetten, maar borden die je in 0.9 bewaarde openen niet in 0.8.

- **Nieuw: meerdere ploegen**, elk met eigen logo, spelers, wedstrijdplannen, analyses, borden en affiches. Oefeningen, tags, leerplannen en coachingswoorden blijven gedeeld. Instellingen is opgedeeld in acht tabbladen, en per ploeg zie je de statistieken per speler (minuten, wedstrijden, doelpunten, assists, werkpunten), ook als pdf.
- **Nieuw: sets** voor tags, leerplan en coachingswoorden. Bewaar ze met een naam, wissel ertussen en koppel ze aan een ploeg.
- **Nieuw: de kalender** in de matchplanner. Importeer je foot24-kalender (`.ics`) of typ wedstrijden zelf, kies per wedstrijd wie thuisblijft (beurtrol) en laat "Stel voor" de volgende invullen. Van elke rij maak je een wedstrijdplan, en je kan de kalender als PNG of pdf exporteren.
- **Nieuw: vijf affiches**: Klassiek, Wedstrijddag kaart, Minimale lijst, Opstelling op het veld en Foto-achtergrond. Met het logo van de tegenstander (één per club, gedeeld door al je ploegen), soort wedstrijd, beurtrol, afwezigen, trainers en bericht. Een versleepte opstelling wordt per formatie onthouden. Shift-slepen zet dezelfde speler in een tweede blok.
- **Nieuw in Videoanalyse (bèta):** vreemde bestanden (HEVC van een iPhone, GoPro 10-bit, mkv, wmv) openen met uitleg en de knop "Zet om met RG Coaching", vloeiend scrubben, spotlights ook in exports en clips per speler.
- **Nieuw op het Bord:** clips uit een analyse als dia's, en ongedaan maken met Ctrl+Z en Ctrl+Y.
- **Algemeen:** één bovenbalk voor alle onderdelen met het tandwiel altijd bereikbaar, menu's worden niet meer afgeknipt, en een nieuw beeldmerk (een spelerstoken).

### 0.8.2 — 26 september 2026

- **Nieuw:** clipmodus. Open een moment als zijn eigen speler, met een tijdlijn van alleen die clip, een herhaalknop en vorige/volgende moment. Tekenen en spotlights zetten gaat daar op een schuif van enkele seconden.
- **Rechtgezet:** een komma typen in de keuzes van een tag lukte niet.

### 0.8.1 — 26 september 2026

- **Nieuw:** speler op een tweede scherm (beamer of tweede monitor), met bediening op je laptop.
- **Nieuw:** video komt als stroom binnen, de laatste stap naar vlot scrubben.
- **Nieuw:** spotlights gaan mee in geëxporteerde clips.
- **Rechtgezet:** een clip met een tekening erin was stil, en een tekening werd in een vierkant of staand kader geperst.

### 0.8.0 — 26 september 2026

- **Nieuw:** exporteren en de snelle kopie maken gebeuren op de achtergrond, met een voortgangsbalk en Annuleer onderaan.
- **Nieuw:** een tabblad Clips, en "Map per speler" zodat elke speler zijn clips in een eigen map krijgt.
- **Nieuw:** de snelle 720p-kopie maakt zichzelf bij het openen van een wedstrijd en ruimt zichzelf op (de vijf laatste wedstrijden blijven).
- **Rechtgezet:** Annuleren tijdens het exporteren stopt nu echt.

### 0.7.1 — 26 september 2026

- **Rechtgezet:** scrubben volgt je hand direct, en clips exporteren lukt weer (een GoPro-bestand gaf een foutmelding).
- **Nieuw:** kwaliteit van clips kiezen (Origineel, Hoog, Normaal, Klein), zoom op het beeld (Ctrl + scrollen, tot 4x) en "Snel scrubben".
- **Nieuw:** de uitleg kan je echt uitzetten, en de updatebalk verschijnt binnen het uur.

### 0.7.0 — 26 september 2026

- **Nieuw:** een portable versie naast de installer.
- **Nieuw:** spotlights die met de fase meelopen: een ovaal onder een speler of een rechthoek op een zone, met keyframes of live volgen.
- **Nieuw:** het knoppenpaneel pas je aan op de balk zelf: hoogte, grootte, aantal kolommen en knoppen bewerken ter plekke.
- **Rechtgezet:** scrubben in de tijdslijn verzette het beeld niet, en het menu op de videopagina hing buiten het venster.

### 0.6.4 — 14 september 2026

- **Rechtgezet:** in de 3-3-1 stonden links en rechts omgekeerd (bovenaan is de linkerflank), en de keeper heet overal GK. Plannen die je al bewaard hebt veranderen niet.
- **Nieuw:** je eigen namen voor de shirts blijven staan, per vorm.
- **Nieuw:** Speeltijd heeft een ploegweergave "Per positie" en **Exporteer pdf...**: een ploegblad en een blad per speler, met de minst gespeelden bovenaan, om aan ouders door te sturen.

### 0.6.3 — 6 september 2026

- **Nieuw:** je bibliotheek mag ergens anders staan (Instellingen → Ploeg → Bibliotheek), bijvoorbeeld in een gesynchroniseerde map.
- **Nieuw:** vindt de app je bibliotheek niet, dan zegt een rode balk welke map ze zoekt, in plaats van te doen alsof je seizoen weg is.
- **Rechtgezet:** trainingen met een platte schijf gingen niet meer open (aan de bestanden zelf was niets gebeurd). Eén onbekend voorwerp laat niet langer je hele training zakken.

### 0.6.1 — 6 september 2026

- **Nieuw:** een knop **Nieuw** om een nieuwe wedstrijd te beginnen.
- **Nieuw:** Speeltijd telt je hele seizoen op, per speler en per positie, met de minst gespeelde bovenaan.
- **Rechtgezet:** het kader van een gedraaid doel stond haaks op het doel. De platte schijf is vervangen door de vlakke markering; bestaande borden blijven zoals ze waren.

### 0.6.0 — 5 september 2026

- **Rechtgezet:** op de affiche van een uitwedstrijd stond je eigen ploeg als tegenstander. Je typt nu één naam: die van hen.
- **Nieuw:** beurtrol onderaan de affiche, trainers en veldtype kan je verbergen, en je eigen rijvolgorde geldt voor elk nieuw plan.
- **Nieuw:** de aandachtspunten staan ook als tabblad naast het blad.

### 0.5.3 — 21 augustus 2026

- **Rechtgezet:** de minuten van je keeper gingen er nog twee keer af als je zijn doelminuten zelf had ingetypt.
- **Nieuw:** de standaard 8v8 (3-3-1) heeft de juiste rugnummers, met letters die de cirkels volgen. Bestaande plannen veranderen niet.

### 0.5.2 — 14 augustus 2026

- **Rechtgezet:** de eerlijke speeltijd noemde een getal dat je niet kon halen. Nu zie je bijvoorbeeld "45m, 2 spelers 52,5m": wat rondgaat, met de rest erbij.
- **Nieuw:** zodra het blad vol is, zegt een regel wie achterloopt.
- **Rechtgezet:** de blokkenlijst is een dropdown en loopt niet meer over zichzelf.

### 0.5.1 — 14 augustus 2026

- **Nieuw:** elke speler heeft een kleur, zodat je hem over acht kolommen terugvindt.
- **Nieuw:** het rooster licht op waar een speler al staat (geel) en waar hij nog kan staan (groen), zodra je hem aanwijst of oppakt.
- **Nieuw:** ruimte tussen de periodes, en Overzicht staat vooraan.

### 0.5.0 — 14 augustus 2026

- **Rechtgezet:** slepen werkte niet in de bureaublad-app, het keuzemenu werd afgesneden, en je eigen cijfers telden niet mee in de eerlijke speeltijd.
- **Nieuw:** spelerskaartjes naast het rooster om te slepen, twee blokken op rij op de bank kleurt rood, en rijen zijn te slepen.
- **Nieuw:** bij een tornooi draagt elke kolom de naam van de tegenstander.
- **Nieuw:** drie exports: Per wedstrijd (opstelling en wissels), Schema (tabel) en Overzicht (speelminuten).

### 0.4.4 — 12 augustus 2026

- **Rechtgezet:** TORNOOI stond twee keer op de affiche.

### 0.4.3 — 11 augustus 2026

- **Nieuw:** pagina 2 van de tornooi-affiche herhaalt pagina 1 niet meer, zodat er meer wedstrijden op passen.
- **Nieuw:** een link naar het tornooi (bijvoorbeeld Tournify) komt in de WhatsApp-tekst en onderaan pagina 2.
- **Rechtgezet:** velden die buiten het paneel liepen, en een namenlijst die niet op de affiche paste.
- **Nieuw:** een gastspeler heeft geen rugnummer nodig, en positiecirkels in het wedstrijdplan hebben geen armpjes meer.

### 0.4.2 — 11 augustus 2026

- **Nieuw:** een speler voor één wedstrijd (gast), die van dat plan blijft.
- **Nieuw:** het programma van een tornooi op een tweede pagina van de affiche en in de WhatsApp-tekst.
- **Rechtgezet:** wie afwezig is, is niet meer te plannen en telt niet meer mee in ieders speelminuten.
- **Rechtgezet:** een definitieve affiche toont enkel wie bevestigd heeft, en de locatie en het bericht staan nu echt op de affiche.

### 0.4.1 — 6 augustus 2026

- **Nieuw:** opmaak in de omschrijving van een oefening: vet, opsommingen en genummerde lijsten.
- **Rechtgezet:** het Veld-venster, de jeugdveld-vinkjes, de spelersrijen in Instellingen en Enter in Coachingpunten en Variaties. De schuif voor de grootte van je spelers staat terug achter de knop Ploeg.
- **Eerste versie** die je te zien krijgt via het balkje bovenaan de app.

### 0.4.0 — 6 augustus 2026 (publieke bèta)

De eerste versie die je zelf kan komen halen. De app zegt het zelf wanneer er een nieuwere is.

- **Nieuw:** 8 tegen 8 ligt op lijnen die er al staan, en de maailijnen kloppen met de belijning.
- **Nieuw:** zones pak je bij de rand (acht grepen). Je exportinstellingen, bibliotheekfilters en de laatste maat van elk materiaal worden onthouden.
- **Nieuw:** de bibliotheek is een kaartenraster met filter op leeftijdsgroep en sorteren op datum.
- **Rechtgezet:** het selectiekader van doelen en de onderkant van het exportblad.

### 0.3.12 — 6 augustus 2026

De eerste uitgave die hier staat in plaats van in de privérepo. Hetzelfde bestand als voorheen; alleen de plek is veranderd.
