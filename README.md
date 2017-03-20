[<img src="https://img.shields.io/travis/playframework/play-scala-starter-example.svg"/>](https://travis-ci.org/playframework/play-scala-starter-example)

# Benchmark data rest api.

This is a simple rest api application derived from play scala started application. IT is used for storing benchmark data in a mongodb collection. The initial plan is to store only tpcds data, every benchmark will have its own data.

## Prerequisites.

Install mongo db. Configure the web application to connect to mongo db by ernsuring right host and port for the following lines.
```
mongodb.uri = "mongodb://localhost:27017/dashboard"
```

## Running

Run this using [sbt](http://www.scala-sbt.org/). You'll find a prepackaged version of sbt in the project directory:

```
sbt run
```

And then go to http://localhost:9000 to see the running web application.

There are several demonstration files available in this template.

## Controllers
The controllers from the play started application are not deleted. The main functionality for the benchmark related function is in

- TpcdsController.scala
  Has two api's implemented
  1) GET  /api/t_benchmarks
  2) POST /api/t_benchmark
  Example 
  ``` 
  $ curl -i -X POST -H "Accept: application/json" -H "Content-Type: application/json" -d '{ "name" : "TPCDS", "git_url" : "https://github.com/apache/spark", "last_commit" : "1472cac4bb31c1886f82830778d34c4dd9030d7a", "date" : "2016-03-15T18:25:43.511Z", "master" : "10.20.3.144", "workloads" : [ { "name" : "q1", "metrics" : [ { "name" : "executionTime", "value" : "400" }, { "name" : "setupTime", "value" : "400" } ] }, { "name" : "q2", "metrics" : [ { "name" : "executionTime", "value" : "400" }, { "name" : "setupTime", "value" : "400" } ] }, { "name": "q3", "metrics" : [ { "name" : "executionTime", "value" : "400" }, { "name" : "setupTime", "value" : "400" } ] }, { "name" : "q4", "metrics" : [ { "name" :"executionTime", "value" : "400" }, { "name" : "setupTime", "value" : "400" } ] } ] }' http://127.0.0.1:9000/api/t_benchmark
  ```

- HomeController.scala:

  Shows how to handle simple HTTP requests.

- AsyncController.scala:

  Shows how to do asynchronous programming when handling a request.

- CountController.scala:

  Shows how to inject a component into a controller and use the component when
  handling requests.

## Components

- Module.scala:

  Shows how to use Guice to bind all the components needed by your application.

- Counter.scala:

  An example of a component that contains state, in this case a simple counter.

- ApplicationTimer.scala:

  An example of a component that starts when the application starts and stops
  when the application stops.

## Filters

- Filters.scala:

  Creates the list of HTTP filters used by your application.

- ExampleFilter.scala

  A simple filter that adds a header to every response.
