# Grupper - Hjälp
* Vår kår kör redan med Google Workspace. Vad händer om vi börjar använda programmet för synkronisering av grupper/e-postlistor?
  - Det går alldeles utmärkt. De grupper som tidigare är skapade manuellt hanteras ej av programmet och fortsätter fungera som tidigare.

* Var hittar jag **Scoutnet-id**?
  - Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> **API-nycklar och endpoints** --> **Endpoints för maillista [kårens namn]** kan du se alla id för listor och deras regler.

* Var hittar jag **groupId**?
  - Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> kan du se **Kår-ID för webbtjänster**, det är den.

* Vilka inställningar ska jag göra i Scoutnet när jag skapar en e-postlista där?
  - **Namn på e-postlistan** - Bra att ange så att du har koll.
  - **Visa listnamnet för mottagarna** - Lämna tom ruta.
  - **Beskrivning av e-postlistan** - Bra att ange något om att den används av Google Workspace så inte någon råkar radera den av misstag.
  - **Behörighetsnivå** - **Fördefinerad lista**.
  - **Typ av lista** - **Dynamisk lista**. Annars kommer den aldrig uppdateras!
  - **Öppen för inkommande e-post** - Lämna tom ruta.
  - **Epostmottagare** - **Primär e-post + kopior enligt medlemsprofil**

* Vad är rule_id **1930** och **1940** som används i exemplen på [följande](./Grupper-Hur-gör-jag-för-att) sida?
  - Det är exempel på regler för en e-postlista. En lista kan bestå av en eller flera olika regler som tillsammans bygger upp en lista genom inkludering och exkludering av olika regler. **1930** och **1940** är t.ex regler för listan **1910**. Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> **API-nycklar och endpoints** --> **Endpoints för maillista [kårens namn]** kan du se alla id för listor och deras regler.

* Vi har satt upp en ny grupp men får det inte att synkronisera. E-postadressen är rödmarkerad
i google kalkylarket efter att skriptet körts. Vad är fel?
  - Den vanligaste orsaken är att e-postadressen för gruppen redan används. Om du har skapat
gruppen manuellt är det enklaste om du tar bort gruppen manuellt och sen kör skriptet igen.

* Vi har en funktionär som inte ska ingå i en arbetsgrupp (t.ex kårstyrelsen) men ändå ska stå
med på deras e-postlista. Hur lägger jag till personen manuellt till listan?
  - **Alt 1.** Du kan lägga till en e-postadress manuellt i någon av kolumnerna **Scoutnet-id** i kalkylarket. Om du behöver lägga till flera lägger du ett kommatecken emellan varje e-postadress.
  - **Alt 2.** Det går också att lägga till en ny regel till styrelselistan i Scoutnet och där
  ställa in en regel som matchar just denna funktionär. Det alternativet är dock inte något
  som rekommenderas då det gissningsvis är stor chans att ni kommer glömma bort att ta bort
  personen från listan någon gång i framtiden då man väldigt sällan går in och redigerar en
  specifik lista i Scoutnet. Om personen dock har en specifik roll, t.ex. revisor/anställd och
  att det är därför som ni tycker personen bör få alla styrelsebrev är tipset att skapa en ny
  lista i Scoutnet för detta, alternativ en ny regel för samma lista i Scoutnet. Detta då allt
  då blir kopplat till en specifik roll och inte en specifik person. Detta alternativ fungerar
  endast för att lägga till medlemmar manuellt på listan och inte icke medlemmar.

* Varför blir personer som jag satt att de bara ska kunna skicka till listan medlemmar i gruppen?
  - Samtliga personer som har någon definerad behörighet för en grupp läggs till i gruppen. T.ex bara att kunna skicka till listan. Om du för aktuell rad för gruppen i kalkylarket klickar på **Länk** skickas du till en sida där du får en överblick över samtliga som är tillagda till gruppen och vilka behörigheter de har.

* Kan jag sätta flera parametrar i kolumnen **Synkinställning**?
  - Ja det kan du. Det är bara att sätta dem efter varandra i samma cell och programmet gör ingen skillnad på vilken ordning du skriver dem.

* När jag är inne på sidan för Google-grupper efter att ha tryckt på **Länk** på aktuell rad för gruppen i kalkylarket, varför har olika personer olika roller?
  - Det är av tekniska skäl för att programmet ska fungera korrekt och har samband med vilken behörighet som är inställd för respektive person i kalkylarket.
    - Rollen **Medlem** - **Bara ta emot**
    - Rollen **Ansvarig** - **Bara skicka** eller **Skicka och ta emot**
    - Rollen **Ägare** - **Bara skicka**, **Skicka och ta emot**. Denna roll används för den e-postadressen som fylls i variabeln `moderateContentEmail` i filen `Konfiguration.gs`. Ingen vanligt roll alltså.

