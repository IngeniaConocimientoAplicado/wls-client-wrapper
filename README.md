# Weblogic Client Connector Wrapper

[![N|Solid](http://www.ingenia.la/sites/default/files/ING_Logo%20Positivo-Peq_3.png)](http://www.ingenia.la)

This utility is useful to be able to use Weblogic  client connector in OSGI architecture. The client *wlthint3client* by itself is not OSGI compliant.

# Requirements
- JDK 1.7.x or newest
- Maven 3.x or newest
- OSGI Container (Redhat JBoss Fuse 6.x or newest as an example)

# Build the project

  - Clone the project
```sh
$ git clone https://github.com/IngeniaConocimientoAplicado/wls-client-wrapper.git
```
  - Install weblogic client locally
```sh
$ cd wls-client-wrapper
$ mvn install:install-file -Dfile=./lib/{VERSION}/wlthint3client.jar -DgroupId=com.oracle.weblogic -DartifactId=wlthint3client -Dversion={VERSION} -Dpackaging=jar
```
  - Compile the project
```sh
$ cd wls-client-wrapper
$ mvn clean install
```

# How to use it
  - Add property to your project pom
```sh
	<properties>
		...
		<fabric8.bundles>
            mvn:com.ingenia.utils/wlclient-wrapper/1.0.0-SNAPSHOT
        </fabric8.bundles>
        ...
	</properties>
```
  - Mark package as *Dynamic*
```sh
	DynamicImport-Package: *
```
