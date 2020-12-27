# Grupper - Hjälp
* Vad är rule_id **1930** och **1940** som används i exemplen på [följande](./../Grupper-Hur-gör-jag-för-att) sida?
  - Det är exempel på regler för en e-postlista. En lista kan bestå av en eller flera olika regler som tillsammans bygger upp en lista genom inkludering och exkludering av olika regler. **1930** och **1940** är t.ex regler för listan **1910**. Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> **API-nycklar och endpoints** --> **Endpoints för maillista [kårens namn]** kan du se alla id för listor och deras regler.

* Vi har satt upp en ny grupp men får det inte att synkronisera. E-postadressen är rödmarkerad
i google kalkylarket efter att skriptet körts. Vad är fel?
  - Den vanligaste orsaken är att e-postadressen för gruppen redan används. Om du har skapat
gruppen manuellt är det enklaste om du tar bort gruppen manuellt och sen kör skriptet igen.

* Vi har en funktionär som inte ska ingå i en arbetsgrupp (t.ex kårstyrelsen) men ändå ska stå
med på deras e-postlista. Hur lägger jag till personen manuellt till listan?
  - **Alt 1.** Du kan lägga till personen i kalkylarket manuellt. I cellen där list-id står för styrelsens e-postlista kan du lägga till ett kommatecken och sen skriva in e-postadressen
  till funktionären i samma cell.
  - **Alt 2.** Det går också att lägga till en ny regel till styrelselistan i Scoutnet och där
  ställa in en regel som matchar just denna funktionär. Det alternativet är dock inte något
  som rekommenderas då det gissningsvis är stor chans att ni kommer glömma bort att ta bort
  personen från listan någon gång i framtiden då man väldigt sällan går in och redigerar en
  specifik lista i Scoutnet. Om personen dock har en specifik roll, t.ex. revisor/anställd och
  att det är därför som ni tycker personen bör få alla styrelsebrev är tipset att skapa en ny
  lista i Scoutnet för detta, alternativ en ny regel för samma lista i Scoutnet. Detta då allt
  då blir kopplat till en specifik roll och inte en specifik person.

* Varför blir personer som jag satt att de bara ska kunna skicka till listan medlemmar i gruppen?
  - Samtliga personer som har någon definerad behörighet för en grupp läggs till i gruppen. T.ex bara att kunna skicka till listan. Om du för aktuell rad för gruppen i kalkylarket klickar på **Länk** skickas du till en sida där du får en överblick över samtliga som är tillagda till gruppen och vilka behörigheter de har.

* Kan jag sätta flera parametrar i kolumnen **Synkinställning**?
  - Ja det kan du. Det är bara att sätta dem efter varandra i samma cell och programmet gör ingen skillnad på vilken ordning du skriver dem.

* När jag är inne på sidan för Google-grupper efter att ha tryckt på **Länk** på aktuell rad för gruppen i kalkylarket, varför har olika personer olika roller?
  - Det är av tekniska skäl för att programmet ska fungera korrekt och har samband med vilken behörighet som är inställd för respektive person i kalkylarket.
    - Rollen **Medlem** - **Bara ta emot**
    - Rollen **Ansvarig** - **Bara skicka** eller **Skicka och ta emot**
    - Rollen **Ägare** - **Bara skicka**, **Skicka och ta emot**. Denna roll används för den e-postadressen som fylls i variabeln `moderateContentEmail`. Ingen vanligt roll alltså.