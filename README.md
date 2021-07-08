# SWAPI_TestTask

The project for retreiving data from SWAPI GraphQL API

## Table of Contents
* General info
* Technologies
* Setup and Usage
* Status

### General Info
The project aim is to query SWAPI GraphQL API and retreive the next data:
- all species participated in 1st movie of Star Wars
- data for person with "Droid" specie
- totalCount and data for all persons from 1st movie
- data for person with id=4

### Technologies
The Postman tool is used 

### Setup and Usage
Import collection.json and environment.json files to Postman.
Run the Query#1 and Query#2 requests from imported collection.
Check the response for retrieved data and environment for stored data.

## Questions:
1) What is kafka? How it works? Which are the main advantages/benefits of using
kafka?

Kafka is a messaging technology for asynchronous communication. It is  a distributed, parallel processing, replicated messaging service
Producers send records to Kafka brokers, the messages clustered in the kafka storage, consumers fetch records from broker
The advantages is high throughout (big performance), scalability, permanent storage, high availability, works with any content

2) Write down testing strategy for an application that uses kafka, describe how the
testing will be organized and provide 1 test case as an example.

As a testing environment we can use Testcontainers - for testing with docker containers
For a good confidence we can use end-to-end testing approach to validate both producing, consuming and processing of records.
Scenario: Send and receive a record
Given: The http producer is up
Given: The http-consumer follows Topic1
When: The http producer sends record {"key":1, "value":"text"} to the Kafka Topic1
Then: The http consumer receives with record {"key":1, "value":"text"} from Topic1

3) What is microservice architecture? Please write down your approach for testing
microservices and what will be the scope of your testing.

It is an approach when a big system is decomposed to various services for handling specific functions so we can easily add new features to the application.
The application uthat uses Kafka usually is usually SOA based solutions. So it should start from verification SOA itself, that it can produce a correct data or process a received data in a right way.
Each SOA should be tested independently with unit-testing and send perform intergation testing between services with operate in pair. Make a performance testing to evaluate system responsiveness and stability on load.

4) What will be your approach to ensure that tests can be re-run in future?
-
