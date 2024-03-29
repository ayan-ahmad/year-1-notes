## Structure and Nature of the Application
- The hypertext/link structure means there is a need to
	- avoid user disorientation and cognitive overload
	- provide multiple paths to support users with different requirements
	- provide a good superstructure include search facilities, site map, and guided tours
- The presentation and user interface must be
	- self-explanatory with no user manuals for web sites!
	- aesthetically pleasing and adaptable to different contexts
- Content delivery must be
	- fast, up-to-date, consistent and reliable
	- secure - particularly for financial transactions
	- adaptable to different contexts in terms of how much can be delivered
## Users and Usage
- Users expect immediate and fast availability
- They also expect permanent availability
- They also expect access on a variety of devices – quality of service becomes an issue
- They have a very diverse background culturally and linguistically
- They have a low tolerance threshold for slow or hard to use sites
- There may be lots of users so plan accordingly
## Development Process
- The nature of the developers
	- Professional development is by a multidisciplinary team
	- Much development is by amateurs or inexperienced programmers
	- Development can be communal by a geographically distributed group
- The development environment consists of
	- a wide variety of technologies, each programmed differently
	- many of the technologies are immature but some are legacy
	- each of the technologies has multiple competing products and upgrades to the site often mean a change of product
- The development process
	- follows no accepted internet application development methodologies
	- must be flexible and not rigid
	- Parallel development of components (and even versions) is necessary
	- Agile processes seem valuable here
### Waterfall
### Agile
## Types of Web Apps
### Static
Originally web applications were just collections of hand-built HTML pages which required manual updates and introduced the possibility of inconsistency
### Interactive
Forms, selection menus and radio buttons on web pages offer the possibility of selectively chosen pages generated by server-side programs
### Transactional
Forms also offer the capture of data and database storage at the server; although the data management may be separated from the internet server
### Workflow-based
Support for functionality expressed as a sequence of pages reflecting a business process – For instance, booking a flight
### Portal Oriented
One point of access is given to multiple web sites for example, Virtual Shopping malls
### Collaborative
Web sites which permit multiple users to share information management for example, Wikis such as Wikipedia
### Social Web
Many sites provide a focal point for communities for example, Photo sharing sites, Facebook, etc.
### Mobile and Ubiquitous
“Web” applications increasingly provide access by small, mobile and nonvisual devices (i.e., phones) as well as data capture by sensors
## System Architectures
Every component of a system must be designed

The architecture of the system shows the blueprint or plans of how each component fits together.

Architectural diagrams can be at various levels
- Data structure / algorithm / object level
- Component / library level
- Application level

Various diagrams are needed, for this we will be focusing on high-level system architecture
### Monolithic
The main tasks that any application must support:
- user interface management
- the implementation of algorithms – the business logic
- information manipulation - data storage
A monolithic program in Java does all of these: 
- user interface with Swing or JavaFX 
- algorithms in methods 
- information manipulation in methods, e.g. sort methods - data storage using File I/O
### Tiered
The structure of applications have changed from:
- Monolithic programs as a single unit in which every aspect of the application is coded, to
tiered structures in which different aspects are separated into different levels
The advantage of the tiered architectures are
- Each tier can be coded separately without one programmer having to deal with
everything
- The different tiers can be distributed over the network leading to increased efficiency
But the tiers must interact effectively
- There must be well defined interface between adjacent tiers
- Internet protocols and database connection software do this well
### Single Tier
![[Single.png]]
### Two Tier
#### Data Management
It is difficult/time-consuming to write the code which accesses large amounts of data efficiently

Solution: Separate the concerns
- Let a Database System handle the data management
- And then use a Client application to interact with the database:
	- The client acts like a database user sending in queries and updates and making use of the result
	- Simple way to do this by coding SQL statements as strings inside the program
#### Fat Client
This then is the standard architecture for getting an application (e.g. Java-based) to work on top of a database.
![[Thin.png]]
#### Thin Client
This is the standard architecture for serving up static content on the web
![[Fat.png]]
## Middleware
## Load balancing

