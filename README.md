# architectural_kata_healthy_food_system

This repo contains diagrams and description for architecture kata Farmacy Food.
For better understanding of this description open please system design diagram.

Design of this system includes several types of architecture patterns: microserveces, service-based and event-drivern pattern.

Microservices is used to have small services that have clear boundary and to do one thing and do it well. 
For example Dictionary Service was chosen to be seperate small service and to have access both from Inventory and Admin. It could be 
for example part of Admin but in that case boundary would be crossed if Inventory accessed Admin directly.
In case of having seperate service with separate DB we do not have integration on DB level which can lead to horrible consequences.

Service Based architecture style is implemented in our Inventery service design. This service incapsulates several domains inside,
but until we do not need separate scalability of them, they can live together without issues and what is more important, in this case
we have less operational work. Also with this approach we tryied to avoid distributed transactions. Because handling them is a nightmare for distributed systems.

Inventory service is stateless which means that it can be scaled horizontically as all other services.

Event based architecture was used to build part of system that accept events from external systems and then can process them.
Architectural descision why this pattern was selected is described in  streaming-spec file.
