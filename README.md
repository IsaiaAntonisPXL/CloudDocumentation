# Cloud samenvatting

## Opfrissing cloud concepten

![title](images/4layersaws.png)
### AWS layers
AWS bestaat uit 4 lagen,

1. __Infrastructure__

De onderste laag biedt de fysieke en virtuele basis voor alle andere diensten. Dit omvat:

    Regions: Geografische gebieden waar AWS-datacenters zich bevinden (bijvoorbeeld Europa, Noord-Amerika).
    Voorbeeld: Als je een applicatie in Europa wilt hosten voor een lagere latentie bij Europese gebruikers, kies je een regio zoals Frankfurt.
    Availability Zones: Subsets binnen een regio met meerdere datacenters voor hoge beschikbaarheid.
    Voorbeeld: Je kunt je database in meerdere zones repliceren, zodat een storing in één zone geen impact heeft.
    Edge locations: Locaties dicht bij gebruikers om content sneller te leveren via een CDN zoals Amazon CloudFront.
    Voorbeeld: Video's streamen via CloudFront levert snellere prestaties voor gebruikers wereldwijd.

2. __Foundation Services__

Deze laag biedt fundamentele bouwstenen zoals rekenkracht, opslag en netwerken:

    Compute: Diensten zoals Amazon EC2 en Lambda voor het uitvoeren van code of applicaties.
    Voorbeeld: Gebruik EC2-instanties om een website te hosten.
    Networking: Verbindingen tussen diensten en gebruikers, inclusief VPC's en load balancers.
    Voorbeeld: Met een Load Balancer kun je verkeer verdelen tussen meerdere servers.
    Storage: Diensten zoals S3, EBS en Glacier voor object-, blok- en archiefopslag.
    Voorbeeld: Sla afbeeldingen of backups op in S3.

3. __Platform Services__

Biedt meer geavanceerde diensten zoals databases, analytics en DevOps-tools:

    Databases: Relational (RDS), NoSQL (DynamoDB), of caching (ElastiCache).
    Voorbeeld: Gebruik DynamoDB om gebruikersgegevens in een mobiele app op te slaan.
    Analytics: Data-analyse zoals Amazon Redshift of EMR.
    Voorbeeld: Analyseer websitegebruikers met Redshift.
    Deployment and management: Tools voor containers, monitoring en infrastructuurbeheer, zoals CloudFormation of EKS.
    Voorbeeld: Automatiseer de implementatie van je infrastructuur met CloudFormation.

4. __Applications__

Deze bovenste laag biedt eindgebruikersgerichte diensten zoals virtuele desktops, samenwerking en mobiele diensten:

    Mobile Services: Tools zoals AWS Cognito voor identiteitsbeheer in mobiele apps.
    Voorbeeld: Voeg loginfunctionaliteit toe aan je app met Cognito.
    Collaboration: Tools zoals WorkSpaces voor samenwerking en virtuele werkplekken.
    Voorbeeld: Stel werknemers in staat op afstand te werken via virtuele desktops.
### Foundation services

#### 1. Compute
![title](images/foundation_compute.png)
#### 1.1 Common used compute services and their use cases
1. __Amazon EC2 (Elastic Compute Cloud)__

A service that provides resizable virtual servers (instances) in the cloud.
__Use Cases__:

    Hosting websites and applications.
    Running custom software that requires specific operating systems or configurations.
    Batch processing workloads.
    Running legacy applications that can’t easily be containerized or serverless.

2. __AWS Lambda__

A serverless compute service that runs your code in response to events.
__Use Cases__:

    Building microservices or APIs.
    Running short-lived, event-driven functions (e.g., processing S3 uploads, triggering actions from database changes).
    Automating infrastructure tasks like resizing images or monitoring logs.
    Real-time data processing, such as streaming data from IoT devices.

3. __Amazon ECS (Elastic Container Service)__

A container orchestration service to deploy and manage containerized applications.
__Use Cases__:

    Running Docker containers for microservices-based architectures.
    Orchestrating containerized batch jobs.
    Hosting scalable APIs or backend services.

4. __Amazon EKS (Elastic Kubernetes Service)__

A managed Kubernetes service to run Kubernetes clusters without managing the control plane.
__Use Cases__:

    Running containerized workloads using Kubernetes-native tools.
    Migrating on-premises Kubernetes workloads to AWS.
    Managing multi-cloud or hybrid Kubernetes clusters.


#### 2. Storage
![title](images/foundation_storage.png)
#### 2.1 Common used storage services and their use cases
Here are the top 4 commonly used AWS Storage Services and their use cases:
1. __Amazon S3 (Simple Storage Service)__

A highly scalable, durable, and cost-effective object storage service.

__Use Cases__:

    Data backups and archiving: Storing backups or compliance-related data.
    Static website hosting: Hosting static files like HTML, CSS, and images.
    Big data storage: Storing raw data for analytics, such as logs or IoT device data.
    Media storage: Storing large media files like videos, images, or audio.

2. __Amazon EBS (Elastic Block Store)__

Block storage for use with Amazon EC2 instances, designed for low-latency workloads.

