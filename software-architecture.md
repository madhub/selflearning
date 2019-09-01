# Software Architecture
* An architecture is a dcomposition of a system into smaller elements , interface  & rules( for further design or implementation) and the specification of the interaction between the elements & behaviors.
* The primary purpose of architecture is to support the life cycle of the system. Good architecture makes the system easy to understand, easy to develop, easy to maintain, and easy to deploy. The ultimate goal is to minimize the lifetime cost of the system and to maximize programmer productivity

* [vertical-slice-architecture](https://jimmybogard.com/vertical-slice-architecture/)
* [Onion Architecture In ASP.NET Core MVC](https://www.c-sharpcorner.com/article/onion-architecture-in-asp-net-core-mvc/)
* Messaging is a great way to build loosely coupled, scalable, and reliable systems
* Design tips for building scalable systems 
  * Asynchronouse message based
  * Create stateless application or keeping state outside the application
* [Service Connector Pattern](http://www.servicedesignpatterns.com/WebServiceInfrastructures/ServiceConnector). There are two types of Service Connectors. The first is the Service Proxy (a.k.a. Proxy). This type of connector is used with RPC APIs and Message APIs. The second type is the Service Gateway, which is commonly used with Resource APIs. Unlike service proxies, they usually aren't produced by code generation tools. 
    * 
