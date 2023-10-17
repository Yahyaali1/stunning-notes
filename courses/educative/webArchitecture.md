Layer: Code Level 

Tier: Physical Separation 

____
Single Tier Application 
Multiple Tier Application 
Three Tier Application 




Both of these can be on at any level. Eg service etc 


Single Responsibility Principle 
    -Example database to take care of only persisting data

Separation of Concerns
- Separation of concerns loosely means the same thing, be concerned about your work only and stop worrying about the rest of the stuff.
  

### Web Architecture

Server and Client 

### Client 

Thin: Has UI 

Thick: Has logic as well 


### Communication protocol 

REST 
- Without State

Http Pull
-   Request server for infromation all the time 
-   Ajax small polling 
  
HTTP push
- Server send information after initial request
  There are multiple technologies involved in the HTTP PUSH-based mechanism, such as:
- Ajax Long polling
  - Hold response and send update if available eg 1-2 sec timeout 
- Web Sockets
  - Client and Server both should support it 
  - 
- HTML5 Event Source
  - One way communication 
  - server send html events ? Q:
- Message Queues
- Streaming over HTTP
  - Like video and images
- We’ll go over all of them in detail up next.

### Scalability
https://scaleyourapp.com/ 

Scalability means the application’s ability to handle and withstand increased workload without sacrificing performance.

### Latency 
- Response Time 
  - Network and Application 

### Scaling 
- Vertical 
- Horizontal
  - Load balancing 
  - Need to manage static instances in server X 
  - Server needs to be stateless 


### Potential Bottle Necks 
- Databases
- sequential tasks 
- Not cached responses 
  
### How to identify and fix 
- **Identify events for large loads** 
- Profiling 
  - Code and Application 
- Caching 
  - All static content
- CDN 

### Parameters of load testing 
- CPU usage
- Network bandwidth consumption
- Throughput
- Number of requests processed within a stipulated time
- Latency
- Memory usage of the program
- End-user experience when the system is under heavy load and so on.

Examples 
https://engineering.fb.com/production-engineering/how-production-engineers-support-global-events-on-facebook/

https://scaleyourapp.com/how-hotstar-scaled-with-10-3-million-concurrent-users-an-architectural-insight/

### Fault Tolerant Systems 

- That can take hits yet withstand it 

Remedies

All the possible components having a single point of failure are made redundant to ensure the availability of the service.

- Standby systems 
  - Multiple remedies to single point of failure 
- Geographical Distribution 
- Automatic Load Distribution in case of a failure 

### Load balancing 

Distribution and Monitoring at multiple levels tiers 

- Helps with
  - Availability 
  - Replication
  - Prevention of bottleneck 

DNS load balancing and inexpensive alternative to load balancers on all services

- Hardware Load Balancing 
  - Hard to manage 
  - Effective 
- Software Load Balancing 
  - Software load balancers are pretty advanced compared to DNS load balancing. They consider many parameters such as data hosted by the servers, cookies, HTTP headers, CPU and memory utilization, load on the network, etc., to route traffic across the servers.

Techniques for Load Balancing 
  
  - Hashing IP
  - Round Robin
  - Least common used 

### Monolithic architecture
- Tightly coupled code and infrastructure 
  - Not cloud-ready, hold state
  - Cannot leverage heterogeneous technologies
  - Scalability issues
  - Single points of failure
  - Regression testing
  - Continuous deployment

### Micro Services 
- Loosely Coupled services 
  
Also, every microservice ideally has a separate database. This eliminates single points of failure and system bottlenecks.
- No Single Points of failure
- Independent and continuous deployments

Q: When micro services ?

case studies: 
- https://segment.com/blog/goodbye-microservices/
- https://segment.com/blog/goodbye-microservices/
- https://blog.christianposta.com/microservices/istio-as-an-example-of-when-not-to-do-microservices/ 


### Micro Frontends 
- Using particular service 
- Generally for very large applications 
- Can be completely client or server side rendered (iframes)
- It is recommended to use SPA for integrations

