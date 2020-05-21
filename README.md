# Welcome to MS SQLServer DB support for Liferay CE 7.3.1 GA2

## 1. Build project
Requirements for build project
1. Sun/Oracle JDK 1.8
2. Maven 3.x (for build project) or Gradle 2.x

The driver that adds support for SQL Server database is a jar (**liferay-portal-sqlserverdb-support-${version}.jar**) which then will be installed in ROOT/WEB-INF/lib (for apache tomcat).

To generate the driver for SQL Server database just follow the instructions below.

You can download the binary jar [liferay-portal-sqlserverdb-support-1.0.1-SNAPSHOT.jar](https://github.com/amusarra/liferay-portal-sqlserverdb-support/releases/download/v1.0.1/liferay-portal-sqlserverdb-support-1.0.1-SNAPSHOT.jar), by doing so you can avoid doing the build.

```
$ git clone https://github.com/amusarra/liferay-portal-sqlserverdb-support.git
$ cd liferay-portal-sqlserverdb-support
$ mvn package
```

the build process create the jar inside the (maven) target directory:

```
liferay-portal-sqlserverdb-support-1.0.1-SNAPSHOT.jar
```

If you have a Gradle build system, then you can build jar by the following command

```
$ git clone https://github.com/amusarra/liferay-portal-sqlserverdb-support.git
$ cd liferay-portal-sqlserverdb-support
$ gradle build
```

the build process create the jar inside the build/libs directory.

## 3. Install Liferay CE 7 on Microsoft SQLServer Database

To install Liferay on SQLServer you must have previously configured a schema for Liferay on an SQLServer instance (including SQLServer Express Edition).

I have used an SQLServer Express 2014 installation on Windows 8.1 created on the fly on VirtualBox.

The parameters of my SQLServer instance are:
* Username: liferay
* Password: liferay12345
* DB Name: liferayce7
* FQDN: sqlserverdb.vm.local (IP: 192.168.56.101)
* TCP/IP Port: 1433
* Instance ID: SQLEXPRESS


```
##
## Admin Portlet
##
    #
    # Configure email notification settings.
    #
    admin.email.from.name=Joe Bloggs
    admin.email.from.address=test@liferay.com

##
## JDBC
##

    #
    # SQL Server
    #
    jdbc.default.driverClassName=com.microsoft.sqlserver.jdbc.SQLServerDriver
    jdbc.default.username=liferay
    jdbc.default.password=liferay12345
    jdbc.default.url=jdbc:sqlserver://sqlserverdb.vm.local;databaseName=liferayce7

##
## Liferay Home
##
    #
    # Specify the Liferay home directory.
    #
    liferay.home=/opt/liferay-ce-portal-7.0-ga4

##
## Setup Wizard
##
    #
    # Set this property to true if the Setup Wizard should be displayed the
    # first time the portal is started.
    #
    setup.wizard.enabled=false
```

![Liferay CE 7 GA1 on SQLServer DB ](https://www.dontesta.it/wp-content/uploads/2014/02/Liferay7CEOnSQLServerDB.png)

![Liferay CE 7 GA1 on SQLServer DB ](https://www.dontesta.it/wp-content/uploads/2014/02/Liferay7CEOnSQLServerDB_1.png)
