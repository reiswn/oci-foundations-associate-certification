
# oci-foundations-2021-associate-certification
My personal notes about this certification - OCI Fundation Certification Exam


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
 		- OCI IAM service auth a Principal by
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
- IAAS
- PAAS
- CAPEX vs OPEX

# Infrastructure
- Region: Location ; Data Residency & Compliance ; Service Availability
- Domains
- Compartment
- Available Domains (AD): Physical infrastructures NOT shared; Isolated, fault tolerant
- Fault Domains (FD): 3 FD / AD ; Logical data center within an AD ; Each FD does not share unique points of hardware failure with the others

# Storage
- Local NVME
- Block Volume
- File Storage
- Object Storage
- Archive

# Cloud Network
-
# Security for Cloud
- Cloud Guard
- Vault

# Databases *
- VM DB Systems
- Bare Metal
- RAC
- MySQL Cloud Service
- NoSQL Cloud Service
- Autonomous Json DB
# Billing
-
#
-
