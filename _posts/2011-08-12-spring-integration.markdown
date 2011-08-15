---
layout: default
title: Spring Integration as building block for SOA
categories: soa
type: blog
---

This is a short review of the Spring Integration Framework(SI)[^si]. 
To understand this article you should be familiar with Enterprise Application Integration(EAI) and have
basic understanding of Enterprise Integration Patterns(EIP)[^eip].
For those new to EAI or EIP:

* _EAI_ is an architectural approach for integrate data, services across the enterprise. EAI simplify and
automate business process without requiring comprehensive changes in existing applications and data structures[^psi].

* _EIP_ is set of integration patterns. EIP helps developers and architects describe and develop robust integration solutions[^eip].

For those new to SI, definition from project home page[^si]:
> _"Spring Integration provides an extension of the Spring programming model to support the well-known Enterprise_
> _Integration Patterns. It enables lightweight messaging within Spring-based applications and supports integration_
> _with external systems via declarative adapters. Those adapters provide a higher-level of abstraction over Spring's_
> _support for remoting, messaging, and scheduling. Spring Integration's primary goal is to provide a simple model_
> _for building enterprise integration solutions while maintaining the separation of concerns that is_
> _essential for producing maintainable, testable code."_

What is the place of SI in Service Oriented Architecture(SOA)? Tom McCuch explains this in one of his comment[^tmc]:
> _"SOA is an architectural pattern. A pattern, by definition, is the encapsulation_
> _of a complex system into a reusable component. Patterns are meant to describe_
> _"building blocks" for YOUR solution - they are not meant to be solutions in of_
> _themselves. Patterns therefore lend themselves to be best implemented by lightweight,_
> _embeddable frameworks that serve to support your solution, not heavy, commercial-off-the_
> _shelf products that aim to control it. This is where the big vendors have all gone wrong with_
> _SOA - and where SpringSource, yet again, has gotten it right with Spring Integration."_

For more information refer to wikipedia[^eai] or SI home page[^si].
You will find there documentation, reference manual, articles, podcasts and much more.

### Lets take a look on some advantages and disadvantages of the SI.

#### At first advantages:

