# VPR

Must be implement at some point into project:
- Profile: Old Partys (Bewertung)
- Profile: Picture (Image)
- Profile: Recipes (Bewertung)
- Profile: Recipes (Bewertung)
- SQL: E-Mail Syntax
- real Chat implement for party and between users
- no idea how to make the notifications

Finished:
- Partylize
- LoginScreen -> Chris login and register version
- LogoutScreen
- Navigation
- MainScreen
- ProfilePage
- RecipeSearch (more or less) -> Robert Task
- Party
- Chat
- NotificationBar (0%)
- Options (0%) -> Dominik Task (implement SQL, remove Colors)

Changes to MySQL-Database:
- BringerDrinks
- BringerSnacks
- PrivateParty & PublicParty -> Party
- Snack

Added MySQL-Tables:
- ProfileInPrivateParty
- ProfileInPublicParty

Removed Tables:
- Drinks

SQL PartyManipulation:
added:
- getPartys()
- getFriendsNotInParty()
- addFriendsToParty()
- getParticipantsInParty()
- removeParticipantFromParty()
- getGiftName()
- getGiftsInParty()
- getGiftsAdded()
- getGiftsNotAdded()
- addGiftsToParty()
- removeGiftsFromParty()
- isUserInPublicParty()
- getPartyInformation()
- createParty()
- deleteParty()
- updatePartyInformation()
removed:
- checkIfFriendIsAlreadyParticipant
- addParticipantToPrivateParty
- inviteFriendToPrivateParty
- getPartyId()
change:
- createPrivateParty() --> createParty()

SQL ProfileManipulation:
added:
- getFriends()

TIPPS FOR EVERYONE:
- Wenn Ihr dieselbe Codezeile bzw. denselben Codeschnipsel mehr als 1x schreibt -> in Methode auslagern (spez. die FX-Leute mit ihren Styles)
- Wenn eine Variable nur geschrieben und nie gelesen wird ist sie nutzlos und kann raus!
- Es gibt immer nur EINE main, das heißt es gibt auch nur 1 Datei, in der primaryStage.show() aufgerufen wird.
- "extends Application" nur dann, wenn ihr in der main-Class seid.
- Wenn jede Datenbank-Klasse dieselben variablen, denselben Konstuktor, eine getInstance() und eine endConnection() hat dann lagert man das aus und extended auf die ausgelagerte Klasse.
- Wenn ihr kleine Funktionen habt, wie getUserName(int id), dann passt mit getInstance() und endConnection() auf. 
  Große Funktionen rufen diese im try-and-catch auf und ein endConnection() mittem im try-and-catch zerschießt die gesamte Funktion.
- Bitte nicht 3 unterschiedliche teams an den SQL Tabellen arbeiten lassen! Dabei entsteht nur quatsch.
- Der PrimaryKey in eine Tabelle heißt (eigentlich immer) id!!!!!
- Wenn jemand nicht gut ist mit SQL dann sagt das und lasst andere diese Tasks machen.
- Okay...... An alle die SQl-Abfrafen gemacht haben (ich möchte niemanden angucken O.O) -> Schritt 1: SELECT * FROM table;
  Ich habe ungefähr 7 Funktionen gefunden wo SELECT xy WHERE id = whatever ...! Diese Regel hat einen Sinn!
- RICHTIG -> while(results.next()) { ... } | FALSCH -> results.next(); ... -> Führt zu fehlern bei falschen paragraphen | MÖGLICH -> if(result.next()) { ... } else { ... }
- NEVER EVER packt man einen SQL-Datenbank Wert UNIQUE, ausßer man weiß mit 100% sicherheit, das dieser nur ein mal vorkommt. Wer auch immer diebeiden Bringer Tabellen geschrieben hat 
  und snackId und drinksId auf UNIQUE gesetzt hat soll sich schämen. Jeder Drink/Snack kann nur zu einer Feier (global) mit genommen werden.... 
- Bitte niemals min und max Size auf dasselbe setzen. Dadurch wird alles umgerückt. Allgemein eher auf min Size verzichten außer es geht wirklich nicht andern.
