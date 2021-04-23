+++
title = "Glossary"
slug = "glossary"
template = "glossary.html"
draft = false
[taxonomies]
tags = []
+++

### Data
---

- **BLOB** - Binary Large OBject - collection of binary data stored as a single entity. Usually used to store images, audio, etc. Also used by some databases like PostgreSQL, MongoDB to store persitent values.

- **SRID** - Spatial Reference IDentifier - It defines what coordinate system you want to use. There are many SRIDs used for different geographies around the world. To perform geospatial functions on the same data, it has to be on the same SRID. A common one is SRID 4326 (maps to WGS84). You can store SRID data in different formats: WKT (commonly used), WKB, HEX
  - WKT (Well Known Text) is a text markup language used by Open Geo Consortium

- **TOML** - Tom's Obvious Minimal Language - Tom Preston Weiner's simple format for specifying software configuration. Examples: Cargo.toml (cargo -Rust), pyproject.toml (poetry - Python)

### Date/Time
---

- **DST** - Daylight Savings Time - happens when a country/region decides to wind their clocks forward one hour to make most of the available sunlight.

- **UTC** - Universal Time Coordinated - coordinated time scale maintained universally. Also known as "Z time" or "Zulu Time". It refers to time on the zero or Greenwich meridian, which is not adjusted to reflect changes either to or from Daylight Saving Time. So, the switch to daylight saving time does not affect UTC. Prior to 1972, this time was called Greenwich Mean Time (GMT). Always use UTC to store, pass around datetime objects.

### Web
---

- **SSL** - Secure Sockets Layer - Protocol for web browsers and servers that allows for the authentication, encryption and decryption of data sent over the Internet.

- **TLS** - Transport Layer Security - successor protocol to SSL. TLS is an improved version of SSL. It works much the same way as the SSL, using encryption to protect the transfer to data and information. SSL certficates work with both SSL and TLS protocols.

- **sessions** - non-permanent data to represent a user's interaction with a web application

- **graphQL** - a language-independent query language - meaning it can be used with any language and any database system. It exposes a single endpoint for *Queries* (does job of REST API's GET) and *Mutations* (does job of REST API's POST, PUT, PATCH, DELETE)

- **SSL certificate** - Server certificate that enables authentication of the server to the user, as well as enabling encryption of data transferred between the server and the user. SSL certificates are issued by Certificate Authorities like DigiCert, Letsencrypt.

- **DNS** - collection of rules and records which helps clients understand how to reach a server through URLs. It routes clients to final addresses. DNS operates on port 53. Most common DNS records are:
  - A record (Address Record) - maps URL to IPv4 address
  - AAAA record - maps URL to IPv6 address
  - CNAME (Canonical Records) - maps URL to URL - use it for non-root domain (Ex: backend.lorem.com)
  - Alias - maps URL to an alias (Ex: AWS resource in Route53 - ELB, CloudFront distribution or S3 bucket sites)
  - MX Record (Mail Exchange Record) - specifies mail server responsible for accepting email messages on behalf of a domain name.

### System
---

- **CPU Core** - Modern CPUs can be made of multiple cores to facilitate multi-tasking. Each Core is independent. Each core has a frequency specicification (in GHz) which represents how fast it rotates. Higher is better - meaning more computations can be performed in less amount of time.
  - In Unix-like systems, CLI command: `top` can be used to monitor CPU usage. Each core amounts to 100%. If you have 4 cores, all cores are used when CPU usage shows 400%.

- **compiler** - converts source code to executable

- **Docker Engine** - referred to a Host with Docker installed on it. Docker Engine has 3 components: Docker daemon, REST API server, Docker CLI.

- **Docker Registry** - repository for hosting docker images. DockerHub is the Docker Registry but you can also spin up your own docker registry.

- **Container Orchestration** - set of tools and scripts that helps in hosting containers in live environment that can easily scale up or down when required. Some popular orchestration solutions are: Docker Swarm, Kubernetes (feature rich), Apache MESOS

### Cloud
---

- **AWS - AMI** - Amazon Machine Image - A base VM image used for booting EC2 instances in AWS. Several Linux and Windows AMIs are available in AWS but you can also create your own custom images.

- **AWS - Security Groups** - acts as Firewall to EC2 instances and regulates access to ports and IP addresses

- **AWS - CloudFormation** - Declarative way of outlining your AWS Infrastructure. Facilitates Infrastructure as Code - all infrastructure changes are version controlled and no resources are manually created.

- **load balancer** - A gatekeeper component used for spreading application load across multiple downstream instances and exposing a single point of access (DNS) to the application.

- **CIDR** - Classless Inter-Domain Routing - method for allocating a range of IP addresses. CIDR has 2 components:
  - *Base IP* (`192.168.0.0`) - represents the first IP contained in the range
  - *Subnet mask* (`/24` <=> `255.255.255.0`) - represents how many bits can change in the IP - smaller the subnet mask, the more IPs you'll have in the CIDR range. `/32` allows 1 IP, `/31` allows 2 IPs, `/30` allows 4 IPs, ... `/0` allows all IPs

  Ex: `192.168.0.0/24` means you can go from `192.168.0.0 - 192.168.0.255` (256 IPs)

### Python
---

- **distutils** - standard system for packaging and distributing Python packages
- **setuptools** (Python package) - built on Python's distutils to provide easier building, distribution and installation of libraries and applications
- **distribution** - File representing an installable library or application. Distributions are usually archives with suffix of .whl, .tar.gz or .zip. Distributions are the target of packaging-related commands such as pip install.
- **entry point** - a setuptools indirection, defined within Setuptools distribution (usually in `setup.py` or `setup.cfg`). it's usually a name that refers to a function somewhere in a package which is held by the distribution.



### Miscellaneous
---

- **Augmented Reality** - having virtual things in real space. You can do AR stuff with Unity (Physics/game-dev), Unreal engine

- **SLAM** - Simultaneous Localization And Mapping (used in Reinforcement Learning/Robotics/AR)