__Use Cases__:

    Database storage: Running high-performance relational or NoSQL databases like MySQL or MongoDB.
    Transactional workloads: Supporting applications that require low-latency, high-throughput access.
    Boot volumes: Hosting the root file system of an EC2 instance.

3. __Amazon EFS (Elastic File System)__

A fully managed, scalable file storage for use with AWS compute services.

__Use Cases__:

    Shared storage: Providing a shared file system for multiple EC2 instances or containers.
    Content management systems: Hosting shared content like media assets or configuration files.
    Big data and analytics: Storing large datasets accessible by multiple processing nodes.

4. __Amazon Glacier (S3 Glacier)__

A low-cost storage service for archiving and long-term data storage.

__Use Cases__:

    Cold storage: Archiving infrequently accessed data such as compliance records or legal documents.
    Disaster recovery: Storing backups for recovery in the event of data loss.
    Data retention: Retaining data for regulatory or historical purposes at a low cost.


#### 3. Network
![title](images/foundation_network.png)
#### 3.1 Common used network services and their use cases

1. __Amazon VPC (Virtual Private Cloud)__

A service that lets you create a logically isolated network environment in AWS.

__Use Cases__:

    Isolating workloads: Running sensitive applications in a private network.
    Hybrid cloud environments: Connecting on-premises networks to AWS using VPN or Direct Connect.
    Custom networking: Defining custom subnets, routing tables, and security groups.

2. __Amazon CloudFront__

A content delivery network (CDN) that caches data at edge locations for faster delivery.

__Use Cases__:

    Content delivery: Serving static and dynamic content like websites, videos, or APIs.
    Global reach: Improving performance for users in different regions.
    DDoS protection: Enhancing security through integration with AWS Shield.

3. __Elastic Load Balancing (ELB)__

Automatically distributes incoming traffic across multiple targets (e.g., EC2 instances, containers).

__Use Cases__:

    High availability: Ensuring application reliability by routing traffic to healthy instances.
    Scaling applications: Distributing traffic as instances scale up or down.
    Multi-AZ deployments: Balancing traffic across multiple availability zones for fault tolerance.

4. Amazon Route 53__

A scalable DNS and domain name management service.

__Use Cases__:

    Domain management: Registering and managing domains directly through AWS.
    Routing traffic: Directing traffic to endpoints (e.g., EC2 instances, S3 buckets) based on routing policies like geolocation or latency.
    Failover: Automatically redirecting traffic during outages to backup servers.
#### 4. Security
![title](images/foundation_security.png)
#### 4.1 Common used security services and their use cases

1. __AWS Identity and Access Management (IAM)__

A service that controls access to AWS resources using users, roles, and policies.

__Use Cases__:

    User authentication and authorization: Managing who can access specific AWS resources.
    Granular permissions: Enforcing least privilege access for different teams or services.
    Service-to-service access: Allowing secure interactions between AWS services using roles.

2. __AWS Key Management Service (KMS)__

A managed service for creating and controlling encryption keys.

__Use Cases__:

    Data encryption: Encrypting data in S3, EBS, or RDS.
    Application-level encryption: Securing sensitive data like API keys or user credentials.
    Compliance: Meeting regulatory requirements by managing cryptographic keys securely.

3. __AWS CloudTrail__

A service that provides governance, compliance, and operational audit logs of AWS account activities.

__Use Cases__:

    Audit logging: Tracking changes to resources and identifying unauthorized access.
    Security analysis: Monitoring and investigating suspicious activities.
    Compliance reporting: Proving adherence to regulations by providing an activity history.
### Platform services
#### 1. Regions

Een "Region" is een geografische locatie waar AWS datacenters (Availability Zones) zijn gevestigd. Elke regio bestaat uit meerdere zones om hoge beschikbaarheid en fouttolerantie te garanderen.

In eigen woorden: Dit is de fysieke plek waar je applicaties en data worden gehost. Je kiest een regio dicht bij je gebruikers om de prestaties te verbeteren.

Bij het kiezen van een regio moet je wel op onderstaande letten:
- __data goverance/legaliteit__
- __latency__
- __beschikbare services in de region__
- __costs__

__Voorbeeld__:

    Amazon EU (Frankfurt) Region: Een Europese e-commercewebsite gebruikt de Frankfurt-regio om lage latentie te bieden aan klanten in Europa.

__Use case:__ Het kiezen van een regio dicht bij klanten om snellere responstijden te realiseren.

#### 2. Availability Zones (AZs)

Een regio bevat meerdere AZ's, die bestaan uit afzonderlijke datacenters met eigen stroom, koeling en netwerk. Ze zijn ontworpen om onafhankelijk te zijn, maar ook om met elkaar te communiceren via snelle verbindingen.

In eigen woorden: Een AZ is een cluster van datacenters in een regio. Het gebruik van meerdere AZ's zorgt ervoor dat je applicatie online blijft, zelfs als een van de zones faalt.

__Voorbeeld__:

    Een applicatie die gebruikmaakt van meerdere AZ's in de US East (N. Virginia) Region om downtime te voorkomen.
