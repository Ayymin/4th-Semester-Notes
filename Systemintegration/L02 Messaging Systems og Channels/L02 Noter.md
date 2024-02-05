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
