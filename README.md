# Finatra Thrift Server Lightbend [Activator](https://www.lightbend.com/activator/docs) Template

[![Build Status](https://secure.travis-ci.org/twitter/finatra-activator-thrift-seed.png?branch=master)](http://travis-ci.org/twitter/finatra-activator-thrift-seed?branch=master)
[![Project status](https://img.shields.io/badge/status-deprecated-lightgrey.svg)](#status)

A minimal [Activator](https://www.lightbend.com/activator/docs) seed template for creating a Finatra Thrift server application.

### Note:

[Activator](https://www.lightbend.com/activator/docs) has been [deprecated by Lightbend](https://www.lightbend.com/blog/introducing-a-new-way-to-get-started-with-lightbend-technologies-and-saying-goodbye-to-activator) with a scheduled EOL at the end of 2017.

## Quick Start

A simple client implementation

```scala
val client: PingService[Future] = ThriftMux.client
    .withTracer(NullTracer)
    .withStatsReceiver(NullStatsReceiver)
    .newIface[PingService.FutureIface]("localhost:9999")


client.ping().onSuccess { response =>
  println(s"response: $response")
}
```

## Running

Run the server using sbt
```sh
sbt run
```

## License

Licensed under the Apache License, Version 2.0: http://www.apache.org/licenses/LICENSE-2.0
