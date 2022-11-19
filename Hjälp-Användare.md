# Användare - Hjälp
* Vår kår använder redan Google Workspace. Vad händer om vi börjar använda programmet för synkronisering av användarkonton?
  - Det går alldeles utmärkt. De användare som tidigare är skapade manuellt hanteras ej av programmet och fortsätter fungera som tidigare. Det som dock kommer ske är att det kommer skapas en hel del onödiga användarkonton på formen **fornamn.efternamn1@domännamn.se**.
  Detta då programmet bara rör de användarkonton som ligger under organisationsenheten **Scoutnet**. Då det för vissa redan finns användarkonton på formen **fornamn.efternamn@domännamn.se** på andra ställen kommer det skapas nya på formen **fornamn.efternamn1@domännamn.se**. Programmet kommer aldrig radera konton.

* Var hittar jag **ScoutnetListId**?
  - Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> **API-nycklar och endpoints** --> **Endpoints för maillista [kårens namn]** kan du se alla id för listor och deras regler.

* Var hittar jag **groupId**?
  - Om du går in på kårens sida i Scoutnet under **Webbkoppling** --> kan du se **Kår-ID för webbtjänster**, det är den.

* Vi har sedan tidigare använt Google Workspace inom kåren. Hur gör vi för att börja synkronisera med Scoutnet?
  1. Börja med att följa den vanliga instruktionen för att börja synkronisera användare. Du kan börja med att enbart synkronisera några få användare med Scoutnet för att testa om du vill.
  1. För de användare du vill synkronisera gör du följande:
     1. För respektive användare lägg in deras medlemsnummer under rubriken **Anställnings-id**. Den plats att lägga in numret hittas under **Användarinformation** på medlemsprofilen i Google Workspace.
     1. Se till att alla användare har sin e-postadress angiven på formen **fornamn.efternamn@domännamn.se** och inte enbart deras förnamn. Du kan ändra detta för ett konto under **Byt namn på användare** och den gamla e-postadressen kommer då läggas till som ett alias och fortsätta fungera också.
     1. Flytta över de användare du vill ska synkroniseras så att de hamnar under organisationsenheten **Scoutnet**.
  1. Kör programmet
  1. Om något går fel
     - Användaren flyttas till organisationsenheten **Scoutnet/Avstängda**.
        - Detta pga av att medlemsnummer saknas eller är felaktigt eller inte längre matchar något från listan från Scoutnet.
     - Det skapas användare på formen **fornamn.efternamn1@domännamn.se**.
        - Detta pga av att användarkontot ligger antagligen inte under organisationsenheten **Scoutnet** eller så är medlemsnumret felangivet. Rätta detta och ta sen bort **fornamn.efternamn1@domännamn.se** om den ska bort.   

* Vi har en ledare/medlem som skriptet alltid stänger av efter varje synkronisering. Varför?
  - **Alt 1.** Personen är inte längre med i listan i Scoutnet varifrån allt hämtas då personen inte matchar uppsatta regler eller inte längre är medlem i kåren. 
  Du kan se om hon är med i listan i Scoutnet genom att kolla i Scoutnet under **Kårsidan-->E-postlistor** och sen för aktuell e-postlista **Alternativ->Visa lista över mottagare** (om du har tillräcklig behörighet)
  - **Alt 2.** Om det inte tidigare heller har gått att få användarens konto på rätt plats i organisationsstrukturen är det gissningsvis så att ni tidigare har använt Google Workspace i kåren och gjort något fel med just denna medlems konto för att få synkroniseringen att fungera. T.ex. att
  personen ligger under fel organisationsenhet (**Scoutnet**) eller att medlemsnummer inte är infört på rätt plats.
