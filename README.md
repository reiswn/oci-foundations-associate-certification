
# oci-foundations-2021-associate-certification
My personal notes about this certification - OCI Fundation Certification Exam

# Links
- [Oracle Cloud Overview](https://learn.oracle.com/ols/learning-path/oracle-cloud-overview/37192/89873)
- Course : [Oracle Cloud Infrastructure Foundations](https://learn.oracle.com/ols/course/oracle-cloud-infrastructure-foundations/35644/96915/142023)

# Introduction (see [fundamentals-of-oci](https://learn.oracle.com/ols/course/fundamentals-of-oci/37192/89889/130850))
 - **Compute Services**
	- **Bare Metal :** Code ; App container ; Language Runtime ; Operating System ; Virtualization
		- Use when
			- Workloads that are Performance-intensive
			- Workloads that are not virtualized
			- Workloads that require a specific hypervisor
			- Workloads that require BYO (bring your own) Licensing
	- **Dedicated Virtual Hosts :** Code ; App container ; Language Runtime ; Operating System ; ~~Virtualization~~
	- **Virtual Machines :** Code ; App container ; Language Runtime ; Operating System ; ~~Virtualization~~
		- Use when
			- you want to control all aspects of an **environment**
			- you want to deploy a legacy app running on **Windows** or **Linux**
			- you want to move applications from **on-premises** to OCI
		- Require
			- OS patch management
			- Security configuration
			- Monitoring
			- Application configuration
			- Scaling to handle variable traffic
	- **Container Engine :** Code ; App container ; ~~Language Runtime ; Operating System ; Virtualization~~
	- **Functions :** Code ; ~~App container ; Language Runtime ; Operating System ; Virtualization~~
 - **Storage Services**
	 - Requirements
		 - Persistent vs Non-Persisten
		 - Type of Data (database ; videos ; audio ; photos ; text)
		 - Performance (max capacity, IOPS, throughput)
		 - Durability (# of copies of data)
		 - Connectivity (local ; network)
		 - Protocol (block ; file ; http)
	- **Local NVMe :** NoSql ; in-memory db ; Scale-out transactional db ; Data warehousing
		- Flash, low latency (high performance)
		- Locally attached to the compute instances
		- Non-persistent (need to be protected using RAID (1, 6 or 10))
	- **Block Volume :** Databases ; VMFS ; NTFS ; boot and data disks for instances
	- **File Storage :** Oracle apps (EBS), HPC, general purpose file system
		- Hierarchical collection of documents organized into named directories which are themselves structured files
		- Distribuited File Standards: **NFS and SMB**
		- Suported by UNIX and Windows
		- Allow creation, deletion, reading, writing, sharing and locking
		- Supported by all major OS and Hypervisors
		- Provide access over network
	- **Object Storage :** Hot (Standard Storage Tier) : Unstructured data incl. logs, images, videos
		- All data, regardless of content type, is managed as objects
		- Storage in a **Bucket** (logical container for storing objects)
		- Without folder hierarchy (fast and easy access)
		- key-value (metadata - object itself)
		- No need to mount. Relies on standard HTTP verbs.
	- **Archive Storage :** Cold (Archive Storage Tier) Same API of Object Storage : Backups and long term archival (DB backups)
		- Seldom or rarely accesses data but must be retained and preserved for long periods of time
		- 10X cheaper than Standard Tier
		- 90 days minimum retention requirement
		- Objects need to be restored before download ; Time To First Byte (TTFB) after restore request is made: 4 hours
		- Archive Bucket can't be upgraded to Standard storage tier 
 - **Networking**
	- VCN (Virtual Cloud Network)
	- Private or Public
	- Subnets
	- Gateways
		- Internet Gateway: IN and OUT
		- Nat Gateway: only OUT
		- DRG (Dynamic Rounting Gateway): virtual router. Can be used to connect with on-premises network (IPsec VPN / FastConnect)
		- Service Gataway 
	- VCN Security: Stateful or Stateless
	- Peering
		- Remote VCN Peering: different regions
		- Local VCN Peering: same region
	- Load Balancer
		- Service Discovery ; Health Check ; Algorithm
		- Fault tolerance and HA ; Scale ; Naming abstraction (backends dont need public IP addresses)
		- Previsioned banwidth
		- Key features
			- Public or Private
			- Provisioned bandwidth: Flexible Load Balancer
			- Single LB for TCP (layer 4) and HTTP (layer 7) traffic
 - **Identity and Access Management**
 	- OCID: Oracle Cloud Identity
 	- OCI IAM
 		- Identities (Who requests)
 			- Groups
 				- Users (individual people or applications)
 			- Instance
 		- Permissions (What is requested by the idendity)
 			- Policies
 				- Compartments : Collection of related resources. Isolate and control access. Ex.: Compartment Network or Compartment Storage
 					- Resources : can interact with other resources in different compartments
 	- Principals: IAM entity that is allowed to interact with OCI resources
 		- USERS and GROUPS (Users --> Groups --> at least one policy with permission to tenancy or a compartment
 		- INSTANCE (API calls)
 	- Authentication: deals with user identity
 		- OCI IAM service auth a Principal by:
 			- User name, Password
 			- API Signing Key
 			- Auth Tokens
 	- Authorization
 		- Specifies various actions an authenticated Principal can perform
 		- Same that Policies
 			- Are written in human-readable format
 			- Policy Attachment: policies can be attached to a compartment or the tenancy. Where you attach it controls who can then modify it or delete it.
 			- Example
 			```
 				- Allow group NetworkAdmins to manage virtual-network-family in tenancy
 				- Allow group <group_name>  to <verb> <resource-type>        in tenancy | in compartment <compartment_name> [where <conditions>]
				- Allow <subject> to <verb> <resource_type> in <location> where <conditions>
			```
 - **Databases Services**
 	- <= Fast Provisioning ; Fast Performance ; Managed high Avalability ; Managed Exadata infrastructure ; Self-{driving | securing | repairing} =>
 	- VM DB Systems                                 
 	- BM DB Systems
 	- RAC
 	- Exadata DB Systems
 	- Autonomous - Shared     --|
 	- Autonomous - Dedicated  --|--> Auto { back up ; patching ; upgrading ; tuning }
 - **Security**
---
- Gen 2 Exadata Cloud at Customer
	- DaaS in your data center
	- Public cloud hardware, software, and APIs
	- Public cloud operational model
	- Public cloud financial model
	- Seamlessly interoperates with Oracle Public Cloud
- Oracle Roving Edge infrastructure
	- Cloud integrated service that extends the power of cloud and accelerates deployment of cloud workloads outside the data center
	- Oracle REDs - Roving Edge Devices deliver cloud and storage at the edge of networks and in disconnected locations
- OCI Azure Interconnect
- Oracle FastConnect
	- Enables connect directly to their OCI VCN via dedicated, private and high-bandwidth connections
	- Based on data, can choose port speed and pay a consistent, low price each month
	- Dedicated connectivity
	- Dedicated, reliable, and consistent networking experience is required
	- Good for latency-sensitive enterprise applications, sensitive data that cannot traverse the Internet

---
- PAAS
	- OCI Visual Builder Studio
		- Extend Oracle Cloud Applications
	- OCI Analytics Cloud
		- Uses embedded machine learning and artificial intelligence to analyze data across the organizations
---
 - Event Driven Architecture
 - Developer Services
 - Observability & Management
 - Hybrid Capabilities
---
 - Differentiated Pricing
 - SLA
 - Support

# Cloud
- Scaling Horizontal
- Scaling Vertical
- SAAS
	- ERP/EPM: Enterprise Resource Management / Enterprise Performance Management
		- ERP: manages the day-to-day businesses for accounting, procurement, project management, risk management and compliance, and supply chain management
		- EPM: helps you model and plan across finance, HRM, supply chain, and sales, and streamline the financial close process while driving better decisions.
	- SCM: Supply Chain management
	- HCM: Human Capital Management
	- CX: Customer Experience
- IAAS
- PAAS
- CAPEX vs OPEX

# Infrastructure
- Region: Location ; Data Residency & Compliance ; Service Availability
	- A region is a localized geographic area
- Domains
- Compartment
- Available Domains (AD): Physical infrastructures NOT shared; Isolated, fault tolerant
	- Every AD has three FD for high availability.
- Fault Domains (FD): 3 FD / AD ; Logical data center within an AD ; Each FD does not share unique points of hardware failure with the others
	- Fault domains provide anti-affinity: they let you distribute your instances so that the instances are not on the same physical hardware within a single availability domain. A hardware failure that affects one fault domain does not affect instances in other fault domains.

# Storage
- Local NVME
- Block Volume
	- In order to provision a volume to an instance, you need to attach it to the instance.
- File Storage
	- File System organizes files in a hierarchy of named directories.
- Object Storage
	- Object Lifecycle management manages object storage versioning.
- Archive
	- The Archive Storage service is ideal for storing data that is seldom accessed, but requires long retention periods.
- OCI doesn’t have a managed NetApp storage service.

# Cloud Network
- VCN : Virtual Cloud Network
	- Each VCN comes with a **default** set of **route tables**, **security lists** and **DHCP options** with initial values that you can change.
- Subnets
	- You can designate a subnet to exist either in a single availability domain or across an entire region 
- Load Balancer
	- The Load Balancing service provides automated traffic distribution from one entry point to multiple servers reachable from your VCN.
- Gateways
	- Service Gateway
	- NAT Gateway
		- A NAT gateway gives cloud resources without public IP addresses access to the internet without exposing those resources to incoming internet connections.
	- DRG (Dynamic Routing gateway)
	- Internet Gateway
		- An internet gateway allows both inbound and outbound traffic.
# Compute Services
- Oracle Cloud Infrastructure offers both Bare Metal and virtual machine **instances**.
- You can run **containers** in OCI, but the service **doesn’t offer** a managed container instance.
- Once allocated, the **primary private IP** for the instance is not editable.
- **OS management** can be used for automating patches, simplifying package management and managing CVE (Common Vulnerability Exposure)
- **Autoscaling** automatically scales up or down to meet the capacity requirements.

# Security for Cloud
- Cloud Guard
- Vault
	- *Oracle Cloud Infrastructure **Vault*** is a managed service that lets you centrally manage the *encryption keys* that protect your data and the *secret credentials* that you use to securely access resources.
	- **JWA is not** a supported algorithm for OCI Vault service.
- Multi-factor Authentication
	- Multi-factor authentication is a method of authentication that requires the use of more than one factor to verify a user’s identity.
- Web Application Firewall
	- WAF can protect any internet facing endpoint, providing consistent rule enforcement across a customer's applications.
- Security Zone
	-  A security zone is associated with a compartment and a security zone recipe.

# Databases
- VM DB Systems
- Bare Metal
- RAC
	- Two-node *Oracle RAC DB systems* require **Oracle Enterprise Edition - Extreme Performance**.
- MySQL Cloud Service
- NoSQL Cloud Service
	- Provides on demand throughput and storage based provisioning that supports document, columnar, and key value data models all with the flexible transaction guarantee.
	- **NoSQL Database** gives a predictable *single-digit*, millisecond *latency* with *high performance* workloads.
- Autonomous Json DB
- Autonomous Database
	- **Dedicated deployment** is a deployment choice that enables you to provision **autonomous databases** into their own dedicated cloud infrastructure.
	- An **Autonomous Database** handles the creating of the database along with **backups, patching, upgrading, and tuning** of the database.
	- **ATP** is a workload *type* on the **Autonomous Database** and **not** a *DB system*

# App Dev
- Terraform
	- Using Terraform, **Resource Manager** helps you *install, configure, and manage resources* through the *"infrastructure-as-code"* model.
- OCI Container Registry (OCIR)
	- A single registry can only contain either private or public Docker repositories
- Oracle Functions
	- The serverless and elastic architecture of **Oracle Functions** means there's no infrastructure administration or software administration for you to perform.
- OCI Container Engine for Kubernetes
	- is a fully-managed, scalable, and highly available service that you can use to deploy your containerized applications to the cloud.
- OCI API Gateway service
	- You can access the API Gateway service to define API gateways and API deployments using the Console and the REST API.
	- Doesnt provides a deployment plataform for your API implementations

# Observability and Management
- OCI Loggin : Can be used to enable, manage and search critical diagnostic information that describes how resources are performing.
	- Audit Logs
	- Custom Logs
	- Service logs
- OCI Monitoring : enables you to actively and passively **monitor your cloud** resources using the Metrics and Alarms features.
	- Alarms : use metrics for monitoring and consists of a trigger action and notification method.
	- Namespace
	- Triggers
	- Queries
- OCI Logging Analytics

# Analytics and AI
- Data Integration : enables the **ETL** (Extract-Transform-Load) developers to develop, build, and test data integration solutions.
- Data Flow : is used to easily create, share, run, and view the output of Apache **Spark** applications.
- Data Catalog : can harvest technical **metadata** from a wide range of supported data sources that are accessible using public or private IPs.
	- Find the information you need by exploring the data assets, browsing the data catalog, or using the quick search bar.
- Data Science
	- Accelerated Data Science SDK : Oracle Accelerated Data Science (ADS) SDK is a Python library that is included as part of the OCI Data Science service.
# Billing
-
#
-
