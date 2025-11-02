## Deployment topology
**Is an arragement or configuration of :**
- Hardware
- Software
- Network components
**Depend on:** 
- Scalability
- Performance 
- Reliability
- Nature of the application
Common deployment topologies
- Single-tier architecture
	- Deploys all components on a single server 
	- Operates with in the same environment 
- Client-server architecture or two-tier 
	- Divides the application into two distinct layers 
	1. Client layer: Responsible for user interface
	2. Server layer: Manages the application logic 
	- The remote server host the database
	- The user access it from client system 
	![[2-tier architecture.png]]
	-> Database Server (DBMS) include
		Data access layer: Interfaces **communicate** with the server through [[APIs]] and have various client interface
		Database engine layer : Compile queries, Retrieve/Process data 
		Database storage layer 
- Three-tier architecture 
	- Introduce a middle tier between client and server
	- Benefits : 
		- Security: Prevent unauthorized data access or modification
		- Performance: Avoid overload traffic to the database
		- Maintainability: Avoid making changes to data except administrators
![[tier3-architecture.png]]
## Cloud deployment
Definition : 
- Involve residing the database within a cloud
- Offer many advantages inherent to cloud-based services
- Eliminates the need to download database software locally 
Advantage: 
- Easily to access with internet
- Involve communication between database server and application server only in cloud environment
![[cloud.png]]