__Use case:__ Het draaien van een database in twee AZ's met automatische failover voor hoge beschikbaarheid.

#### 3. Edge Locations

Edge-locaties zijn datacenters die zich dicht bij eindgebruikers bevinden en worden gebruikt door AWS-diensten zoals Amazon CloudFront. Ze verbeteren de prestaties van applicaties door content dichter bij de gebruiker te brengen.

In eigen woorden: Dit zijn datacenters verspreid over de hele wereld die zorgen voor snelle levering van content zoals websites, video's en API's.

__Voorbeeld__:

    Een streamingplatform maakt gebruik van een edge-locatie in Tokyo om video's met lage latency te leveren aan kijkers in Japan.

__Use case:__ Een internationaal bedrijf gebruikt edge-locaties om een wereldwijd publiek snel toegang te bieden tot statische en dynamische content.
## System tools

AWS Systems Manager is een krachtige service voor het beheren van de infrastructuur van AWS-cloudomgevingen. Het biedt een breed scala aan tools voor het beheren, bewaken en automatiseren van IT-operaties. Hieronder worden verschillende concepten en gerelateerde services binnen AWS Systems Manager besproken.
Algemeen Concepten van AWS Systems Manager

#### 1. Maintenance Windows

Dit is een geplande tijdsperiode waarin systeemonderhoud kan plaatsvinden zonder dat het invloed heeft op de gebruikerservaring of de werking van de service.
Voorbeeld:

    Een organisatie plant onderhoud voor haar servers in een Maintenance Window van 00:00 tot 04:00, zodat er minimale impact is op de productieomgeving.

#### 2. Compliance

Compliance in AWS Systems Manager houdt in dat je ervoor zorgt dat je infrastructuur voldoet aan de specifieke standaarden en beleidsregels die van toepassing zijn op je omgeving.
Voorbeeld: 

    Het automatisch controleren of alle instances voldoen aan de beveiligingsrichtlijnen, zoals het gebruik van versleutelde volumes en het uitvoeren van beveiligingspatches.

#### 3. Fleet Manager

Deze service biedt een gecentraliseerde interface voor het beheren van meerdere instances over verschillende AWS-regio's en helpt bij het volgen van de status en prestaties.
Voorbeeld: 

    Een beheerder gebruikt Fleet Manager om een overzicht te krijgen van alle EC2-instances, hun status en recent uitgevoerde taken.

#### 4. Incident Manager

Een tool die helpt bij het identificeren, onderzoeken en herstellen van incidenten in de AWS-omgeving. Het biedt een gestandaardiseerd proces voor incidentbeheer.
Voorbeeld: 

    Wanneer er een storing optreedt in een productieomgeving, kan Incident Manager helpen bij het coördineren van de respons, zodat het probleem snel wordt opgelost.

#### 5. State Manager

State Manager helpt bij het automatiseren van configuratiebeheer door ervoor te zorgen dat de gewenste configuratie op een systeem aanwezig is.
Voorbeeld: 
    
    Het automatisch configureren van alle instances in een bepaalde regio om altijd een specifieke versie van een applicatie uit te voeren.

### AWS Systems Manager Service


AWS Systems Manager is een uitgebreide beheeroplossing voor AWS-cloudinfrastructuren, waarmee je automatisch je virtuele servers kunt beheren, configureren en schalen. Het biedt tools zoals automation, compliance monitoring, patchbeheer en incidentmanagement om je IT-infrastructuur efficiënt te beheren.

__Praktische Case__

: Stel je voor dat een bedrijf een cloudgebaseerde webapplicatie uitvoert op verschillende EC2-instances. Ze gebruiken AWS Systems Manager om regelmatig patches te implementeren, beveiligingsinstellingen te controleren, en de prestaties van hun infrastructuur in de gaten te houden. Dit vermindert handmatige fouten, verhoogt de uptime en zorgt ervoor dat de applicatie altijd voldoet aan de nieuwste beveiligingsrichtlijnen.

__AWS Session Manager__
__AWS Session Manager__ maakt veilige, gemakkelijke en auditeerbare verbindingen mogelijk naar instances zonder dat een SSH of RDP nodig is. Dit biedt een gemakkelijke manier om beheer op instances uit te voeren zonder directe netwerktoegang.

__Praktische Case__

: Een IT-beheerder wil inloggen op een __EC2-instance__ om bepaalde systeeminstellingen te controleren zonder deze toegang via SSH te doen. Ze gebruiken __AWS Session Manager__ om verbinding te maken, wat __de veiligheid verhoogt__ omdat __geen open netwerkpoort nodig__ is.
Vereisten voor __AWS Session Manager__

    IAM-rollen: De juiste IAM-rollen moeten zijn toegewezen voor toegang tot de instances via Session Manager.
    Systeemvereisten: AWS Systems Manager Agent (SSM Agent) moet geïnstalleerd en draaiende zijn op de instance.
    Beveiliging: Er moeten de juiste permissies worden gedefinieerd in AWS IAM voor het gebruik van Session Manager.

#### Advanced Features van AWS Session Manager
##### 1. Port Forwarding:

