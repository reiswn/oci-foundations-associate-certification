
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
	- **Block Volume :** 
	- **Local NVMe :** 
		- Flash, low latency (high performance)
		- Locally attached to the compute instances
		- Use cases: NoSql ; in-memory db ; Scale-out transactional db ; Data warehousing
		- Non-persistent (need to be protected using RAID (1, 6 or 10))
	- **File Storage :** 
		- Hierarchical collection of documents organized into named directories which are themselves structured files
		- Distribuited File Standards: **NFS and SMB**
		- Suported by UNIX and Windows
		- Allow creation, deletion, reading, writing, sharing and locking
		- Supported by all major OS and Hypervisors
		- Provide access over network
	- **Object Storage :** Hot (Standard Storage Tier)
		- All data, regardless of content type, is managed as objects
		- Storage in a **Bucket** (logical container for storing objects)
		- Without folder hierarchy (fast and easy access)
		- key-value (metadata - object itself)
		- No need to mount. Relies on standard HTTP verbs.
	- **Archive Storage :** Cold (Archive Storage Tier) Same API of Object Storage
		- Seldom or rarely accesses data but must be retained and preserved for long periods of time
		- 10X cheaper than Standard Tier
		- 90 days minimum retention requirement
		- Objects need to be restored before download ; Time To First Byte (TTFB) after restore request is made: 4 hours
		- Archive Bucket can't be upgraded to Standard storage tier 
 - **Networking**
 - **Identity and Access Management**
 - **Databases Services**
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
