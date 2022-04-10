# Inställningar
1. Logga in till [Adminkonsolen](https://admin.google.com/) med ditt adminkonto.
1. Under **Säkerhet/Åtkomst- och datainställningar/API-kontroller** tryck på kryssrutan för att **Lita på interna appar som ägs av domänen**. [Direktlänk](https://admin.google.com/ac/owl)
1. I **Adminkonsolen** under **Organisationsenheter** skapar du en underorganisation till
   kåren som heter **Scoutnet**. Läs hur [här](https://support.google.com/a/answer/182537?hl=sv)
1. I **Adminkonsolen** ställer du in under **Appar/Google Workspace** vilka tjänster som ska
   vara tillgängliga för olika organisationsenheter. Om du trycker på **Scoutnet** i
   organisationsstrukturen till vänster kan du sätta på/stänga av de tjänster som ska vara
   tillgängliga för just de användare som ska synkroniseras. Tänk på att det är lättare att ha
   mycket avstängt och sen sätta på tjänster vid behov än tvärt om.
   - Om du går in på [Kataloginställningar](https://admin.google.com/ac/appsettings/986128716205)
   kan du ställa in om användare ska få anpassa sina namn mm.
   Det går också att aktivera kontaktdelning inom kåren vilket kan underlätta kommunikationen internt.
   - Det går också att sätta på och stänga av inställningar under
   **Appar/Ytterligare tjänster från Google**.
   Om ni har stängt av det tidigare behöver **Google Cloud Platform** aktiveras för den användare som
   ska köra dessa program.
1. Besök [följande mall](https://docs.google.com/spreadsheets/d/1JEm7uBhAXE4InmzTsjIqR6dUOsk_uonFppE2hwSu2Ho/edit#gid=0) inloggad med ditt adminkonto.
1. Skapa en egen kopia av kalkylarket genom att trycka på **Arkiv-->Kopiera** och placera den på lämpligt ställe.
1. Du hittar konfigurationsfilen `Konfiguration.gs` i menyn i kalkylarket under **Tillägg-->Apps Script**.  
1.  Gör inställningar enligt följande för respektive skript för att sätta upp dem.
   [Användare](Manual-Användare#inställningar-för-att-komma-igång-i-konfigurationgs), 
   [Grupper](Manual-Grupper#inställningar-för-att-komma-igång-i-konfigurationgs), [Medlemslistor](Manual-Medlemslistor#inställningar-för-att-komma-igång-i-konfigurationgs)
1.  Kör programmen genom att öppna filen **Start_funktioner.gs** och kör önskad funktion för att se att de olika skripten fungerar som de ska.
Du kan också göra inställningar att t.ex enbart vissa rader grupper eller medlemslistor synkroniseras vid olika tillfällen.
För standardfunktioner kör du dom enklast via kalkylarket under övre menyn under
**Scoutnet**.
1.  Du kan nu tidinställa hur ofta som programmen ska köra/synkronisera genom att trycka på
    klocksymbolen i menyn till vänster i kodläget och ställa in synkroniseringar för olika funktioner och skript.    
    - Tänk på att inte köra synkroniseringen för ofta då det finns maxbegränsningar hos Google per
   dag för olika operationer. Det rekommenderas också att ställa in enskilda synkroniseringar för
   de olika skripten då de annars kan ta för lång tid på sig och då kanske inte lyckas synkronisera klart.
   Det bör räcka med att synkronisera användare en gång per dygn och samma för grupper och
   medlemslistor; förslagsvis under natten.
    
    - Om körningen för grupper trots allt tar för lång tid finns i **Start_funktioner.gs**
   funktionerna `GrupperVissaRader1` osv. som du kan ställa in att enbart vissa rader i
   kalkylarket ska synkroniseras.
    
    - Det finns också funktioner i **Start_funktioner.gs** för att enbart synkronisera vissa
   medlemslistor, enbart skicka e-brev mm om man vill dela upp saker.
1. För att komma ihåg vilken version av programmet du har kan du t.ex anteckna det i filen
`Konfiguration.gs` på något sätt eller namnge kalkylarket efter det.
