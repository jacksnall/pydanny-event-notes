============================
Django and the Real-Time Web
============================

* by Zachary Voase

WWW: Changelog
===============

* Since July 2008 Chrome has stolen the market from IE. 
* Chrome is about to take over IE in the desktop.
* JavaScript and long polling has come around.

Can't miss this opportunity
==============================

But If we spend all your time playing with bright and shiny we'll lose our existing customer base.

Zachary's definition of Real-Time
===================================

* UI before technology
* Proactive, not reactive
* Synchronized with the 'real world'.

Stories
==============

MVC
----

* Parc 1978-1979
* Originally part of Smalltalk-80
* Now the dominant UI design pattern

How it works on the web:

* Listen for reqursts

    * Load session state for this user
    * Persist session state, clean up objects

REST
----

* **RE**presentational **S**tate **T**ransfer
* Roy T Fielding (2000)
* Descriptive, not prescriptive
* Constraints

    * Client-server
    * Stateless
    * Cacheable
    * Layered
    * Code-on-demand (optional)
    * Uniform
    
WebSockets
-----------

* Real TCP connection
* Magic HTTP request to port 80
* Reduces latency
* Enables real-time push

REST & WebSockets
-------------------

* Full-duplex communication
* Long-running connections
* Direct TCP connection
* TODO missed

Version Control
----------------

* Centralized VCS (CVS, SVN, etc)
* Distributed VCS (Git, Mercurial, etc)

Summary of the stores
-----------------------

* Imagine a system where the client is a full MVC stack, as is the server. 
* Content is a matter of pushing/pulling like with DVCS
* Backbone.js does this, as well as Cappucino

Caching
=========

* Read RFC 2616
* Seriously.
* Etags
* Cache-Control
* Conflict resolution