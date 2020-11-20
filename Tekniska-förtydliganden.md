# Tekniska förtydliganden
## E-postalias
I vissa specifika fall kan det bli ett felmeddelande i loggen då ett alias till en e-postadress
redan är tillagd. Detta kan vara då en användare t.ex själv har lagt till en e-postadress
abc123@hotmail.se som en alternativ e-postadress för sitt Google-konto hos Google och vi lägger till
hotmail.se-adressen då i e-postlistan för att sedan försöka lägga till den riktiga Gmail-adressen i listan,
tex. abc123@gmail.com som. Det blir då ett fel då denna adress redan är tillagd som alias kan man typ säga,
och Google-gruppen tolkar då dessa adressen som samma. Om båda dessa adresser (abc123@hotmail.se &
abc123@gmail.com) läggs till kan dock inte programmet i förväg veta att de hör ihop utan det märker
det först när den försöker lägga till den andra adressen.
Du löser felet genom att köra programmet igen om du startade det manuellt alternativt invänta nästa
schemalagda körning.

## E-postadresser genereras på följande sätt.
1. För och efternamn görs om till gemener och tar bort alla mellanslag och
   andra tomrum som är skrivet i de fälten i Scoutnet.
1. Därefter görs bokstäverna om till bokstäver som lämpar sig för e-postadresser.
   T.ex åäö blir aao.
1. Om det därefter finns några fler konstiga tecken kvar som inte lämpar sig för
   e-postadress så tas de bort.