* __Implements proven patterns__ - The SI team didn’t invent the wheel again. The whole architecture 
and solutions in SI are based on Enterprise Integration Patterns[^eip]. 
  For example [Service Activator pattern](http://bit.ly/riOKGt):
  <script src="https://gist.github.com/1139466.js?file=gistfile1.xml">
  </script>

* __Lightweight, maintainable, easy debugging and testable code__ - SI is based on the Spring programming model which gives you possibility to:
    * develop code using POJO approach - There is rarely any need to couple your code with SI API.
    * unit testability and system testing support is provided by framework, you can do it without requiring deployment to your application server or connecting to other enterprise infrastructure.

    Sample test configuration:
    <script src="https://gist.github.com/1139498.js?file=ServiceActivatorTest-context.xml">
    </script>

    And test suite:
    <script src="https://gist.github.com/1139498.js?file=ServiceActivatorTest.scala">
    </script>

* __Documentation__ - SI has good documentation with practical examples that will help 
you understand channels, adapters, routers etc. You can find also very good books 
about SI e.g., [“Pro Spring Integration”](http://bit.ly/pu2ul4) from Apress. It covers contemporary technologies 
and real-world examples, facing the real problems. Another important thing is community 
which is really helpful and eager to solve your problems fast.

* __Low Coupling - channel as a first class citizen__ - 
By Oleg Zhurakousky: 
> _"In SI we have Channel as a first class citizen. In all other frameworks it is mentioned only as an internal implementation not exposed to the end-user._
>  * _Channels is what enforces the decoupling between producers and consumers._
>  * _Channels is what's allowing us to manage message-exchange protocols. From throttling to parallelism all is accomplished via channels._
>  * _Channels gives end-user transparency with regard to how these message-exchange protocols are applied. Change the type of a channel without any producer/consumer awareness."_

* __Model complex solutions__ - using SI you are able to model complex solutions using various technologies 
like EJB, RMI, AMQP etc. in one place[^dsblog].

* __Adapters for legacy system__ - possible adapters for legacy systems like an old mainframe 
application where input/output are batch files deposited on some FTP endpoint. Writing your own adapters in most cases are easy and straightforward. For more 
details check out "Pro Spring Integration" chapter 15[^psi].

* __Easy integration with other spring projects__  like Spring Batch, Spring AMQP(RabbitMQ). 
SI has the ability to launch Spring Batch jobs via messaging, 
allowing for event-driven batch process. In addition, SI can be used to scale 
out Spring Batch using partitioning. This provides the ability to partition big 
batch jobs over many nodes using message channels as the coordination fabric[^psi].

* __GUI designer in SpringSource Tool Suite__ - Simple designer will help you with fast modelling of flows and let you visualize your configuration file adhoc.
Mark Fisher about GUI designer:
> _“One of the best things about it is that it was designed from day one to support "round trip" editing._
> _In other words, changes in the graph immediately show up in XML and vice-versa. They are just 2 tabs_
> _on the same view - sitting on top of the exact same metadata model. Unlike the big commercial products,_
> _we know it's very important that a GUI editor does NOT hide the details from a developer's perspective._
> _XML, if kept as concise as possible (something we have worked very hard at doing), is actually pretty_
> _good for configuration (although IMHO it's NOT good at all for coding imperative logic like when/otherwise_
> _or try/catch!), and we made sure that the editor does not interfere in any way with the developer's ability to read/understand/modify that XML.”_

    For quick introduction refer to Refcards: [Eclipse Tools for Spring: The SpringSource Tool Suite](http://bit.ly/pbmlZr)

* __Spring Integration Scala DSL__ - domain-specific language for Scala[^dsl]. Example:

    <script src="https://gist.github.com/1141786.js?file=DslDemo.scala">
    </script>

#### Disadvantages:
* __New technology__ - tree years on the market might not be enough for the bigger companies.
* __Missing adapters__ like ssh, shttp. Lack of the many adapters comparing to e.g., [MuleESB](http://bit.ly/ohrEq4). Always you can i
fill JIRA for SI if you see some functionality which is crucial for you and can be used by community.

Is the Spring Integration framework for you?
You have to answer this question by yourself. SI is lightweight, 
powerful technology build on the proven platform which you can use to model ESB which fits your needs.

Gists are from [https://github.com/kgrodzicki/spring-integration-samples](http://bit.ly/p6DPTP) project.

Any comments? Let me know on Twitter [@kgrodzicki](http://bit.ly/t-kgrodzicki).

[^eai]: [http://en.wikipedia.org/wiki/Enterprise_application_integration](http://en.wikipedia.org/wiki/Enterprise_application_integration)

[^eip]: [http://www.eaipatterns.com/](http://www.eaipatterns.com/)

[^dsblog]: [http://www.digitalsanctum.com/2010/08/31/using-rabbitmq,-spring-amqp-and-spring-integration/](http://www.digitalsanctum.com/2010/08/31/using-rabbitmq,-spring-amqp-and-spring-integration/)

[^siftips]: [http://forum.springsource.org/showthread.php?109838-Tips-for-article-about-Spring-Integration](http://forum.springsource.org/showthread.php?109838-Tips-for-article-about-Spring-Integration)

[^sijl]: [http://www.infoq.com/articles/Spring-Integration-Joshua-Long](http://www.infoq.com/articles/Spring-Integration-Joshua-Long)

[^si]: [http://www.springsource.org/spring-integration](http://www.springsource.org/spring-integration)

[^psi]: Pro Spring Integration Josh Long , Dr. Mark Lui , Mario Gray , Andy Chan

[^tmc]: [http://www.infoq.com/articles/Spring-Integration-Joshua-Long#view_38115](http://www.infoq.com/articles/Spring-Integration-Joshua-Long#view_38115)

[^dsl]: [https://github.com/SpringSource/spring-integration-scala](https://github.com/SpringSource/spring-integration-scala)
