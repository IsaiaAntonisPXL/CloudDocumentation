# Cloud samenvatting

## opfrissing cloud concepten

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
    Use case: Het kiezen van een regio dicht bij klanten om snellere responstijden te realiseren.

#### 2. Availability Zones (AZs)

Een regio bevat meerdere AZ's, die bestaan uit afzonderlijke datacenters met eigen stroom, koeling en netwerk. Ze zijn ontworpen om onafhankelijk te zijn, maar ook om met elkaar te communiceren via snelle verbindingen.

In eigen woorden: Een AZ is een cluster van datacenters in een regio. Het gebruik van meerdere AZ's zorgt ervoor dat je applicatie online blijft, zelfs als een van de zones faalt.

__Voorbeeld__:

    Een applicatie die gebruikmaakt van meerdere AZ's in de US East (N. Virginia) Region om downtime te voorkomen.
    Use case: Het draaien van een database in twee AZ's met automatische failover voor hoge beschikbaarheid.

#### 3. Edge Locations

Edge-locaties zijn datacenters die zich dicht bij eindgebruikers bevinden en worden gebruikt door AWS-diensten zoals Amazon CloudFront. Ze verbeteren de prestaties van applicaties door content dichter bij de gebruiker te brengen.

In eigen woorden: Dit zijn datacenters verspreid over de hele wereld die zorgen voor snelle levering van content zoals websites, video's en API's.

__Voorbeeld__:

    Een streamingplatform maakt gebruik van een edge-locatie in Tokyo om video's met lage latency te leveren aan kijkers in Japan.
    Use case: Een internationaal bedrijf gebruikt edge-locaties om een wereldwijd publiek snel toegang te bieden tot statische en dynamische content.
