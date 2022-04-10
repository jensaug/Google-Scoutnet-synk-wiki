# Medlemslistor - Hjälp
* Villkor - Hur fungerar dessa mer praktiskt?
  - I kalkylarket som används för synkronisering av t.ex Grupper, Medlemslistor, Kontakter har du på kalkylbladet **Medlemslistor** angivet en länk till ett annat kalkylark under rubriken **Länk till kalkylark**. I det kalkylarket finns det många kolumnrubriker angivna som t.ex. **Förnamn**, **Efternamn**, **Avdelning**, **Primär e-postadress**.
  Du kan använda alla dessa olika rubriker som villkor men enklast är de som enbart är siffror för att använda jämförelseoperatorer alternativt för att jämföra med ett exakt värde som t.ex enbart ett visst postnummer.
  Du anger dubbla måsvingar ```{{``` före rubriken och dubbla måsvingar ```}}``` efter. Dessa rubriker kommer vid körning ersättas av variabler för respektive person med den datan som finns på deras medlemsprofil.
  Ett exempel att skriva kan vara ```{{Ålder}}>5 && {{Dagar till nästa födelsedag}}>5``` för att då sätta som krav att enbart de som just nu finns i medlemslistan så ska enbart e-brev skickas till de personer som både är över 5 år och har fler än 5 dagar till sin nästa födelsedag. När detta körs kan villkoret för en person t.ex jämföras på detta sätt **10>5 && 45>5** För en person som är 10 år och har 45 dagar till sin nästa födelsedag och som också logiskt uppfyller hela villkoret.

* Hur får jag fram ID för ett dokument för dokumentkopplingen
  - Om url:en t.ex för ett dokument skulle vara **https://docs.google.com/document/d/1Ki4R9458123456789/edit** skulle dokument-id vara **1Ki4R9458123456789**

* Kan jag skicka ett personligt e-brev till en person som senaste dygnet fått ett aktivt Google-konto?
  - Inte vad jag kommer på. Det finns dock en kolumn **Antal dagar som medlem i kåren** för en medlemslista som kan användas för nya medlemmar i kåren.
  Ett alternativ på vägen skulle kanske vara att sätta ett vilkor ```{{Ålder}}>25 && {{Antal dagar som medlem i kåren}}==5``` vilket då bör matcha alla nya ledare som kommer direkt in i kåren och som inte råkats registreras av misstag som ledare. De man missar då är ju t.ex utmanare, rovers mm som kommer in som ledare i kåren. Ett komplement kanske skulle vara att skicka ett separat utskick till alla ledare under X år som är registrerad med en ledarroll på en avdelning och skicka dem ett mejl en gång per år eller så med samma info.