Hiermee kun je netwerkpoorten van een EC2-instance via een beveiligde tunnel doorsturen.
Voorbeeld: 

    Je kunt een lokale poort op je machine doorsturen naar een databasepoort op een EC2-instance zonder dat er een directe netwerkverbinding nodig is.

##### 2. Session Logging:

    Alle sessies kunnen worden vastgelegd voor auditen en troubleshooting.
    Voorbeeld: 
    
        Een organisatie configureert loggen om te controleren welke acties beheerders uitvoeren op de EC2-instances via Session Manager.

### AWS OpsCenter


__OpsCenter__ helpt bij het organiseren van incidentbeheer binnen AWS, door het automatisch creëren en beheren van incidenten, ook wel __"OpsItems"__ genoemd. Het biedt teams een centrale plaats om problemen op te lossen en de status bij te houden.

__Praktische Case__

: Een organisatie gebruikt __OpsCenter__ om automatisch incidenten te genereren wanneer een kritieke service uitvalt, zoals een database die niet beschikbaar is. Het team kan het probleem snel identificeren en oplossen, met alle communicatie en logboeken verzameld in een enkel OpsItem.

__AWS Parameter Store__
__AWS Systems Manager Parameter Store__ biedt veilige opslag voor configuratie-instellingen, zoals API-sleutels, wachtwoorden en andere gevoelige gegevens.

__Praktische Case__

: Een ontwikkelaar slaat API-sleutels voor een externe service op in Parameter Store, zodat deze veilig kunnen worden opgehaald door EC2-instances zonder hardcoding van de sleutels in de applicatiecode.

#### Key Features van AWS Parameter Store

__Veilige opslag van gegevens__:
Voorbeeld: 

        API-sleutels worden versleuteld opgeslagen en kunnen alleen door geautoriseerde gebruikers worden opgehaald.

__Versiebeheer__:
    Voorbeeld: 
    
    Wanneer een API-sleutel wordt gewijzigd, kan de vorige versie behouden blijven zodat systemen die die sleutel nog gebruiken niet breken.

__Integratie met andere AWS-services__:
        Voorbeeld: 
        
        Parameter Store kan automatisch worden geïntegreerd met EC2-instances via IAM-rollen om de vereiste parameters op te halen.

##### Private vs Public Parameters en References

__Private Parameters__:
Bevat gevoelige gegevens die versleuteld moeten worden opgeslagen.
    Voorbeeld: 
        
        Wachtwoorden voor databases.

__Public Parameters__:
Bevat niet-gevoelige gegevens die niet versleuteld hoeven te worden.
Voorbeeld:
        
         Een configuratie-instelling zoals de versie van een applicatie.

__References__:
Verwijzingen naar andere parameters die binnen je infrastructuur worden gebruikt.
Voorbeeld: 

    Een parameter die naar een andere parameter verwijst, zoals de naam van een database.

#### AWS Automation Runbook


__AWS Automation Runbook__ is een set geautomatiseerde stappen die worden uitgevoerd om routinematige of complexe taken binnen AWS te voltooien. Runbooks kunnen worden geconfigureerd om automatisch actie te ondernemen op basis van een trigger.

__Praktische Case__
: Een organisatie gebruikt een Runbook om automatisch een EC2-instance te herstarten als het wordt gedetecteerd dat de instance meer dan een bepaalde hoeveelheid tijd zonder reactie is.
##### Voor- en Nadelen van AWS Automation Runbooks
__Voordelen:__

__Automatisering van repetitieve taken:__
        Voorbeeld: 
        
        Het automatisch patchen van systemen zonder handmatige interventie.
__Consistentie in uitvoering:__
        Voorbeeld: 
        
        Het uitvoeren van dezelfde set van handelingen in meerdere regio's zonder menselijke fouten.

__Nadelen__:

__Complexiteit van configuratie:__
        Voorbeeld: 
        
        Het opzetten van een Runbook voor een geavanceerde infrastructuur kan tijdrovend en complex zijn.
__Kosten__:
        Voorbeeld: 
        
        Het uitvoeren van veel automatisering kan de kosten verhogen afhankelijk van de vereiste resources.

### AWS Automation Runbook binnen het IaC Landschap
Vergelijking met Andere Frameworks

Automation Runbooks in AWS kunnen worden vergeleken met Infrastructure-as-Code (IaC) tools zoals Terraform of CloudFormation. Het verschil is dat Runbooks specifiek gericht zijn op het automatiseren van operationele taken, terwijl IaC zich richt op het definiëren van infrastructuur en resources.
## Finops tools

Cloud FinOps (Financial Operations) is het raamwerk dat bedrijven helpt om cloudkosten efficiënt te beheren, te optimaliseren en te voorspellen. Het combineert de technische en financiële kant van cloudinfrastructuren en richt zich op samenwerking tussen teams om een beter begrip van kosten en waarde te verkrijgen.
### Algemene Concepten in FinOps
#### 1. FinOps

