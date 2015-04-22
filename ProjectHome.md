
---

# WE MOVED TO GITHUB #
Find us here: https://github.com/dana-i2cat/netconf4j
# CODE IN THIS REPO IS OUTDATED #

---




# Project #

A simple, from scratch implementation of the Netconf protocol. We are currently testing the current code base in order to release a beta version with basic functionality. See roadmap for more details and things to come.

Contributors are welcomed!

## Features ##

  1. Low, atomic dependencies (commons-logging, commons-configuration, commons-io, junit, ganymed-ssh2).
  1. OSGi ready.
  1. Test coverage.
  1. Support for both sync and async calls.
  1. Maven based, easy to build & contribute.
  1. Efficient (SAX based) parsing.
  1. Transport abstraction (currently, SSH and Virtual).
  1. This is an RPC only implementation. Configuration data passed to user untouched.

## Roadmap ##

  1. Fully support base Netconf (RFC4741) with all its capabilities.
  1. Support for events (RFC5277) and SOAP transport (RFC4743).
  1. Add vendor (i.e. Juniper) specific capabilities utils project.

## Usage ##

See how to checkout the code [here](http://code.google.com/p/netconf4j/source/checkout).

Will as usual. Both maven2 and maven3 should work:

```
cd netconf-read-only/
mvn install
```

Alternatively, if any test fail but you want to build anyway, try:

```
cd netconf-read-only/
mvn install -DskipTests
```

The produced jar can now be found in the target directory and at your .m2 local repo.

For importing the produced jar in your maven project use:

```
<dependency>
    <groupId>net.i2cat.netconf</groupId>
    <artifactId>netconf4j</artifactId>
    <version>0.0.2</version>
</dependency>
```

From java, you can open a netconf session with:

```
sessionContext = new SessionContext();
sessionContext.setURI(new URI(System.getProperty("net.i2cat.netconf.test.transportUri", "mock://foo:bar@foo:22/okServer")));

session = new NetconfSession(sessionContext);
session.connect();

```

For the library interface check:

  * INetconfSession [here](https://code.google.com/p/netconf4j/source/browse/trunk/src/main/java/net/i2cat/netconf/INetconfSession.java).
  * SessionContext [here](http://code.google.com/p/netconf4j/source/browse/trunk/src/main/java/net/i2cat/netconf/SessionContext.java).
  * The RPC objects [here](https://code.google.com/p/netconf4j/source/browse/trunk/src/main/java/net/i2cat/#i2cat%2Fnetconf%2Frpc).

Some usage examples can be found at:

  * The JUnit tests inside the library [here](http://code.google.com/p/netconf4j/source/browse/trunk/src/#src%2Ftest%2Fjava%2Fnet%2Fi2cat%2Fnetconf%2Ftest).
  * The OpenNaaS protocol bundle [here](https://github.com/dana-i2cat/opennaas/tree/master/extensions/bundles/protocols.netconf).

## Origin ##

This project is a spin-off of the Manticore 2 and Mantychore FP7`*` projects. See http://www.mantychore.eu/about/ for further details.

Mantychore FP7 project is funded by the European Commission.

## Contact ##

Mail { user | dev } @ lists.opennaas.org for further information.