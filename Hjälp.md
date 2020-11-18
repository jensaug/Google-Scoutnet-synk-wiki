## Hjälp
1. Om problem uppstått när du kört programmet tidsinställt, testa då att köra
   programmet manuellt en gång och se om felet uppstår då också. När man kör programmet
   manuellt kan det dyka upp rutor för att godkänna vissa saker som inte syns när man
   kör programmet tidsinställt.
1. Om du fått något felmeddelande; titta bland de nedan som förklarar de felen som hittills
   har frågats om bland andra kårer.
1. Kolla i loggfilen genom att trycka Ctrl+Enter så kanske du lyckas se vad problemet är
1. Det kan hända att det finns en bugg i den versionen av programmet som du kör vilket
   givet vissa specifika omständigheter yttrar sig för just dig. Se till att du har den
   senaste versionen av programmet.
1. Lägg ett ärende under "Issues" eller mejla emil.ohman@scouterna.se

### Hur gör jag för att...?
Nedan finns en del exempel med olika Scoutnet-id och e-postadresser på hur du gör för att
ställa in programmen så som du vill.
Om du saknar något exempel eller behöver hjälp är det bara att mejla emil.ohman@scouterna.se

#### Användare - inställningar exempel
*  Hur gör jag om jag bara vill synkronisera användare?
   - Du kör funktionen "Anvandare" i filen "Anvandare.gs"

#### Grupper - inställningar exempel
* Hur gör jag om jag bara vill synkronisera grupper / e-postlistor?
   - Du kör funktionen "Grupper" i filen "Grupper.gs"
   
*  Jag vill ha följande e-postlista
   * Bara de med en e-postadress från kåren ska kunna skicka till listan.
   * En grupp/avdelning/scoutföräldrar ska bara kunna ta emot från listan, EJ skicka. Vi vill
   skicka till alla e-postadresser som är registrerad på någon medlem på avdelningen.
      
   Gör följande inställningar i kalkylarket

   <table>
      <thead>
         <tr>
            <th colspan=2>Kan skicka och ta emot</th>
            <th colspan=2>Kan skicka</th>
            <th colspan=2>Kan ta emot</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
         </tr>
         <tr>
            <td></td>
            <td></td>
            <td>@ (kårens googlekonton)</td>
            <td></td>
            <td>1910 (id för avdelningen)</td>
            <td></td>
         </tr>
      </tbody>
   </table>
   
*  Jag vill ha följande e-postlista
   * Bara de som är med på listan samt de med en e-postadress från kåren ska kunna skicka till listan.
   * För de som är med på listan ska e-breven bara skickas till en medlems primära e-postadress i Scoutnet.
      
   Gör följande inställningar i kalkylarket

   <table>
      <thead>
         <tr>
            <th colspan=2>Kan skicka och ta emot</th>
            <th colspan=2>Kan skicka</th>
            <th colspan=2>Kan ta emot</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
         </tr>
         <tr>
            <td>1910 (id för avdelningen)</td>
            <td>-m</td>
            <td>@ (kårens googlekonton)</td>
            <td></td>
            <td></td>
            <td></td>
         </tr>
      </tbody>
   </table>
   
*  Jag vill ha följande e-postlista
   * Bara de som är med på listan samt de med en e-postadress från kåren ska kunna skicka till listan.
   * För de som är med på listan ska e-breven skickas till en medlems primära e-postadress i Scoutnet
   samt deras e-postkonto hos kåren.
      
   Gör följande inställningar i kalkylarket

   <table>
      <thead>
         <tr>
            <th colspan=2>Kan skicka och ta emot</th>
            <th colspan=2>Kan skicka</th>
            <th colspan=2>Kan ta emot</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
         </tr>
         <tr>
            <td>1910 (id för avdelningen)</td>
            <td>&m</td>
            <td>@ (kårens googlekonton)</td>
            <td></td>
            <td></td>
            <td></td>
         </tr>
      </tbody>
   </table>
   
*  Jag vill ha följande e-postlista
   * Vem som helst ska kunna skicka till listan.
   * Alla scouter på avdelningen ska ta emot alla e-brev från listan, men listan ska endast skicka till föräldrarnas e-postadresser för scouterna.
   * Alla ledare på avdelningen ska ta emot alla e-brev från listan, men listan ska endast skicka till deras e-postkonto hos kåren och inte till någon privat e-postadress.
      
   Gör följande inställningar i kalkylarket
   I exemplet är det minavdelning@hasselbyscout.se som ska användas som följande e-postlista.

   <table>
      <thead>
         <tr>
            <th colspan=1></th>
            <th colspan=2>Kan skicka och ta emot</th>
            <th colspan=2>Kan skicka</th>
            <th colspan=2>Kan ta emot</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <td>E-post</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
         </tr>
         <tr>
            <td>ledareavdelning@hasselbyscout.se</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>1910&rule_id=1930 (id för avdelningen och regel för ledarna)</td>
            <td>@</td>
         </tr>
         <tr>
            <td>minavdelning@hasselbyscout.se</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>1910&rule_id=1940 (id för avdelningen och regel för scouter på avdelningen), ledareavdelning@hasselbyscout.se</td>
            <td>-f</td>
         </tr>
      </tbody>
   </table>
   
 * Jag vill ha följande e-postlista
   * Vem som helst ska kunna skicka till listan.
   * Jag vill manuellt lägga till vilka e-postadresser som ska vara med.
      
   Gör följande inställningar i kalkylarket

   <table>
      <thead>
         <tr>
            <th colspan=2>Kan skicka och ta emot</th>
            <th colspan=2>Kan skicka</th>
            <th colspan=2>Kan ta emot</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
            <td>Scoutnet-id</td>
            <td>Synkinställning</td>
         </tr>
         <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>scoutnet@scouterna.se, scoutid@scouterna.se</td>
            <td></td>
         </tr>
      </tbody>
   </table>

#### Google Drive - exempel
Att koppla ihop grupper med delade enheter på Google Drive sker manuellt, men du kan använda grupperna som skapats enligt ovan för enkel uppdatering av åtkomst.
Om du döper om själva gruppen, t.ex. e-postadressen, _kan_ gruppen tappa åtkomst till mappen. Detta då gruppen tas bort och en ny skapas med det nya namnet.

- Skapa en "Delad enhet" på Google Drive (https://drive.google.com) från ett konto med lämplig behörighet som finns med i kårens Google Workspace.
- Lägg till medlemmar till den delade enheten, du kan ange grupper som skapats ovan som medlemmar.

### Felmeddelanden och förslag till lösning
*  ```
   API-anrop till directory.users.insert misslyckades med felet: Domain user limit reached......
   ```
   Du har skapat maximalt antal Google-konton enligt din licens. Detta då din kår antaligen
   inte har skaffat Google Nonprofit och kör på en gammal gratislicens. På admin.google.com
   under Fakturering ska det stå "G Suite for Nonprofit" om du har det. Du kan läsa hos
   https://www.techsoup.se hur du skaffar Google Nonprofit.