FinOps is een set van best practices, processen en tools die bedrijven helpen bij het beheren van hun cloudkosten, terwijl ze de waarde van de cloud optimaliseren. Het zorgt voor samenwerking tussen de technische, financiële en operationele teams.
    __Voorbeeld:__ 
    
    Een bedrijf implementeert FinOps om realtime kosten te volgen, verantwoording af te leggen en samenwerking tussen teams te verbeteren, zodat kostenbeheersing en waarde-maximalisatie hand in hand gaan.

#### 2. AWS Budgets

AWS Budgets stelt je in staat om budgetten in te stellen voor cloudkosten en verbruik. Het biedt waarschuwingen wanneer de werkelijke uitgaven of het verbruik een ingesteld limiet overschrijden.
    __Voorbeeld:__ 
    
    Een bedrijf stelt een maandelijks budget in voor zijn AWS-diensten en ontvangt een melding als het 80% van het budget overschrijdt.

#### 3. Spot Instances

Spot Instances zijn tijdelijke EC2-instances die gebruik maken van ongebruikte capaciteit van AWS tegen lagere prijzen.
    __Voorbeeld:__ 
    
    Een bedrijf draait een batchverwerkingsprogramma op Spot Instances om de kosten drastisch te verlagen, zolang de processen niet kritisch zijn voor tijdige uitvoering.

#### 4. Reserved Instances

Reserved Instances (RI) zijn vooraf betaalde, langdurige instances die aanzienlijke kortingen bieden ten opzichte van on-demand prijzen.
    __Voorbeeld:__ 
    
    Een organisatie koopt Reserved Instances voor een periode van drie jaar om zijn servercapaciteit te verlagen en kosten te besparen voor zijn langdurige workload.

### 3 Eigenschappen van Cloud FinOps

__Realtime kostenbeheer__:
        Cloud FinOps zorgt ervoor dat je continu inzicht hebt in de werkelijke uitgaven in de cloud. Dit stelt bedrijven in staat om snel in te grijpen bij onverwachte kostenstijgingen.
        Voorbeeld: 
        
        Een organisatie stelt een alarm in voor overmatige kosten in AWS en krijgt real-time meldingen wanneer het budget wordt overschreden.

__Kostenoptimalisatie door samenwerking:__
        FinOps vereist samenwerking tussen de financiële en technische teams om de cloudkosten te optimaliseren.
        Voorbeeld: 
        
        Het technische team werkt samen met de financiële afdeling om onnodige resources, zoals ongebruikte EC2-instances, te verwijderen.

__Wendbaarheid en voorspelbaarheid:__
        FinOps biedt zowel flexibiliteit als nauwkeurigheid in kostenvoorspelling, zodat bedrijven hun cloudbudgetten nauwkeurig kunnen plannen en aanpassen.
        Voorbeeld: 
        
        Een startup gebruikt historische gegevens en gedetailleerde analyses om de cloudkosten te voorspellen voor de komende drie maanden.

### 4 Elementen van de FinOps Tooling Stack

__Kosten- en gebruiksgegevens:__
         Verzamelen van gedetailleerde gegevens over het verbruik van cloudresources en de bijbehorende kosten.
        Voorbeeld: 
        
        Het gebruik van AWS Cost Explorer om inzicht te krijgen in welke services de meeste kosten genereren.

__Kostenmodellen en budgetten:__
         Het instellen van budgetten en het definiëren van kostenmodellen die organisaties helpen hun uitgaven te beheren.
        Voorbeeld: 
        
        Een bedrijf maakt gebruik van AWS Budgets om budgetlimieten in te stellen voor verschillende teams en ontvangt meldingen wanneer deze limieten bijna worden overschreden.

__Kostenoptimalisatie:__
         Het implementeren van processen en tools die helpen om cloudkosten te optimaliseren door bijvoorbeeld overbodige resources te identificeren.
        Voorbeeld: 
        
        Het gebruik van AWS Trusted Advisor om onbenutte EC2-instances te identificeren en deze automatisch te beëindigen.

__Rapportage en analyse:__
         Het genereren van gedetailleerde rapporten en analyses over cloudkosten om strategische beslissingen te nemen.
        Voorbeeld: 
        
        Het gebruik van AWS Cost Explorer om maandelijkse rapporten te genereren en kosten per afdeling te analyseren.

### 6 FinOps Domains & Capabilities

__Kostenbeheer:__
: Het controleren van cloudkosten en het implementeren van strategieën om uitgaven te verminderen.
        Voorbeeld: 
        
        Een team gebruikt AWS Budgets om het maandelijks budget voor EC2-instances te monitoren.

__Kostenoptimalisatie:__
: Het identificeren van onnodige of niet-gebruikte cloudresources en het optimaliseren van het verbruik.
Voorbeeld: 
        
        AWS Trusted Advisor wordt gebruikt om ongebruikte EBS-volumes te identificeren en deze op te schonen.

__Forecasting:__
: Het nauwkeurig voorspellen van toekomstige cloudkosten op basis van historisch verbruik.
Voorbeeld: 
        
        Een bedrijf maakt gebruik van Cost Explorer om cloudkosten te voorspellen voor de komende maanden en deze op te nemen in hun budgetplanning.

