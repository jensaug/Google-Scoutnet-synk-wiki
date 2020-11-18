### Google användarkonton - synkronisering med Scoutnet
Synkroniserar personer som är med på e-postlistor från Scoutnet genom att man
anger id-nummret för e-postlistan i filen Konfiguration.gs i variabeln "userAccountConfig".
Det går bra att ange flera e-postlistor med kommatecken samt skriva kommentarer med
parenteser inom variabelnamnet. Se exemplen i filen.

Om inget id-nummer för en e-postlista anges så tolkar programmet det som alla
personer i kåren som har en avdelningsroll eller roll på kårnivå och skapar
användarkonton på kårens G Suite åt dem i den underorganisationen i G Suite som
man specificerar.

Om ett användarkonto vid nästkommande synkronisering ej matchar någon person
som synkroniseras så inaktiveras det specifika kontot.

Om personen senare matchas aktiveras kontot igen. Det är bara konton som finns
i organisationsstrukturen "Scoutnet" i G Suite som berörs vid en synkronisering.

Användarkonton skapas på formen fornamn.efternamn@domännamn.se

Om det finns personer som har samma namn (för- och efternamn) angivet i Scoutnet
kommer de som skapas som nr2 osv skapas på formen fornamn.efternamnX@domännamn.se
där X motsvarar en siffra från 1-5.

#### Inställningar för att komma igång (i Konfiguration.gs)
- Ändra kårens domän namn på variabeln "domain"
- Ändra kårens grupp-id som finns angivet i Scoutnet på sidan för Webbkoppling
- Ändra api-nyckeln som under Webbkoppling i Scoutnet står under
  "Get a detailed csv/xls/json list of all members"
- Om du gör detta för ett distrikt. Ändra variabeln "organisationType" från "group"
  till "district".

### Övrigt
- Avstängda konton, alltså de som inte längre matchar de som ska synroniseras flyttas till
  underorganisationen "/Scoutnet/Avstängda"