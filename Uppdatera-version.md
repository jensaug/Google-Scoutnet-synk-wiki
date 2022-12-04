# Ny version - Hur du gör för att uppgradera
- Uppdatering av programmet sker genom att besöka https://github.com/Scouterna/Google-Scoutnet-synk/releases/latest och läsa vad och hur du behöver uppdatera.
- För det mesta behöver du inte uppdatera så mycket bland dina filer utan det räcker med att välja att du ska använda senaste versionen av biblioteket och skapa en ny version av kårens skript som kårens användare anropar.
  - Tryck på **ScoutnetSynkLib** och välj vilken version av biblioteket du vill använda vilket antagligen är den senaste och som har högst nummer.
  <br/>![Bild över kårens skript](https://raw.githubusercontent.com/wiki/Scouterna/Google-Scoutnet-synk/Kårens-skript.PNG)
  - För att kåranvändare ska kunna använda den uppdaterade koden måste du "bygga" en ny version av den kårens skript. Detta görs genom att trycka på den blå knappen **Implementera** uppe i högra hörnet och välj **Hantera implementeringar** och sedan trycka på pennknappen/redigera i övre högra hörnet på det fönster som öppnades och sen under **Version** välja **Ny version** och sen tryck på **Implementera**.
- Uppdatera äldsta tillåtna version att använda för kåranvändare som synkroniserar kontakter. Detta är främst om det har skett kodförändringar i filen **Kontaker-Anvandare.gs** för att se till att kårens användare kör aktuell version. För att slippa be kårens användare uppdatera sina skript vid behov är det enklaste antagligen att de slänger sitt kalkylark som används för att synkronisera kontakter och att du skickar ut en ny version av deras kalkylarksmall till kårens funktionärer där koden är uppdaterad och med uppdaterad version.
- Kör de olika programmen manuellt en gång innan du kör med tidsinställning då det kan ha
  tillkommit någon ny funktionalitet som kräver ditt tillstånd.
- Du kan hålla dig uppdaterad med nya versioner genom att om du är inloggad på Github trycka
  på knappen **Watch** uppe till höger på sidan för att då kunna bli notifierad vid ny version.