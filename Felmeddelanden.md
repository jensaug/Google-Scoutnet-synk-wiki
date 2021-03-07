# Felmeddelanden och förslag till lösning
*  ```
   GoogleJsonResponseException: API call to directory.groups.get failed with error: Resource Not Found: groupKey
   ```
   Det unika identifikationsnumret för denna grupp som lagras i kolumn **J** i kalkylarket finns inte längre. Antagligen har gruppen tagits bort manuellt.
   Detta lösas enklast genom att ta bort det identifikationsnummer som lagras i kolumn **J** på aktuell rad och sen köra programmet igen.

*  ```
   API-anrop till directory.users.insert misslyckades med felet: Domain user limit reached......
   ```
   Du har skapat maximalt antal Google-konton enligt din licens. Detta då din kår antaligen
   inte har skaffat Google Nonprofit och kör på en gammal gratislicens. På admin.google.com
   under Fakturering ska det stå **G Suite for Nonprofit** om du har det. Du kan läsa hos
   https://www.techsoup.se hur du skaffar Google Nonprofit.