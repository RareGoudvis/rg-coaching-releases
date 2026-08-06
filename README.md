# RG Coaching — downloads

De installatiebestanden van **RG Coaching**. Meer staat hier niet: geen broncode, geen issues, geen
geschiedenis. Alleen de setup die je nodig hebt om het programma te installeren of bij te werken.

## Installeren

1. Ga naar [de laatste versie](https://github.com/RareGoudvis/rg-coaching-releases/releases/latest).
2. Download `RG.Coaching_<versie>_x64-setup.exe`.
3. Dubbelklik. Windows waarschuwt dat de maker onbekend is — *Meer info* → *Toch uitvoeren*. Het
   bestand is niet ondertekend met een certificaat, en dat is het enige wat die melding zegt.

Je trainingen, wedstrijdplannen en analyses staan in `Documenten\RG Coaching`. Een nieuwe versie
installeren raakt die map niet aan.

---

## Waarom deze repo bestaat

De app kijkt zelf of er een nieuwere versie is en zet dan een balkje bovenaan het scherm. Dat balkje
vraagt het aan deze repo, met een gewone onbeveiligde GitHub-API-call:

```
GET https://api.github.com/repos/RareGoudvis/rg-coaching-releases/releases
```

De broncode staat in een **privérepo**, en die kan zo'n call niet zien. Een token in een programma
stoppen dat je uitdeelt is een token weggeven, dus dat gebeurt niet. Vandaar deze tweede repo: hij is
publiek, hij bevat niets vertrouwelijks, en hij houdt precies één ding bij — welke versie de laatste
is en waar je hem haalt.

Er wordt niets verstuurd. Geen versienummer, geen gebruiker, geen telemetrie. De app *stelt* een
vraag die iedereen ook in een browser kan stellen.

## Een nieuwe versie uitbrengen

De installer wordt met de hand gebouwd op Windows — er is geen release-workflow en geen
handtekeningcertificaat.

1. Zet het nieuwe versienummer in `package.json` **en** in `src-tauri/tauri.conf.json`. Die twee
   moeten gelijk zijn: de app leest de eerste, de installer de tweede.
2. `npm run app:build`
3. De setup staat in `src-tauri/target/release/bundle/nsis/`.
4. Publiceer hem **hier**, niet in de privérepo:

   ```
   gh release create v<versie> \
     --repo RareGoudvis/rg-coaching-releases \
     --title "RG Coaching <versie>" \
     --notes "..." \
     "src-tauri/target/release/bundle/nsis/RG.Coaching_<versie>_x64-setup.exe"
   ```

De tag mag `v0.3.13` of `0.3.13` heten, en de release mag als pre-release gemarkeerd staan: de app
leest de hele lijst en kiest zelf het hoogste nummer. Wat hij **niet** meetelt is een concept
(draft) — daar valt niets te downloaden.
