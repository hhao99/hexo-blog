---
title: springboot-practice-01
date: 2018-03-19 13:39:40
tags: spring microservice kotlin
---
# Getting startted with spring boot
spring boot simplified the springframework and help us to focus on the development, not the configuration and the depenpendices.
with the release of the spring-boot 2.0, it support the modern language kotlin, I will take the note the develop the simple micro service based timesheet application based on the 12factors design pattern and implmented in springframework.

# timesheet application
in the software project, every engineer need record his work based on the time and work, timesheet applicaiton help the developer to input his work to the central timesheet database and the project manager can view the effort of the every member to be charged in his project.

## monolithic application approach
in the traditional architecture design approach, we seperate the application domain to 3 differenet tiers and use the MVC design pattern to architect the application, with more than 10 years, J2EE and SSH framework is the main stream of the applicaiton development in the enterprise application architecture.
In this approach, the UI is build by JSP or some template engine, the business domain was moduled by the EJB or POJO with JPA to the backend, all the business logic was implemented in the same deploy module and maintained by the same dev team.

## challendge of the monlithic application
Transactional and stateful design pattern make the application is hard to scale out to support growing bussiness demand, and the availability and fault tolerent is also the shortcomming for this architecture, migrate the the cloud and adopt the modernized application architecture is hard to re-engineering this type of application.
And also fro the bussiness requriements aspect, we can not quickly add the feature to the existing application, the AOP can help this type of application, but modify the code and adopt the new feature to the existing model need extral effort the do the unit test and integration test, need redeploy the code the production enviornment which will stop the current transaction in the production environment.

And the DevOps adoption also is the big challenge for this approach, the dev and ops team must define the clear test and deployment process, testing and delpoyment will take longer time to complete, agile development is the myth.

## mciro service
Moving to the micro service.

"In short, micro service architecture style is an approach to developing a single application as a suite of small service, each running in its own process and communicate with lightweight mechanism, offer an HTTP API to represent its resources.These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies.”
-- James Lewis and Martin Fowler

## micro service of timesheet
we design the timesheet service to 3 different domain(for simplified version), employee service for the engeer details and wbs code for the charge code and time record for the timesheet record.

All the services follow the micro service pattern:
-- single reponsibility, around the business
-- share nothing, stateless
-- independent deploy

## advantage of the microservice
### Parrelle development model
With the implementation of the 3 different service model for the time sheet application, we can split the applicaiton to 3 different model to proritized the business module and parrelle develop the application.
### focus on the business domain
with the simplifed business domain, we can focus the business domain requirement and utility the agile development methodology to quick implement the prototype and add the feature with 2-4 release cycle, more agile to support the business demands and quick delpoy to production environment.
### high performance development team
with this model, only 4-6 person in one development team to communicate with each others effiently and effectively.
### service oriented design applied
Loosely decouple, focus the internal architect and extensibility was the key success factor of the soa design pattern.
### language and tools neutral 
every team will use their tools and platform to develop and host their service, the devops model also is applied effieciently to this model.

in the next module, we will discuss the microservice design method, the DDD and BDD related topic.

