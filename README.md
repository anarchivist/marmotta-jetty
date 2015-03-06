# marmotta-jetty

This is a copy of Jetty bundled with Apache Marmotta and Apache Solr.

* [Marmotta](http://marmotta.apache.org)
* [Solr](http://lucene.apache.org/solr/)

This project is based upon [hydra-jetty](https://github.com/projecthydra/hydra-jetty), a distribution of Jetty, Solr, and Fedora developed by the Hydra project.

## Included Versions

* jetty: 8.1.16
* solr: 4.10.3
* marmotta: 3.3.0

## Usage

### Dependencies

* [Java 7 (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)

### Manual
  
    git clone https://github.com/dpla/marmotta-jetty
    cd marmotta-jetty
    java -jar start.jar

You can also change the port jetty starts on by editing the file etc/jetty.xml and changing this line to indicate a different port number:

    <Set name="port"><SystemProperty name="jetty.port" default="8983"/></Set>

### Using jettywrapper

jettywrapper is a Ruby gem that provides convenient Rake tasks to start and stop Jetty and its deployed applications. For use within your application's Rails directory.

    rake jetty:install
    rake jetty:start

See [jettywrapper](https://github.com/projecthydra/jettywrapper) for more information regarding configuration and usage.
Port numbers and other java options may be configured via the gem. 
    
### Interaction

When jetty is finished initializing itself, Solr is available at 

* [http://localhost:8983/solr/](http://localhost:8983/marmotta/)

and Marmotta is available at

* [http://localhost:8983/marmotta/](http://localhost:8983/marmotta/)

You can see a list of all installed applications at

* [http://localhost:8983](http://localhost:8983)

### Updating

#### Solr and Jetty

Solr is updated by downloading the latest from [Lucene](http://lucene.apache.org/solr/), which includes an instance of Jetty in the
`example` directory.  Updating is a process of replacing the jar files as well as the solr.war and start.jar files.  Note that the
example from Lucene does not include the start.ini file.

#### Marmotta

Marmotta provides a packaged WAR file for distribution. A built WAR file using Marmotta's [installation from source instructions](http://marmotta.apache.org/installation.html#source) can be used to replace the provided `marmotta.war` file.
