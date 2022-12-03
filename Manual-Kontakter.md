# Google kontakter - synkronisering med Scoutnet
Med kontaktsynkronisering kan du ställa in vilka i kåren (antagligen funktionärer) som ska ha möjlighet att synkronisera kontakter från Scoutnet samt vilka personer som de ska kunna synkronisera. Kontakterna sparas i Google Kontakter i kontaktgrupper https://contacts.google.com/ så att du t.ex kan synkronisera en kontaktgrupp för en spåraravdelning och få en kontaktgrupp som består av alla de som är med i den. Synkronisering av kontaktgrupper kan användas som komplement till synkronisering av Google Grupper då e-brev med kontaktgrupper skickas direkt från avsändaren och risken för att ens brev hamnar bland skräpposten hos mottagare minimeras därmed.

Kontaktgruppsynkroniseringen består av 3 uppsättningar av skript
1. **Biblioteket** - Består av alla filer i mappen **Bibliotek** på https://github.com/Scouterna/Google-Scoutnet-synk. Erbjuds centralt men går att köra själv om du vill ha full koll på allting men är lite jobbigare att uppdatera vid behov.
1. **Kårens skript** - Består av det Google kalkylark med alla andra skript för kåren som du har satt upp. Består av alla .gs-filer som syns direkt på https://github.com/Scouterna/Google-Scoutnet-synk förutom **Kontakter-Anvandare.gs**.
Dessa skript anropar Biblioteket som på bilden benämns **ScoutnetSynkLib**.
<br/>![Bild över kårens skript](https://raw.githubusercontent.com/wiki/Scouterna/Google-Scoutnet-synk/Kårens-skript.PNG)
1. **Användarnas skrip** - Består av **Kontakter-Anvandare** som ligger i ett Google Kalkylark. Detta skript anropar **Kårens skript** med din e-postadress och ett lösenord som skickas till dig första gången du försöker köra skriptet. **Kårens skript** håller ordning på vilka medlemmar du ska få kontaktuppgifter för och vilka kontaktgrupper de ska finnas i.

## Inställningar för att komma igång (i Konfiguration.gs)

### Ska uppdateras om ej redan gjort
- Ändra kårens domännamn på variabeln `KONFIG_OBJECT.DOMAIN`.
- Ändra kårens **Kår-ID för webbtjänster** på variabeln `KONFIG_OBJECT.SCOUTNET_GROUP_ID`. Hittas i Scoutnet på sidan för
  Webbkoppling.
- Ändra apinyckeln för att hämta information om alla medlemmar i kåren på variabeln `KONFIG_OBJECT.API_KEY_LIST_ALL`. Den hittas i Scoutnet på sidan **Webbkoppling** vid texten **Get a detailed csv/xls/json list of all members**.
- Ändra api-nyckeln med namn `KONFIG_OBJECT.API_KEY_MAILINGLISTS` som hittas i Scoutnet under
  Webbkoppling under **Get a csv/xls/json list of members, based on mailing lists you have set up**.
- Om du gör detta för ett distrikt. Ändra variabeln `KONFIG_OBJECT.ORGANISATION_TYPE` från `group` till `district`.

### Ska uppdateras
- Ändra till kårens namn på variabeln `KONFIG_OBJECT.GROUP_NAME`.
- Mottagaradress på de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_TO`.

### Rekommenderas att uppdatera
- Avsändarnamn på de e-brev som skickar lösenord till kåranvändare för att de ska kunna synkronisera kontakter. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_CREDENTIALS_SENDER_NAME`. Om inget sätts används namnet på användarkontot som kör skriptet.
- E-postadress som anges som avsändare på de e-brev som skickar lösenord till kåranvändare för att de ska kunna synkronisera kontakter. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_CREDENTIALS_SENDER_FROM`. Om inget sätts används standardadressen på användarkontot som kör skriptet. Avsändaradressen måste finnas upplagd som alias i din Gmail.
- Avsändarnamn på de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_SENDER_NAME`.
- E-postadress som anges som avsändare på de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_SENDER_FROM`. Om inget sätts används standardadressen på användarkontot som kör skriptet.

### Kan ändras om du vill  
- Max antalet tvingade uppdateringar en kåranvändare tillåts göra innan det nollställs. Tvingade uppdateringar menas att det är direkt från Scoutnet och inte någon medlemsdata som kanske är några timmar gammal. Uppdateras med variabeln `KONFIG_OBJECT.MAX_NUMBER_OF_CONTACTS_FORCE_UPDATE`. Öka med försiktighet då det ökar belastningen mot Scoutnet.
- Om anhöriginfo ska läggas till kontakter som tillhör vuxna medlemmar ändras det med variabeln `KONFIG_OBJECT.STORE_CONTACTS_RELATIVES_FOR_ADULTS`. Standard är att det inte läggs till.
- E-postämne på de e-brev som skickar lösenord till kåranvändare för att de ska kunna synkronisera kontakter. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_CREDENTIALS_SUBJECT`.
- Brödtext i de e-brev som skickar lösenord till kåranvändare för att de ska kunna synkronisera kontakter för de som använder e-postklienter som inte kan läsa htmlformaterade e-brev. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_CREDENTIALS_PLAINBODY`.
- Brödtext i de e-brev som skickar lösenord till kåranvändare för att de ska kunna synkronisera kontakter för de som använder vanliga e-postklienter. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_CREDENTIALS_HTMLBODY`.
- E-postämne på de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_SUBJECT`.
- Brödtext i de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem för de som använder e-postklienter som inte kan läsa htmlformaterade e-brev. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_PLAINBODY`
- Brödtext i de e-brev som upplyser lämplig person i kåren om att det finns en inkomplett medlemsmatchning mellan en barnmedlem och en vuxen medlem för de som använder vanliga e-postklienter. Uppdateras med variabeln `KONFIG_OBJECT.CONTACT_GROUPS_EMAIL_PARTIAL_MEMBER_MATCH_HTMLBODY`.
- Nyckelord som hittas som anteckning i en medlemsprofil som ska bytas ut mot något annat. Det som ej skrivs här och som inte heller byts ut följer inte med vid kontaktsynkroniseringen. Den är okänslig för versaler och gemener. Uppdateras med variabeln `KONFIG_OBJECT.NOTE_KEYS_TO_REPLACE`.

## Ställa in synkronisering av kontaktgrupper
- Kalkylarket för kårens inställningar av synkronisering av Grupper och Medlemslistor innehåller också kalkylbladen **Kontakter** och **Kontakter-Användare**
    - **Kontakter** - Innehåller inställningar för vilka som ska få synkronisera kontakter och vilka kontakter de ska få synkronisera. I kolumnen **Medlem i Google grupp som ska ges behörighet** ställer du in vilka som ska ges behörighet att synkronisera de kontakter för de medlemmar som tillhör ett **Scoutnet-id**, som anges i kolumnen bredvid.
    - **Kontakter-Användare** - Innehåller de användare som ska få synkronisera några kontakter. Detta kalkylblad och alla användare uppdateras genom att köra funktionen **updateContactGroupsAuthnSheetUsers**.
      - I kolumnen **E-post** anges e-postadressen för de som ska få synkronisera användare.
      - I kolumnen **Lösenord** anges vilket lösenord användare behöver ange för att kunna synkronisera. Detta lösenord är slumpat fram och kan bytas av dig som har behörighet till kalkylarket vid behov men är inget som rekommenderas. Användare som anger ett felaktigt lösenord när de försöker synkronisera kontakter kommer få sitt lösenord skickat till sig automatiskt via e-post.
      - I kolumnen **Senast använd** syns senaste gången en användare har synkroniserat kontakter. Detta kan användas för att se vilka i kåren som synkronisera kontakter.
      - I kolumnen **Version som körs** syns vilken version som användare har angivit i sitt egna kalkylblad vilken version de kör. Denna version kan du hitta på helt själv hur den ska numreras och så. Syftet är att när du uppdaterar till en ny version av biblioteket och skapar en ny version av kårens skript som kårens användare ska anropa vill du kanske veta hur länge sedan de uppdaterade sina skript. Vid cellen **Äldsta godkända version** kan du ställa in vilken den äldsta godkända version som ska godkännas om du t.ex inte vill att någon kåranvändare använder en väldigt gammal version.
      - I kolumnen **Antal tvingade uppdateringar** syns eventuella tvingade uppdateringar som användare har kört sedan senaste gången funktionen **updateContactGroupsAuthnSheetUsers** har körts. Tvingade uppdateringar är när skriptet hämtar aktuell data från Scoutnet och inte någon om skulle kunna vara upp till några timmar gammal medlemsdata.