case studies:
- https://engineering.atspotify.com/2014/03/spotify-engineering-culture-part-1/ 
- https://www.youtube.com/watch?v=m32EdvitXy4&ab_channel=code.talks%28ehem.DeveloperConference%29 

___
### DataBases
Case studies: 
1. https://scaleyourapp.com/what-database-does-facebook-use-a-1000-feet-deep-dive/
2. https://www.quora.com/Why-does-Quora-use-MySQL-as-the-data-store-instead-of-NoSQLs-such-as-Cassandra-MongoDB-or-CouchDB-Are-they-doing-any-JOINs-over-MySQL-Are-there-plans-to-switch-to-another-DB 
3. 

Structured
- Can be normalized

Unstructured 
- any and everything for data analytics 

Semi Structured
- Json and Xml Stored 

### When do relational databases ? 

- ACID properties are required
- They are tested over several years now 

### When do NOSQL database ?

- Eventual Consistency 
- Data analytics 
- Large reads & writes

### polyglot persistence 

Solution with multiple database working at the same time 

Key-value store 
Wide Column 
ACID transactions and strong consistency
Graph database


### Document Store 

Case Studies: 
- https://www.mongodb.com/blog/post/sega-hardlight-migrates-atlas-simplify-ops-improve-experience-mobile-gamers 
- https://www.wix.engineering/post/how-we-re-able-to-host-1-million-sites-per-mongodb-cluster 
  

Pick a document-oriented data store if:

- You are working with semi-structured data and need a flexible schema that will change often.
- You aren’t sure about the database schema when you start writing the app, there is a possibility that things might change over time and you need something flexible that you could change over time with minimum fuss.
- You need to scale fast and stay highly available.
- Typical use cases of document-oriented databases include: Real-time feeds
Live sports apps
Writing product catalogues
Inventory management
Storing user comments
Web-based multiplayer games

### Graph Database

- For maintaining complex relations 

Case Studies: 

- https://www.uber.com/en-IN/blog/uber-eats-graph-learning/ 
- https://neo4j.com/blog/walmart-neo4j-competitive-advantage/ 
- https://neo4j.com/blog/david-meza-chief-knowledge-architect-nasa/ 
  

### Key value 

If you have a use case where you need to fetch data real fast with minimum fuss, you should pick a key-value datastore.

Key-value stores are built to serve use cases that require super-fast data fetch.

Case studies
- https://blog.twitter.com/engineering/en_us/topics/infrastructure/2017/the-infrastructure-behind-twitter-scale
- 
Typical use cases of a key-value database are:

Caching
Persisting user state
Persisting user sessions
Managing real-time data
Implementing queues
Creating leaderboards in online games and web apps
Implementing a pub-sub system 

### Time series 

Storing data over a period of time. 

case Studies: 
- https://www.uber.com/en-IN/blog/m3/ 
- https://www.youtube.com/watch?v=W_Sp4jo1ACg&ab_channel=DataCouncil 

### Wide column 

case studies 
- https://netflixtechblog.com/aegisthus-a-bulk-data-pipeline-out-of-cassandra-984882557fa


### Cache 
- Db or IO calls replaced with in memory solution 
  
Dynamic Data 
- With Time to live. 

Static Data 
- static images etc 

Strategies 
- Cache aside (Read heavy)
  - Fetch on cache miss 
- Read Through 
  - Keeping cache updated to db
- Write Through
  - Everything goes through cache to db 
- Write Back 
  - Written in cache first, then  in db 


### Message Queues 

Message from one end to another. Allows async behavior. 

FIFO: First one and first out 

Case studies

Publish-subscribe model
Messages are broadcasted to subscribers 1:n 

Point to point 
1:1 
- https://scaleyourapp.com/linkedin-real-time-architecture-how-does-linkedin-identify-its-users-online/ 


Managing Streams with cache 

https://engineering.fb.com/2015/12/03/ios/under-the-hood-broadcasting-live-video-to-millions/ 

