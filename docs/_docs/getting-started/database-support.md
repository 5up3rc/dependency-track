---
title: Database Support
category: Getting Started
chapter: 1
order: 5
---

Dependency-Track includes an embedded H2 database enabled by default. The intended purpose of this 
database is for quick evaluation, testing, and demonstration of the platform and its capabilities. 

> The embedded H2 database is not intended for production use.

To change database settings, edit `application.properties` found in the Dependency-Track data directory.

The following parameters can be customized:
* alpine.database.mode
* alpine.database.url
* alpine.database.driver
* alpine.database.driver.path
* alpine.database.username
* alpine.database.password


#### MySQL Example

For MySQL, it is necessary to remove 'NO_ZERO_IN_DATE' and 'NO_ZERO_DATE' from the sql-mode prior
to creating the Dependency-Track database. Refer to the MySQL documentation for details.

```ini
alpine.database.mode=external
alpine.database.url=jdbc:mysql://localhost:3306/dtrack?autoReconnect=true&useSSL=false
alpine.database.driver=com.mysql.jdbc.Driver
alpine.database.driver.path=~/path/to/mysql-connector-java-5.1.45-bin.jar
alpine.database.username=dtrack
alpine.database.password=password
```