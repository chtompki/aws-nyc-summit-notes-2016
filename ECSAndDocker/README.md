Continuous Integration with Amazon ECS and Docker
=================================================

### Okta Connect Everything.
They "connect people" There are a ton of folks that use their service. Ok...this is boring and silly. Let's get to the details. Ok, so they have 200 engineers. 1 week sprints. Every merge to master is a potential release candidates.

### Problem Statememt.
Opensource monolithic applications. We can replace git poller and Gearman with SQS. What is "Glados?" They replaced it with lambda. The slave pool is the place where things cost the most. How do we manage this?

### Vision
* Clean test environments
* Dynamic worker scaling
* Spot instances for cost (What are "spot instances?")
* Versioned Testing
* Improvised queuing system
* Less Infrastructure...more causes flakiness.
* The correct privileges to maintain security.

### Docker

He introduces what docker is ... ok ... nothing spectactular.