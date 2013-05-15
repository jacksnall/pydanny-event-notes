====================================
Advanced PostgreSQL in Django
====================================

* by Christophe Pettus

PostgreSQL is the most advanced open-source database on the planet, but (except for GeoDjango) few Django developers take advantage of its more advanced features. We want to change that!

We'll talk about custom types (including Admin integration), replication tricks, specialized indexes, unstructured types such as JSON, stored procedures, and other ways to get maximum functionality and performance out of your PostgreSQL data store.

Database Agnosticism
======================

* Django has to be able to handle all databases.
* That means it loses special features of individual database systems (PGSQL, MySQL, etc).
* Database migration is a once in a lifetime thing.


What can PostgreSQL do for you
================================

Custom Types
-------------

