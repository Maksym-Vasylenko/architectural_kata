# Streaming Specification v1

## Context and Problem Statements

* How to ensure the scalability of the system and guarantee the processing of all events of the state of dishes in fridges?
* Standardization of objects for changing the state of dishes.
* Is it possible to add a new point of sale that will produce its data in new/unknown format or way (for example, a new partner company like Toast or Byte)?

## Decision Outcome

Chosen option: Kafka Streaming, because

* Scalability, high throughput and guaranteed delivery ordering out-of-the-box.
* Kafka Connect - allows us to easily integrate with various data formats or information sources.
* Dynamic customization of the processing pipeline by adding a new consumer.