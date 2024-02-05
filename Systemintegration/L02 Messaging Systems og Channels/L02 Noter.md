### Lektionens dagsplan

![[Dagsplan02.pdf]]
### Litteratur
Enterprise_Integration_Patterns_-_Martin_Fowler.PDF
Kapitel 2-3
Kapitel 2: 141-165
Kapitel 3: 167 - 230


### Noter

#### Kapitel 2: Integration Styles

For at kunne iscenesætte hvad der skaber en god applikationsintegration, skal man overveje kriterier.
* Application coupling: Integreret applikationer skal minimere deres afhængighed af hinanden, så man kan videreudvikle en applikation uden at påvirke den anden. Høj samhørighed, lav kobling. 
* Technology Selektion: Forskellige former for systemintegrations teknologi kræver specifikt software, som kan være dyrere og kan kræve høj faglighed blandt udviklere. På samme tid, så kræver det også mere arbejde end nødvendigt at lave sådan en løsning fra scratch.
* Data Format: Integreret applikationer skal være enige om den data som de udveksler.

Der er et hav af forskellige kriterier, som kan findes yderligere på **side 143**, tilsvarende er der også flere valgmuligheder for at imødekomme krævende.
Heriblandt:
* File Transfer, Shared Database, Messaging.
Der vil dog senere blive taget udgangspunkt i Messaging, som kan defineres:
* Lad hver applikation forbinde til et fælles beskeds system og udveklse data samt udføre handlinger ved brug af beskeder. 


##### File Transfer
![[fileTransfer.png]]

Filer som vi kender det, er en universel mekanisme der anvendes til at bevare data. Det vil derfor være en yderst god ide at give disse applikationer muligheden for at kunne udveklse disse filer, dog kræver dette noget forarbejde. 
* Filformater skal overvejes, da outputtet fra en applikation måske ikke helt er hvad der er behov for, i den anden applikation .
* Hvornår skal filerne produceres og hvornår skal de "consumes". 
* Filnavngivning og i hvilken directory de skal opstås i skal også overvejes.
##### Shared Database
![[sharedDatabase.png]]
Når applikationer deler en fælles database, kan de let hente og gemme filer på et centralt sted, ved brug af relationelle databaser. Vi er så heldig at SQL næsten kan bruges i alle former for applikationer, der tillader filoverførsler.
Der kan dog opstå udfordringer som man skal være varsom omkring, når det kommer til anvendelsen af shared databaser.
* Hvis flere applikationer som bruger en shared database hyppigt anvender reads og modify på data, kan det skaber en flaskehals på databasens performance og skabe deadlocks, da applikationer spærrer vejen for hinanden. 

Hvis man nu heller vil integrere applikationers funktionalitet, frem for deres data kan man anvende Remote Procedure Invocation. Hvis man vil gøre brug af frekvente udvkeksling af data i små mængder, som bruger datatyper, kan man gøre brug af Messaging.
#RemoteProcedureInvocation #Messaging
##### Remote Procedure Invocation 
![[remoteProcedureInvocation.png]]
Hvis en applikation skal bruge informationer fra en anden, kan den direkte spørge applikationen. 
Hvis en applikation har brug for at ændre på data hos en anden, kan den gøre det ved at lave et kald til den anden applikation. 
Dette kaldes for encapsulation. 




##### Messaging
Når man har besluttet sig for at anvende messaging for system integration, er der nogle faktorer som man skal overveje.

 * Hvordan vil du transfer data packets?
En afsender sender data til en reciever ved at sende en message via en Message Channel, som forbinder afsenderen og recieveren.

* Hvordan ved man hvor man skal sende dataen?
Hvis afsenderen ikke ved hvor dataen skal sendes, kan den sende dataene til en **Message Router**, som vil dirigere dataene til den rette modtager. 

* Hvordan ved man hvilken data format man skal bruge?
Hvis afsenderen og modtageren ikke kan være enige om en data format, kan afsendere "directe" dataen til en **Message Translator** som kan konvertere dataen til modtagerens format, og dermed forwarde dataen til modtageren.

* Hvis man er en applikations udvikler, hvordan forbinder man sin applikation til dette message system?
En applikation, som ønsker at bruge beskedtjenester, vil implementere message endpoints for at udføre dens aktuelle afsendelse og modtagelse.


#### Kapitel 3: 