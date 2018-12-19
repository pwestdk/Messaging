# Blog
##### Gruppe A1: Emilie Hinsch Nielsen & Philip West Christiansen
##### Efterår 2018 -  Afleveret: 10/12/2018

# Bliv microservice pro med messaging!

# Abstract 
Microservices har som udgangspunkt ikke mulighed for at kommunikere med hinanden.  Anvendelsen af microservices er steget drastisk de seneste par år, men uden muligheden for kommunikation mellem de forskellige services er det ikke muligt at udnytte fordelene ved microservices. Messaging er en kommunikationsform der via messaging sikrer lav kobling og effektiv transfer af data mellem microservices. Man vil herved kunne opnå en effektiv og fleksibel kommunikationsform til microservices. 

# Problemstilling
Hvordan etablerer man bedst muligt kommunikation mellem microservices, der tillader både kompleksitet og fleksibilitet? 

# Introduktion
Der er mange forskellige teknologier der kan anvendes for at opnå kommunikation mellem microservices. Dem du sandsynligvis har brugt mest er REST og SOAP. En du muligvis ikke har hørt om er messaging queues. 
Ligesom REST, har messaging queues mange fordele, og blandt andet disse vil vi fokusere på i denne blog. 

Vi vil undersøge hvad der gør messaging queues unikke og i hvilke tilfælde du fordelagtigt vil kunne anvende messaging.
Dette skal ikke fremstå som messaging queues VS the world, men i stedet give dig en grundlæggende introduktion til hvad messaging queues er og i hvilke sammenhænge det er anvendeligt.

**Vi håber at når du har læst denne blog, har lyst til at prøve messaging queues af i et fremtidigt projekt.**

# Hvad er messaging
Messaging via queues er en teknologi der tillader, asynkront, at sende information, systemer imellem. Ved integrationsløsninger er der mange udfordringer at overkomme. Data skal transporteres fra computer til computer på tværs af netværk. Dette afføder forsinkelser, afbrydelser og er desuden langsomt. 

Systemerne der integreres kan benytte sig af forskellige programmeringssprog, OS, dataformater osv. Derudover ændrer systemerne sig over tid og kræver derfor løs kobling. 

Dette er også problemer messaging queues hjælper med at løse. 

![alt text](https://github.com/pwestdk/Messaging/blob/master/images/messaging1.png "Messaging 1")

## Hvordan fungerer messaging
Messaging queues fungerer ved at man sender pakker af data til hinanden. Disse pakker bliver kaldt messages. 

![alt text](https://github.com/pwestdk/Messaging/blob/master/images/messaging2.png "Messaging 2")

En message består af en header og en body. Headeren indeholder meta-data om, hvem afsender er, hvor den skal hen osv. Headeren bliver primært brugt af messagingsystemet.
Bodyen indeholder selve dataen og bliver primært brugt af modtager systemet. 
Disse messages bliver sendt via såkaldte channels, måske bedre kendt som queues.

Helt konkret er datastrukturen for en channel en collection eller array, hvor henholdsvis producer og consumer kan bruge. Datastrukturen for en message kan være så simpel som en streng, et bytearray eller objekt. 

**Hvem styrer hele dette menageri spørger du så?**

Det gør messaging systemet. Det er kommandocentralen der sørger for at modtage og sende messages korrekte channels.
I praksis kan programmer kun tilgå køerne gennem eksterne services for messaging systemet. De kan åbne en kø, putte en message på den, hente messages og lukke køer. 

# Fordele med messaging queues
Man kan med  fordel anvende messaging queues til microservices frem for teknologier som REST. Nedenfor er listet nogle af messaging queues største fordele:

**Lav kobling:**
- Ved anvendelsen af messaging har de forskellige services ikke kendskab til hinanden. Hver service informeres når de skal processere ny information. Den nye information kan nu bruges af en vilkårlig service. Lav kobling gør microservices klar til fremtidige ændringer i projektet. 

**Ingen blocking:**
- Messaging gør asynkron kommunikation muligt. Dette tillader microservices at arbejde multithreaded. Vi kan altså med messaging queues sende requests og processere samtidigt i stedet for at vente på et respons. 

**Simpel skalering:**
- Grundet lav kobling og asynkrone beskeder er messaging meget skalerbart. 

**Fejlhåndtering:**
- Hvis behandlingen af en message fejler vil den næste i køen stadig blive behandlet. Derved opstår der ikke bottlenecks når fejl opstår ved behandling af messages. 

**Mindre fokus på protokoller:**
- Messaging kræver ingen kommunikationsprotokol da messaging systemet tager sig af kommunikationen for dig. 

# Diskussion 
Messaging Queues har sine fordele især med microservices hvor lav kobling er essentielt, men der er også situationer hvor det ikke kan betale sig. I applikationer hvor vi på forhånd kender flowet i applikationen, kan det være hurtigere og mere simpelt at sætte en RESTful service op. Naturligvis vil dette medføre højere kobling, men det er ikke nødvendigvis altid en dårlig ting. Messaging queues understøtter asynkrone processer hvilket er en kæmpe styrke i det fleste situationer, dette bør tages med i dine overvejelser. Dette er især vigtigt når man bygger store komplekse enterprise systemer. 

# Konklusion 
Vi kan konkludere at messaging queues ikke nødvendigvis er svaret på alle dine bønner, men på en del af dem. I hvert fald hvis du arbejder med komplekse systemer bestående af microservices, der i et vist omfang har behov for understøttelsen af asynkron kommunikation. Derfor er det vigtigt at du analyserer dit behov grundigt, før du beslutter dig for om messaging queues passer til lige netop dit projekt. 

# Outlook
Vi håber på at vi har givet dig mod til at prøve kræfter med messaging efter at have læst denne blog. Som vi er kommet frem til kan det anvendes meget effektivt under visse omstændigheder. Hvis du vil prøve kræfter med Messaging anbefaler vi RabbitMQ. RabbitMQ er det mest udbredte open source messaging værktøj. Du kan læse mere [her](https://www.rabbitmq.com/ ). 



# Further Reading
- Microservices: https://blog.g2crowd.com/blog/trends/digital-platforms/2018-dp/microservices/
- REST: https://en.wikipedia.org/wiki/Representational_state_transfer
- RabbitMQ: https://en.wikipedia.org/wiki/RabbitMQ
- Why you should switch to messaging: https://dev.to/matteojoliveau/microservices-communications-why-you-should-switch-to-message-queues--48ia 
- REST vs Messaging: https://solace.com/blog/products-tech/experience-awesomeness-event-driven-microservices 
- You probably don’t need MQ: https://techblog.bozho.net/you-probably-dont-need-a-message-queue/ 
- Enterprise Integration Patterns: Designing, Building, and Deploying Messaging Solutions af 
 
