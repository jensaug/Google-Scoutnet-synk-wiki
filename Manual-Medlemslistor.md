# Medlemslistor och utskick - synkronisering med Scoutnet
Programmet kan användas för följande:
1. Synkronisera e-postlistor från Scoutnet till ett Google kalkylark.
2. Skicka e-brev till de listade i en medlemslista i ett Google kalkylark.

- Det går att göra att synkronisering och utskick görs vid samma tillfälle vilket bör vara normalfallet.
- Det går att ställa in att synkroniseringen och e-breven skickas ut vid de tidsintervall du själv bestämmer och det går att ha olika intervall för olika medlemslistor.
- Det går att ställa in ytterligare villkor så att endast de i aktuell medlemslista som uppfyller de specifika villkoren ska få e-brev.
- Det går att skicka personliga e-brev inklusive bilagor där vissa kortkoder ersätts med personlig information.
- Du kan själv ställa in vilka avsändaradresser och mottagaradresser som ska användas.


## Inställningar för att komma igång (i Konfiguration.gs)
- Ändra kårens domännamn på variabeln `domain`.
- Ändra kårens **Kår-ID för webbtjänster** på variabeln `groupId`. Hittas i Scoutnet på sidan för
  Webbkoppling.
- Ändra api-nyckeln med namn `api_key_mailinglists` som hittas i Scoutnet under
  Webbkoppling under **Get a csv/xls/json list of members, based on mailing lists you have set up**.
- Skapa ett Google Kalkylark och klistra in webbadressen vid variabeln `spreadsheetUrl_Medlemslistor`.
- Spara filen.
- Välj funktionen **skapaRubrikerMedlemslistor** i **Start_funktioner.gs** och kör den.
- Klart.

## Uppsättning av en medlemslista och utskick via e-brev
1. Skapa en e-postlista i Scoutnet för aktuell medlemslista du vill använda om du inte har en sedan innan.
2. Skapa ett utkast i Gmail för det e-brev som ska användas för ett utskick. Du kan lägga till bilagor samt använda **kortkoder** i utkastet för ämnesraden och i brödtexten som senare ska ersättas med personlig information för varje medlem.
3. Skapa ett tomt Google kalkylark. Detta ska sedan användas för att spara medlemslistan i.
4. I det kalkylarket du angivet för variabeln `spreadsheetUrl_Medlemslistor` anger du de värden för hur medlemslistorna ska synkroniseras och vilken avsändar- och mottagarinformation som ska användas.
De förklaras närmare nedan.


### Vad kolumnerna betyder för olika inställningar
Observera att du inte behöver ange data i samtliga kolumner.
1. **Namn** - Något namn så att du kommer ihåg vad denna medlemslista berör.
1. **Scoutnet-id** - Id för en e-postlista skapad i Scoutnet. Går att ange flera med kommatecken som separerar.
2. **Länk till kalkylark** - Länk till ett egenskapat tomt Google kalkylark. I det angivna kalkylarket kommer medlemslistan för de som hämtas från e-postlistan från Scoutnet skrivas med alla tillgängliga attribut.
3. **Ämnesrad på utkastet i Gmail** - Ämnesraden för ett utkast du skapat i Gmail och som används som mall för e-breven.
4. **Villkor** - Villkor för ytterligare filtrering av vilka i medlemslistan som det ska skickas e-brev till. Filtering anges med hjälp av kortkoder.
   - T.ex `{{Ålder}}<18 && {{Dagar till nästa födelsedag}}==30`
5. **Koppla dokument** - Id för ett Google dokument med text och kortkoder som ska personligfieras och bifogas e-brevet till respektive person i medlemslistan. Dokumentet kommer skickas i formatet PDF.
6. **Avsändare**
   1. **Avsändare namn** - Namnet som ska stå som avsändare på e-breven. Om inget anges blir det standardnamnet för ditt konto.
   2. **Avsändare e-post** - Adressen som står som avsändare på e-breven. Om inget anges blir det standardadressen för ditt konto. De adresser som kan anges är de som i Gmail under **Inställningar-->Konton** är listade som alias.
   3. **Svarsadress e-post** - Adressen som står som adressen dit svar på e-breven ska skickas. Om inget anges blir det samma som för avsändaradressen.
   4. **Svara-ej** - Om sätts till `TRUE` kommer e-breven skickas från en generisk e-postadress för att avråda personer att svara på e-breven.
7. **Mottagare**
   1. **Mottagare e-post** - E-postadresserna dit e-breven ska skickas. Normalt anges t.ex `{{Primär e-postadress}}` för att skickas till medlemmarnas primära e-postadresser. Det går att kommaseparera flera medlemsattribut för e-postadresser. För test anges förslagsvis din egen e-postadress utan att använda någon kortkod.
   1. **Kopia e-post** - E-postadresserna dit e-brev ska skickas som kopia.
   1. **Blindkopia e-post** - E-postadresserna dit e-brev ska skickas utan att mottagarna ser vilka övriga mottagare är.

### Vad är kortkoder?
- Du kan i utkastet använda de medlemsattribut som är rubriker i ett Google kalkylark för en medlemslista för att skapa personliga e-brev. Ange `{{` före namnet på attributet och `}}` efter så att programmet vet att det är något den ska ersätta. T.ex kan det stå `Hej {{Förnamn}},` för att då skriva ut t.ex **Hej Ebbe,** för medlemmen Ebbe.
- Du kan också skapa egna medlemsattribut med hjälp av olika funktioner som går att använda som kortkoder. De anges i filen **Start_funktioner.gs** i variabeln `medlemslista_egna_attribut_funktioner` och kommer läggas in i samtliga medlemslistor automatiskt vid nästa körning.


## Exempel på användningsområden
- Skicka e-brev till nya medlemmar efter X dagar med välkomstinformation.
- Skicka e-brev till nya ledare efter X dagar med kårhandbok, info om Trygga Möten, registerutdrag mm.
- Skicka e-brev till de som behöver gå Trygga Möten, lämna registerutdrag.
- Skicka e-brev till föräldrar till de Äventyrare/Utmanare som inte har någon egen e-postadress angiven i Scoutnet om att lägga in det.
- Skicka e-brev varje termin/år till medlemmar om att kontrollera deras uppgifter i Scoutnet.
- Skicka e-brev under sommaren för de som gått sista året på avdelningen gällande mötestider för den nya avdelningen efter sommaren.
- Skicka e-brev varje termin/år till medlemmar om de medlemsförmåner som ges via kåren. T.ex rabatt i någon affär, hyra kårens båtar.
- Skicka e-brev varje termin/år till medlemmar om hur föräldrar kan engagera sig för att hjälpa till i kåren.
- Skicka e-brev till medlemmar under X år Y dagar innan deras födelsedag om att det går bra att boka scoutlokalen för kalas.
- Skicka e-brev varje år till de som har flera personer i samma hushåll som är medlemmar och som får medlemstidning om att de bör se över om alla verkligen behöver få en egen medlemstidning.

# Exempel
Exempel på olika inställningar för uppsättning av medlemslistor hittas [här](./Medlemslistor-Hur-gör-jag-för-att).

# Hjälp
Hjälp på vanliga frågor hittas [här](./Hjälp-Medlemslistor).
