# Hur gör jag för att...?
Nedan finns en del exempel med olika Scoutnet-id och e-postadresser på hur du gör för att
ställa in programmen så som du vill.
Om du saknar något exempel eller behöver hjälp är det bara att mejla emil.ohman@scouterna.se

## Grupper - inställningar exempel
* Hur gör jag om jag bara vill synkronisera grupper / e-postlistor?
   - Du kör funktionen `Grupper` i filen **Grupper.gs**.
   
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