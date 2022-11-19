# Google grupper/e-postlistor - synkronisering med Scoutnet
I ett Google kalkylark kan du ställa in namn på google-grupper, dess e-postadress,
vilken e-postlista i Scoutnet de ska synkroniseras mot samt hur den ska synkronisera
i fältet Synkinställning.
Du kan i cellera för listid kommaseparera flera listor om du vill använda flera listor
från Scoutnet för att bygga upp en större egen. Det går också bra att skriva kommentarer
med parenteser.

Du kan där för synkinställning för respektive e-postlista ange följande
- `@` Lägg till personens Google-konto om den har något, annars hoppa över personen
- `-` Lägg endast till personens e-postadress som listad i Scoutnet
- `&` Lägg till både personens e-postadress som listad i Scoutnet samt Google-konto
  om den har något.

Det går också att ställa in i detta fält vilka e-postadressfält från scoutnet
som ska läggas till
- `m` Lägg till en medlems primära e-postadress.
- `f` Lägg till de e-postadresser som är angivet i fälten Anhörig 1,2.
  Alltså vanligtvis föräldrarna.
- `a` Lägg till en medlems alternativa e-postadress.
- `e` Lägg till primär e-postadress + kopior enligt medlemsprofil i Scoutnet.
- Om man inte anger något används fälten primär e-postadress, anhörig 1,
  anhörig 2 och alternativ e-postadress.

Det går att enkelt kontrollera vilka som är med i en google-grupp för att se att
man har gjort rätt genom att trycka på länken till höger om varje e-postadress i kalkylarket.

Du kan också lägga till e-postadresser manuellt till en grupp i kalkylarket om du vill.
I stället för att ange listid på något ställe så anger du en e-postadress eller flera med
komma emellan. Det går bra att både använda listid och e-postadress till samma lista.

## Inställningar för att komma igång (i Konfiguration.gs)
- Ändra kårens domännamn på variabeln `KONFIG_OBJECT.DOMAIN`.
- Ändra kårens **Kår-ID för webbtjänster** på variabeln `KONFIG_OBJECT.SCOUTNET_GROUP_ID`. Hittas i Scoutnet på sidan för
  Webbkoppling.
- Ändra api-nyckeln med namn `KONFIG_OBJECT.API_KEY_MAILINGLISTS` som hittas i Scoutnet under
  Webbkoppling under **Get a csv/xls/json list of members, based on mailing lists you have set up**.
- Ändra vart e-post som misstänkts för skräppost ska skickas genom att uppdatera variabeln
  `KONFIG_OBJECT.MODERATE_CONTENT_EMAIL`. Om inget anges skickas e-breven till den användare som kör detta program.
  Det går inte att ange en av kårens grupper som mottagare, men enskilda e-postadresser och
  Scoutnet-id går bra.
- Om du gör detta för ett distrikt. Ändra variabeln `KONFIG_OBJECT.ORGANISATION_TYPE` från `group` till `district`.
- Spara filen.
- Välj funktionen **skapaRubrikerGrupper** i **Start_funktioner.gs** och kör den.
- Fyll i övriga fält i filen Konfiguration.gs vid behov och möjligt.
- Klart.

## Enkelt och avancerat läge
Det går att ställa in om du vill visa samtliga kolumner i kalkylarket för olika
inställningar eller endast de grundläggande. Detta för att kunna hålla det enkelt.
I filen **Grupper.gs** finns funktionerna `visaEnkelLayoutGrupper()` och `avanceradLayout()` att använda för detta.
De visar och döljer egentligen bara olika kolumner i kalkylarket, så om man vill
kan man anropa `visaAvanceradLayoutGrupper()` för att visa alla kolumner och sen dölja de man inte önskar.

## Förtydliga hur man skickar e-brev till en e-postlista
Du kan ange en sidfot som läggs till i alla e-brev som skickas till listan.
- Bra till t.ex för en e-postlista för ledare eller utmanare så att alla vet hur de ska göra för att skicka e-brev till alla andra på listan. Detta kanske man glömmer bort att nämna för nya på listan och om man vill
slippa tänka på att komma ihåg att nämna det när det kommer någon ny så står det då i
alla e-brev som de får skickat till sig via e-postlistan.
- Kan också förtydliga vilken lista som brevet skickades till och vilka som var mottagarna.

## Begränsa åtkomst för att skicka och ta emot e-post
Om du vill kan du ställa in att enbart vissa personer ska kunna skicka till en lista,
att vissa personer ska både kunna skicka och ta emot eller att vissa enbart ska kunna
ta emot e-post.
Som standard om du fyller i **Scoutnet-id** och **Synkinställning** under **Kan skicka och ta emot** så är listan helt publik och vem som helst kan skicka till den. Du kan se detta
som det vanligaste alternativet.
Om du däremot önskar att bara specifika personer ska få skicka till listan så anger du
något Scoutnet-id i cellen under **Kan skicka**. Om du önskar att bara kårens e-postdresser
(de e-postkonton som finns i kårens Google Workspace) ska kunna skicka till en lista så skriver
du in ett `@` (snabela) i rutan **Scoutnet-id** under rukriken **Kan skicka**.

Om du vill kan du också specificera vilka som ska få skicka och ta emot för en lista genom
att ange list-ID under rubrikerna **Kan skicka** & **Kan ta emot**. Du behöver dock inte ange
under alla tre typerna om du inte vill. Du kanske vill att några ska kunna skicka och ta emot,
till en lista och några andra som bara ska få skicka.

**Observera att alla som på något sätt har en behörighet specificerad för sig för en lista läggs till i gruppen. Detta medför att de också kommer få behörighet till en delad enhet om gruppen ges behörighet för den oavsett om de t.ex. enbart får skicka till listan eller enbart ta emot från listan.**

# Exempel
Exempel på olika inställningar för uppsättning av grupper hittas [här](./Grupper-Hur-gör-jag-för-att).

# Hjälp
Hjälp på vanliga frågor hittas [här](./Hjälp-Grupper).
