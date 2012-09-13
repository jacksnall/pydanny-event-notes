=====================
Fractal Architectures
=====================

* by  Laurens Van Houtven (@lvh)


    Traditional service architecture wisdom generally tells us to build services like this:
    Load balancer in front
    Web servers, preferably stateless
    Database (with a caching layer)
    That works great for a wide variety of use cases. The point of this talk isn't to deprecate that design, but to discuss a radically different one.
    The design I will present in this talk is one consisting of recurring, identical components. It localizes state to individual application servers and persists it to durable stores later. It aims to be easier to scale horizontally: that is, enabling you to increase throughput by simply adding more machines to the homogenous cluster.
    I will talk about it's benefits, such as performance and how it fits in well with many cloud providers' services, but also its downsides, such as the inherent complexities of distributed systems. These qualities are analyzed to come to a conclusion about which kinds of project this design is suitable or not suitable for.
    In this talk I will discuss both the abstract concepts and the practical implementation that I have built using Twisted and Axiom (a simple object database on top of SQLite 3), which is currently running in production. Although I will touch on the practical implementation, the talk should still be useful for anyone wanting to implement a similar idea using different tools.
    
Standard Architectures
=======================

Check out Twelve Factor App. 

* Level 1: Servers Database Cache
* Level 2: Application Servers
* Level 3: Load Balancing

The problem is that scaling all of this gets server and code expensive. You have to add in distributed data, messaging queues, and extra servers. 

Consider Instead...
=====================

* Sharding architecture
* Problems:
    
    * Expensive
    * Only for things on a Facebook scale. 
    * Most people don't need this sort of thing.
    * Forces restrictions on code patterns.
    
 * Advantages
 
    * Constraints on code means you have the freedom to do what you want within those constraints.
    * Lower latency
    * Great for when one user is only interacting with data that just affects themselves
    * Perfect for things like a webmail client. Most of the real behavior of the system is interacting with the client, not doing SMTP.