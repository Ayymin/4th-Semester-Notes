### Lektionens Dagsplan 

![[Dagsplan01.pdf]]
### Litteratur
Enterprise_Integration_Patterns_-_Martin_Fowler.PDF
Side 83-140

### Noter

#### Hvad er integration?
Integration indenfor IT's verden betyder grundlæggende at få forskellige systemer til at arbejde sammen harmonisk og dele information effektivt. 

Brugeren tænker ikke over de interne systemgrænser, når de interagerer med en virksomhed. De udfører handlinger, der ofte involverer flere systemer, men systemerne fremstår som enkelte transaktioner.

For at beholde denne fremsættelse, kræver det at systemer og applikationer bliver integreret. 
#### Integrations udfordringer
Per definition, er integration ikke en nemt. På et entreprise niveau, arbejder man med flere forskellige applikationer, som kører på forskellige platforms, i forskellige steder. 
* I en virksomhed kræver det sammenhørighed på tværs af afdelinger. 
* Kan have store konsekvens, når kritiske funktioner er involveret. Dårlig ydeevne i integrationen kan føre til stort tab i kapital.
* Vedligeholdelse af EAI (Entreprise Application Integration) kan også være kompliceret, da man kan ende med komplekse blandinger af teknologier på baggrund af deres karakter. 

#### 6 typer af integration

##### Information Portals
Defineres som værktøjer, der samler information fra forskellige kilder og viser det på en skærm for at undgå, at brugeren skal tilgå flere systemer.
![[Informationsportal.png]]
For eksempel, en detailvirksomheder kan bruge en information portal, så deres kundeservicemedarbejdere nemt kan finde oplysninger om kundekøb, lagerbeholdning og leverings oplysninger fra forskellige systemer. 
##### Data Replication
![[DataReplikation.png]]
Mange forretningssystemer har brug for adgang til det samme data. Fx en kunde adresse, som bruges i kundeservice, regnskab, forsendelse og fakturering. Løses vha. en datareplikationsstrategi, som kan udføres på forskellige måde. Import/Eksport af datafiler kunne være et eksempel.
##### Shared Business Function
![[msedge_sF2ShcrmjJ.png]]
For at undgå redundante funktioner, hvor flere systemer skal kontrollere, om et stykke information er gyldigt, kan man implementere en Shared business Function, der kun skal udvikles en gang og derefter deles som en tjeneste til andre systemer. 


##### Service-Oriented Architecture
![[Service-OrientedArchitecture.png]]
Service Oriented Architecture (SOA) anvender tjenester som grænseflader til at tillade forskellige softwarekomponenter eller systemer at kommunikere og samarbejde. Tjenester fungerer som standardiserede skabeloner, der gør det nemmere for forskellige systemer at integrere og udveklse data samt funktionalitet, på samme måde som et interface i programmering. 

