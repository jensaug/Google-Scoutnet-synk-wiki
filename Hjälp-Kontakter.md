# Kontakter - Hjälp
- Vi har personer i vår kår som använder sina privata e-postkonton i kåren. Går det att synkronisera kontakter med dem också.
  - Det går bra så länge som det är ett Google konto. Det är ingen skillnad på hur du som kåradmin behöver göra för att hålla isär det.

- Vi vill inte att ledare i kåren som slutar ska ha tillgång till uppgifter i kåren som de inte längre behöver. Hur rensar vi bort de kontakter som de har synkroniserat?
  - Om den föredetta ledaren inte längre är med på de listor som definerar vilka som ska ha behörighet för vissa kontakter kommer de att rensas bort. Om en ledare anger fel lösenord för sin synkronisering kommer också deras synkronisera kontakter att tas bort normalt sätt.

- Hur får jag kontakter i Google kontakter över till min telefon?
  - På samma sätt som om du skulle synkronisera dina Google kontakter med din telefon.

- Hur uppdaterar jag vilka som ska få synkronisera kontaktgrupper och kontakter?
  - Genom att uppdatera i kalkylbladet **Kontakter** och sen köra funktionen **updateContactGroupsAuthnSheetUsers**.

- Listan över vilka i kåren som ska få synkronisera kontakter uppdateras inte. Varför?
  - Kolla så att kalkylbladet **Kontakter** är uppdaterat.
  - Kolla att du har ställt in en utlösare att köra funktionen **updateContactGroupsAuthnSheetUsers** regelbundet.

- Hur ser jag till att kårens ledare kör synkroniseringen av kontakter regelbundet?
  - När ledare trycker på den stora gula knappen **Synkronisera kontakter** i deras kalkylark kommer det skapas en utlösare som gör att kontakter synkroniseras varje dygn.