__Cost Transparency:__
: Het creëren van volledige transparantie in cloudkosten door gedetailleerde rapporten en dashboards te bieden.
    Voorbeeld: 
        
        Het gebruik van AWS Cost Explorer om een gedetailleerd overzicht van alle kosten per service te verkrijgen.

__Governance:__
: Het afdwingen van beleid en controles voor het beheren van cloudkosten.
    Voorbeeld: 
        
        Het implementeren van tagging-standaarden in AWS zodat kosten eenvoudig kunnen worden toegewezen aan specifieke projecten.

__Collaboration:__
: Het bevorderen van samenwerking tussen technische, operationele en financiële teams om kosten te beheren.
Voorbeeld: 
        
        Regelmatige vergaderingen tussen het ontwikkelteam en het financiële team om te bespreken welke cloudservices geoptimaliseerd kunnen worden.

### 6 FinOps Principles

__Teams zijn verantwoordelijk voor hun clouduitgaven:__
        : Elke afdeling of team moet verantwoordelijk zijn voor zijn eigen cloudkosten.
        Voorbeeld: 
        
                Het marketingteam beheert de kosten voor hun applicaties, terwijl de IT-afdeling verantwoordelijk is voor de serverkosten.

__Gebruik cloudkosten om zakelijke beslissingen te sturen:__
        : Cloudkosten moeten niet alleen worden gezien als een operationele kostenpost, maar als een strategisch hulpmiddel voor besluitvorming.
        Voorbeeld: 

                Het besluit om een nieuwe feature te bouwen wordt genomen op basis van de kosten-voordelenanalyse van de cloudresources die nodig zijn.

__Beheer cloudkosten met behulp van inzichten en gegevens:__
        : Het analyseren van gedetailleerde kosten- en gebruiksdata om strategische keuzes te maken.
        Voorbeeld: 
        
                Het gebruik van AWS Cost Explorer om inzicht te krijgen in welke services het meest kostenintensief zijn en waar besparingen mogelijk zijn.

__Maak cloudkosten zichtbaar en begrijpelijk voor alle teams:__
        : Transparantie is cruciaal om ervoor te zorgen dat iedereen in de organisatie begrijpt hoe de cloudkosten zich verhouden tot de bedrijfsdoelen.
        Voorbeeld: 
                
                Het maken van visuele dashboards om alle teams te laten zien welke delen van de infrastructuur het meeste kosten.

__Optimaliseer het cloudverbruik:__
        : Het voortdurend optimaliseren van cloudgebruik om onbenutte of inefficiënt toegewezen resources te verminderen.
        Voorbeeld: 
        
                Het beëindigen van onbenutte EC2-instances om kosten te besparen.

__Gebruik een iteratief proces voor kostenbeheer:__
        : Het proces van kostenbeheer moet continu worden geoptimaliseerd en aangepast aan veranderende behoeften.
        Voorbeeld: 
        
                Een bedrijf evalueert elke maand zijn cloudkosten en past het budget aan op basis van veranderende verbruikspatronen.

### AWS Billing Dashboard


Het __AWS Billing Dashboard__ biedt een overzicht van je huidige kosten en het gebruik van AWS-services. Het biedt gebruikers inzicht in hun maandelijkse uitgaven en stelt ze in staat om hun facturering te monitoren.

__Praktische Case__
: Een organisatie gebruikt het AWS Billing Dashboard om de maandelijkse kosten te monitoren en te zorgen dat ze binnen het budget blijven voor hun AWS-omgeving.



__AWS Cost Explorer__
AWS Cost Explorer helpt gebruikers bij het visualiseren van cloudkosten en gebruik. Het biedt gedetailleerde rapporten en filters die helpen bij het begrijpen van kosten, verbruik en trends.

__Praktische Case__

    : Een bedrijf gebruikt AWS Cost Explorer om historische kosten te analyseren en de impact van verschillende services op hun maandelijkse uitgaven te begrijpen.
    CloudWatch Billing Alarms

__4 Eigenschappen__

__Waarschuwingen bij kostenoverschrijding:__
        Voorbeeld: 
        
        Een alarm wordt ingesteld om te waarschuwen wanneer de kosten van EC2-instances boven een bepaald budget komen.

__Gepersonaliseerde drempels:__
        Voorbeeld: 
        
        Het instellen van een alarm voor een specifiek verbruik zoals het aantal S3-opslaadkosten dat de vooraf ingestelde limiet overschrijdt.

__Automatische acties bij overschrijding:__
        Voorbeeld: 
        
        Automatisch stoppen van instances wanneer het geconfigureerde budget is overschreden.

__Meerdere meldingsopties:__
        Voorbeeld: 
        
        Een melding wordt gestuurd via e-mail en SMS wanneer de cloudkosten een bepaalde drempel bereiken.

### EC2 Instances voor FinOps
__Categorieën:__

__On-Demand Instances:__
        : Betaal per uur voor de compute-kracht die je gebruikt zonder langdurige verplichtingen.
        Voorbeeld: Een startup maakt gebruik van on-demand instances voor tijdelijke workloads.

__Reserved Instances:__
        : Betaal vooraf voor een langdurig gebruik van EC2-instances en krijg korting op de kosten.
        Voorbeeld: Een bedrijf koopt reserved instances om kosten te besparen voor continu draaiende workloads.

