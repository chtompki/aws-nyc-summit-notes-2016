Continuous Integration with Amazon ECS and Docker
=================================================

## Table of Contents

* [Okta Connect Everything\.](#okta-connect-everything)
* [Problem Statememt\.](#problem-statememt)
* [Vision](#vision)
* [Docker](#docker)
* [Host management](#host-management)
  
-------------------------------------------------------

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

Importants:

* Only use docker containers from the internal repository
* *jFrog Xray for container*
* *cAdvisor from google*
* Never bake secrets into the images. (KMS??)
* Never use "latest" artifacts 
* Write all logs to standard out, and then let the host manage the logging.
* [ECS Under the Hood](http://www.allthingsdistributed.com/2015/07/under-the-hood-of-the-amazon-ec2-container-service.html)

### Host management
Userdata installs:

* Slave terminator
* Base docker images an option
* credentials from S3
* splunk forwarder
* cluster target
* cache code and libs. (this is important if we're just going to share a volume).

__*IAM separation per "task definition."*__ I'm not sure what this neans, but it sounds interesting. Task definition can list several containers (i.e. you can do a small constellation of containers in the task definitions). __*Need to find his code here*__

### Problems with ECS and Docker

* Docker containers not launching
* ECS agent not launching
* Other junk
* Load balancer isn't as good in the ELB land.
* Different endpoint for adding things in the cluster.