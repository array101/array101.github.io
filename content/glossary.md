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


### System
---

- **CPU Core** - Modern CPUs can be made of multiple cores to facilitate multi-tasking. Each Core is independent. Each core has a frequency specicification (in GHz) which represents how fast it rotates. Higher is better - meaning more computations can be performed in less amount of time.
  - In Unix-like systems, CLI command: `top` can be used to monitor CPU usage. Each core amounts to 100%. If you have 4 cores, all cores are used when CPU usage shows 400%.

- **compiler** - converts source code to executable


### Python
---

- **distutils** - standard system for packaging and distributing Python packages
- **setuptools** (Python package) - built on Python's distutils to provide easier building, distribution and installation of libraries and applications
- **distribution** - File representing an installable library or application. Distributions are usually archives with suffix of .whl, .tar.gz or .zip. Distributions are the target of packaging-related commands such as pip install.
- **entry point** - a setuptools indirection, defined within Setuptools distribution (usually in setup.py or setup.cfg). it's usually a name that refers to a function somewhere in a package which is held by the distribution.



### Miscellaneous
---

- **Augmented Reality** - having virtual things in real space. You can do AR stuff with Unity (Physics/game-dev), Unreal engine

- **SLAM** - Simultaneous Localization And Mapping (used in Reinforcement Learning/Robotics/AR)