* Varför läggs det till personer i grupppen med rollen **Ägare** fastän jag inte har lagt till dem i gruppen?
  - Det är av tekniska skäl och används för de som är tillagda som skräppostmoderator för en grupp. Du kan antingen specificera för varje grupp i kalkylarket vilken eller vilka e-postadresser det ska vara eller ange det i variabeln `moderateContentEmail` i filen `Konfiguration.gs` för det som ska gälla som standard. Om inget är angivet i `moderateContentEmail` heller används e-postadressen för den som kör skriptet.

* Jag vill gärna göra en inställning för en grupp som inte går att göra med programmet. Hur gör jag?
  - Om du för aktuell rad i kalkylarket klickar på **Länk** och där klickar på **Gruppinställningar** kan du göra dina inställningar. Testa köra programmet och se om de finns kvar efter att programmet har kört och om så kan du göra inställningen för fler grupper.
  - Om du tror att det är en inställning som kan uppskattas av flera får du gärna höra av dig så kanske vi kan lägga till det i programmet.

* Jag har gjort grupper där vissa personer inte ska få några e-brev men ska kunna skicka till listan, t.ex. att styrelsen kan skicka till listan. Varför får de en mötesbokning jag skickar till listan fastän de inte ska få några e-brev och hur löser jag det?
  - Detta har egentligen inget med detta program att göra utan har att göra med hur Google Grupper hanterar mötesbokningar. Enligt [följande](https://support.google.com/calendar/answer/172013?hl=en) är det så att om du som skickar mötesbokningen har behörighet att visa medlemmarna i gruppen kommer inbjudan att skickas ut till respektive medlem i gruppen oavsett hur inställningen för att ta emot e-brev via gruppen är. Om du däremot inte har behörighet att visa medlemmarna i gruppen skickas inbjudan till gruppen som till de vanliga.
  - Förslag till lösning är att skapa en renodlad grupp för de som ska få mötesbokningarna och som enbart innehåller de personer som är tänkt att få mötesbokningarna.
  Skapa sen en kalender att använda för denna specifika grupp, t.ex en kalender för spårarledarna och lägg till behörighet för deras grupp till denna kalender.

* När jag skapar en e-postlista i Scoutnet finns det flera alternativ för **E-postmottagare** att välja på för vilka fält som ska användas för mottagare. Vad ska jag välja?
  - Välj alla fält tillgängliga och sköt dessa inställningar via detta program i stället.

* Går det att börja synkronisera en grupp som tidigare är skapad manuellt?
  - Ja, det går men rekommenderas inte med anledning av risken att göra fel och råka radera gruppen och dess logg över tidigare e-brev skickade till den.
  - **Alt 1.** Mest säkra lösningen. Byt namn och e-postadress på den gamla gruppen så att den finns kvar för att sen kunna skapa sen en ny med programmet. Observera att när du byter namn på en grupp läggs det gamla namnet till som ett e-postalias till den gruppen, så du måste ta bort det för att kunna skapa en ny grupp med den e-postadressen. Du har nu kvar e-postloggen via den gamla gruppen och kan kanske ta bort den efter något år eller när det ej längre är aktuellt.
  - **Alt 2.** Den faran som finns med detta alternativ är att gruppen råkar raderas och skapas på nytt då programmet gör så av tekniska skäl om t.ex e-postadressen ändras.
    1. Öppna upp kalkylarket och ta fram den gömda kolumnen **J**.
       - Denna kolumn/cell innehåller id-numret hos Google för en specifik googlegrupp och används för att identifiera vilken grupp som är på respektive rad i kalkylarket då det ju kan hända att man byter e-postadress på en grupp; men id-numret är ändå sig likt.
    1. Du tar sedan och klistrar in id-numret för den grupp du ska konfigurera.
        - Du hittar id-numret genom att gå in på **admin.google.com** --> **Enheter** --> **Grupper** och där välja en grupp och så ser du id-numret i url:en. Om du gör detta för en grupp som du redan skapat med hjälp av programmet och kalkylarket kan du kontrollera att det blir rätt nummer.
        - Du kan också få fram en lista över id-nummer för samtliga grupper genom att köra funktionen `TestListAllGroups` i filen `Grupper.gs`.
    1. Du tar sedan och klistrar in detta id-nummer i kolumn **J** på den tomma raden och **samma namn** och **samma e-postadress** som gruppen har sedan innan i kolumn **A** & **B**.
