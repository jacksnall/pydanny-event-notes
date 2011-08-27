==============================
Behaviour Driven Development
==============================

By Malcolm Tredennick

Why have I asked you here today
===============================

* Testing landscape
* A different way to think about this
* Code

Some terms
===========

* Stubs is empty data
* Mocking is pretend versions of data

Mocks
======

* Substitute for external systems & components
* Need to be injected into the tests

    * "monkey patching"
    * Dependency injection

* Problem: Mocks need to be kept in synch with reality

.. warning:: I've run into this with mocks. This is why Open Comparison includes real API calls to it's target systems.

Testing Strategies
==================

* formal verification
* test everything you can think of
* anti-regression suite

    * no bug fix without a test
    
* Test Driven Development (TDD)

    * Wraite failing test for next method or clas
    * Write minimal code to make test pass
    * Rinse, wash, repeat
    * Kind of drives Malolm crazy
    * Really about "*specification, not verification*"
    
* Documentation Driven Development (DDD)
* Behavior Driven Development (BDD)

.. note:: Apparently this is the point at which we are done with the intro

Specification
=============

* On paper
* Capturing the idea is probably good
* "What was I *thinking* when I cooked this up?"

.. parsed-literal::

    As a [user or role]
    I want [feature]
    so that [something happens]