### 4 Strategieën voor Kostenreductie

__Gebruik Reserved Instances:__
        Voorbeeld: 
        
        Door een driejarige reserved instance te kopen voor een webapplicatie, kan het bedrijf aanzienlijke kortingen krijgen.

__Optimaliseer je EC2-instances:__
        Voorbeeld: 
        
        Door over te schakelen naar kleinere EC2-instances voor piekbelasting, vermindert een bedrijf zijn kosten.

__Gebruik van Spot Instances voor tijdelijke workloads:__
        Voorbeeld: 
        
        Een bedrijf draait batchverwerkingsjobs op spot instances om de kosten aanzienlijk te verlagen.

__Schaal dynamisch op basis van vraag:__
        Voorbeeld: 
        
        Een webapplicatie die automatisch schaling van EC2-instances gebruikt om de kosten te optimaliseren op basis van verkeer.

### AWS Trusted Advisor
__Key Features:__

__Kostenoptimalisatie:__
        Voorbeeld: 
        
        AWS Trusted Advisor helpt bij het identificeren van ongebruikte resources, zoals idle EC2-instances, die je kunt beëindigen om kosten te besparen.

__Beveiligingsaanbevelingen:__
        Voorbeeld: 
        
        Het identificeert beveiligingsconfiguraties die verbeterd moeten worden, zoals onbeveiligde S3-buckets.

__Prestaties en betrouwbaarheid:__
        Voorbeeld: 
        
        Het geeft aanbevelingen voor het verbeteren van de prestaties van jouw infrastructuur, zoals het aanpassen van EC2-instances voor betere prestaties.

__Compliance-controle:__
        Voorbeeld: 
        
        AWS Trusted Advisor helpt bij het waarborgen van naleving van best practices, zoals het versleutelen van gegevens in rust.
## DevOps tools in de cloud

__DevOps__ is een cultuur en een set van praktijken die erop gericht zijn om de samenwerking tussen ontwikkelings- en operationele teams te verbeteren, zodat software sneller en efficiënter kan worden geleverd.

### __Concepten in Continuous Integration (CI) en Continuous Delivery (CD)__
__1. Continuous Integration (CI)__

Continuous Integration is het proces waarbij ontwikkelaars regelmatig (meestal meerdere keren per dag) code integreren in een gedeelde repository. Elke integratie wordt vervolgens geautomatiseerd getest.
    Voorbeeld: 
    

    Ontwikkelaars pushen hun code naar AWS CodeCommit en een geautomatiseerd proces in AWS CodeBuild voert tests uit en meldt de status van de integratie.

__2. Continuous Delivery (CD)__

Continuous Delivery is de praktijk waarbij de geautomatiseerde testen en builds verder worden geautomatiseerd om ervoor te zorgen dat code altijd in een releasebare staat is. Het doel is om code continu naar productie-omgevingen te brengen.
    Voorbeeld: 
    
    Een applicatie is altijd klaar voor productie, en elke keer als een wijziging in AWS CodeCommit wordt gepusht, wordt het door AWS CodePipeline automatisch gepromoot naar een stagingomgeving.

__3. Continuous Deployment__

Continuous Deployment is het proces waarbij elke succesvolle wijziging automatisch naar de productieomgeving wordt gedeployed zonder handmatige tussenkomst.
    Voorbeeld: 
    
    Na elke succesvolle commit naar AWS CodeCommit wordt de code automatisch gedeployed naar de productieomgeving via AWS CodeDeploy.

### __DevOps Culture__
__Eigenschappen van DevOps Culture__

__Samenwerking en Communicatie:__
         DevOps moedigt de samenwerking aan tussen development en operations teams. Dit zorgt ervoor dat beide teams dezelfde doelen hebben en dat communicatie tussen deze teams altijd soepel verloopt.
        Voorbeeld: 
        
        Regelmatige stand-ups tussen ontwikkelaars, testers en operations zorgen ervoor dat iedereen op de hoogte is van de voortgang en eventuele problemen.

__Verantwoordelijkheid:__
         In DevOps zijn zowel ontwikkelaars als operationele teams gezamenlijk verantwoordelijk voor het succes van de software, van ontwikkeling tot productie.
        Voorbeeld: 
        
        Beide teams moeten samenwerken om ervoor te zorgen dat de software efficiënt presteert in productieomgevingen.

__Automatisering:__
         DevOps legt de nadruk op automatisering van handmatige taken zoals testen, builds en deploys, wat leidt tot snellere en betrouwbaardere softwareleveringen.
        Voorbeeld: 
        
        Automatisering van builds en tests via AWS CodeBuild zorgt ervoor dat code snel en betrouwbaar kan worden gepusht naar productie.

### Verschillende DevOps Practices
__1. Automated Testing__

Het uitvoeren van geautomatiseerde tests om ervoor te zorgen dat code voldoet aan de kwaliteitsnormen voordat het naar productie wordt gepusht.
    Voorbeeld: 
    
    AWS CodeBuild draait automatische tests voor elke codewijziging die in AWS CodeCommit wordt gepusht.

