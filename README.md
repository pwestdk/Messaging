# Blog
##### Gruppe A1: Emilie Hinsch Nielsen & Philip West Christiansen
##### Efterår 2018 -  Afleveret: 10/12/2018

# Table of Contents
<!--ts-->
  * [Introduction](#introduction)  
  * [Process](#process)    
      * [Collaboration summary](#collaboration-summary)   
      * [Meetings](#meetings)   
          * [31/10/2018 - Introduction meeting](#31102018---introduction-meeting)
          * [07/11/2018 - First official meeting](#07112018---first-official-meeting)
          * [12/11/2018 - Showing of results, subject change RFID and LIFI](#12/11/2018-showing-of-results,-subject-change-RFID-and-LIFI)
          * [14/11/2018 - Showing of results, subject change foodwaste](#14112018---showing-of-results-subject-change-foodwaste)
          * [19/11/2018 - Showing our results, subject change to Countries with most frequent RFID use](#19112018---showing-our-results-subject-change-to-countries-with-most-frequent-rfid-use)
          * [22/11/2018 - Subject change back to original subject](#22112018---subject-change-back-to-original-subject)
          * [29/11/2018 - Update meeting](#29112018---update-meeting)
      * [Contact forum](#contact-forum) 
  * [Contract](#contract) 
      * [Product](#product)   
      * [Pricing](#pricing)   
      * [Team](#team)   
      * [Delivery date](#delivery-date)
  * [Billing](#billing) 
  * [Final product](#final-product) 
  * [User documentation](#user-documentation) 
  * [Data sources](#data-sources) 
  * [Technical documentation](#technical-documentation)                                      
      * [Datasets formatting](#datasets-formatting)   
          * [Formatting original datasets](#formatting-original-datasets)
          * [joining the datasets](#joining-the-datasets)
          * [Graphs](#graphs) 
      * [Showing our product](#showing-our-product)                                     
<!--ts-->

# Bliv Microservice pro med RabbitMQ!

![alt text](https://cdn-images-1.medium.com/max/1600/1*UnYL-2r54_7AnEwQv0cVxA.png "RabbitMQ")

# Abstract 
Microservices har som udgangspunkt ikke mulighed for at kommunikere med hinanden.  Anvendelsen af microservices er steget drastisk de seneste par år, men uden muligheden for kommunikation mellem de forskellige services er det ikke muligt at udnytte fordelene ved microservices. Messaging er en kommunikationsform der via messaging sikrer lav kobling og effektiv transfer af data mellem microservices. Man vil herved kunne opnå en effektiv og fleksibel kommunikationsform til microservices. 

# Problemstilling
Skrives her
Microservices skal snakke sammen

# Introduktion
Der er mange forskellige teknologier man kan anvende for at opnå kommunikation mellem microservices. De teknologier du sandsynligvis har brugt mest er REST og SOAP. En teknologi som du muligvis ikke har hørt om er messaging. Ligesom REST og SOAP har messaging mange fordele, og blandt andet disse vil vi fokusere på i denne blog. 

Vi vil ligeledes se på hvad der gør messaging unikt og hvorfor du i visse tilfælde fordelagtigt vil kunne anvende messaging  frem for andre teknologier. Dette skal ikke fremstå som messaging VS the world, men i stedet give dig en grundlæggende introduktion til hvad messaging er og i hvilken sammenhænge det succesfuldt kan anvendes.

**Vi håber at når du har læst denne blog, har lyst til at prøve messaging af i et fremtidigt projekt. **

# Hvad er messaging
Ved integrationsløsninger er der mange udfordringer at overkomme. Data skal transporteres fra computer til computer på tværs af netværk. Dette afføder forsinkelser, afbrydelser og er desuden langsomt. 

Systemerne der integreres kan benytte sig af forskellige programmeringssprog, OS, dataformater osv. Derudover ændrer systemerne sig over tid og kræver derfor løs kobling. 

Dette er også problemer messaging hjælper med at løse. 

## Hvordan fungerer messaging
Messaging fungerer ved at man sender pakker af data til hinanden. Disse pakker bliver kaldet messages. 

En message består af en header og en body. Headeren indeholder meta-data om, hvem afsender er, hvor den skal hen osv. Headeren bliver primært brugt af messagingsystemet.
Bodyen indeholder selve dataen og bliver primært brugt af modtager systemet. Disse messages bliver sendt via såkaldte channels, måske bedre kendt som queues.

Helt konkret er datastrukturen for en channel en collection eller array, hvor henholdsvis producer og consumer kan bruge. Datastrukturen for en message kan være så simpel som en streng, et bytearray eller objekt. 

**Hvem styrer hele dette menageri spørger du så?**

Det gør messagingsystemet. Det er kommandocentralen der sørger for at modtage og sende messages korrekte channels.

# REST, SOAP eller Messaging
Man kan med  fordel anvende Messaging til microservices frem for teknologier som REST og SOAP. Med udgangspunkt i REST vs Messaging vil vi her sætte dem op mod hinanden. 

## REST

*Høj kobling*
Man vil ikke kunne lave et system uden kobling. Med RESTful services antages der at dataen altid kun leveres til samme sted. Problemet opstår når der i fremtiden implementeres nye komponenter der har brug for dataen. Selvfølgelig kan koden opdateres så den understøtter et nyt endpoint, men dette medfører unødvendig kobling, hvilket strider mod pointen med microservices.

*Blocking*
Når du initialisere en RESTful service, blokerer din service alt andet trafik mens den venter på et respons. Dette gør applikationen langsom, gør multithreading umuligt og ligeledes er applikationen ikke skalerbar. 

## Messaging

*Lav kobling*
Ved anvendelsen af messaging har de forskellige services ikke kendskab til hinanden. Hver service informeres når de skal processere ny information. Den nye information kan nu consumes af en vilkårlig service. Lav kobling gør microservicesne klar til fremtidige ændringer i projektet. 

*Ingen blocking*
Messaging gør asynkronitet muligt. Dette tillader microservices at arbejde multithreaded. Vi kan altså med messaging sende requests og processere samtidigt i stedet for at vente på et respons. 

*Simpel skalering*
Grundet lav kobling og asynkrone beskeder er messaging meget skalerbart. 

# Diskussion 

# Konklusion 

# Outlook


# Litteraturliste
https://blog.g2crowd.com/blog/trends/digital-platforms/2018-dp/microservices/

REST: https://en.wikipedia.org/wiki/Representational_state_transfer
SOAP: https://en.wikipedia.org/wiki/SOAP 
RabbitMQ: https://en.wikipedia.org/wiki/RabbitMQ
Why you should switch to messaging: https://dev.to/matteojoliveau/microservices-communications-why-you-should-switch-to-message-queues--48ia 
REST vs Messaging: https://solace.com/blog/products-tech/experience-awesomeness-event-driven-microservices 






