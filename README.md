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