__2. Infrastructure as Code (IaC)__

Het beheren van infrastructuur door middel van code, wat zorgt voor herhaalbaarheid, schaalbaarheid en eenvoudiger beheer van omgevingen.
    Voorbeeld: 
    
    AWS CloudFormation wordt gebruikt om alle benodigde AWS-omgevingen (zoals EC2-instances, RDS-databases) in code te definiëren en te beheren.

__3. Continuous Monitoring__

Het voortdurend bewaken van applicaties en infrastructuur om problemen snel op te sporen en te reageren.
    Voorbeeld: 
    
    AWS X-Ray wordt gebruikt om prestaties en foutinformatie van een applicatie in real-time te monitoren en te visualiseren.

__4. Collaboration and Communication__

Het verbeteren van de communicatie en samenwerking tussen teams, wat helpt bij het sneller oplossen van problemen en het versnellen van de softwarelevering.
    Voorbeeld: 
    
    Teams gebruiken chattools zoals Slack om feedback en waarschuwingen van AWS-services snel te ontvangen.

### __Voordelen van DevOps volgens AWS__

__Snellere levering van software:__
         Door het proces van het bouwen, testen en implementeren van software te automatiseren, kunnen teams sneller en efficiënter software leveren.
        Voorbeeld: 
        
        AWS CodePipeline automatiseert het hele CI/CD-proces, zodat software sneller kan worden gepusht naar productie.

__Betere samenwerking tussen teams:__
         DevOps bevordert samenwerking tussen ontwikkeling, operations en andere teams om gezamenlijke doelen na te streven.
        Voorbeeld: 
        
        Ontwikkelaars, operations teams en QA werken samen in de pipeline om code van concept tot productie te brengen.

__Verhoogde efficiëntie:__
         Door automatisering en samenwerking kunnen teams hun tijd en middelen beter benutten.
        Voorbeeld: 
        
        Door de CI/CD-pijplijn van AWS CodePipeline en CodeBuild te automatiseren, hoeven teams zich niet bezig te houden met handmatige taken.

__Betrouwbaardere software:__
         Door geautomatiseerde tests en monitoring kunnen fouten sneller worden opgespoord en opgelost.
        Voorbeeld: 
        
        AWS X-Ray helpt bij het identificeren van prestatieproblemen en fouten in de productieomgeving, zodat ze snel kunnen worden opgelost.

### __5 Fasen van Release en Monitor__
__1. Plan:__

Het plannen van de features en wijzigingen die moeten worden ontwikkeld en uitgerold.
    AWS Service: AWS CodeCommit voor het beheren van broncode.
    Voorbeeld: 
    
    Een team plant nieuwe functies voor hun applicatie en creëert een repository in AWS CodeCommit.

__2. Develop:__

Het ontwikkelen van de software en het schrijven van de code.
    AWS Service: AWS CodeBuild voor het bouwen van de applicatie.
    Voorbeeld: 
    
    Ontwikkelaars schrijven code in AWS CodeCommit, en AWS CodeBuild automatiseert de bouw van de applicatie.

__3. Build:__

Het bouwen van de applicatie en het uitvoeren van geautomatiseerde tests.
    AWS Service: AWS CodeBuild voor build en tests.
    Voorbeeld: 
    
    AWS CodeBuild voert tests uit op de code in AWS CodeCommit om ervoor te zorgen dat alles correct werkt.

__4. Deploy:__

Het implementeren van de software naar de productieomgeving.
    AWS Service: AWS CodeDeploy voor het deployen van applicaties.
    Voorbeeld: 
    
    Na een succesvolle build, gebruikt AWS CodeDeploy om de code naar productieomgevingen te pushen.

__5. Monitor:__

Het bewaken van de prestaties en de gezondheid van de applicatie in productie.
    AWS Service: AWS CloudWatch voor monitoring van de applicatieprestaties.
    Voorbeeld: 
    
    AWS CloudWatch wordt gebruikt om de prestaties van de applicatie in real-time te monitoren en eventuele problemen op te sporen.

### __Vergelijking van AWS CodeBuild en Jenkins__

__AWS CodeBuild:__
        AWS CodeBuild is een volledig beheerde build-service die code bouwt, test en deployt zonder de noodzaak van servers.
        Vergelijking: Het biedt naadloze integratie met andere AWS-services zoals CodeCommit en CodePipeline.
        
__Praktische Case:__
        Een bedrijf gebruikt AWS CodeBuild voor het automatiseren van build- en testprocessen voor hun applicaties.

__Jenkins:__
        Jenkins is een open-source automation server die gebruikt wordt voor Continuous Integration en Continuous Deployment.
        Vergelijking: Jenkins vereist meer handmatige configuratie en beheer van de server, terwijl CodeBuild volledig beheerd wordt door AWS.

__Praktische Case:__
        Jenkins wordt vaak gebruikt in omgevingen waar volledige controle over de serverconfiguratie vereist is, terwijl AWS CodeBuild eenvoudiger is voor teams die geen servers willen beheren.
## Container service in de cloud
## Cloudformation en Automation

