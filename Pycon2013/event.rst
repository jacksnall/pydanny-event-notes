================================================================================================
So Easy You Can Even Do It in JavaScript: Event-Driven Architecture for Regular Programmers
================================================================================================

In this era of rich browser applications, everybody needs to know at least enough about events to write an '``onclick``' handler. But events have a reputation for being confusing. In this talk I'll explain why events can be quite easy to understand if you think about them the right way, and how to scale your understanding from trivial browser JavaScript to distributed systems in Python.

by Glyph

    * Founder of Twisted
    * has been doing event-driven architecture since he was 8 years old
    * Not stupid enough to attempt live-coding while on stage.

Things that are hard in Javascript
====================================

* Comparing Arrays
* Adding numbers
* Defining types
* Loading Modules

Things that are easy in Javascript
====================================

* Calling functions
* Handling events

A Tale of Two Events
======================

* asynchronous I/O
* Clicky buttons

When X -> Do Y
================

* Event driven architecture is incredibly simple. When X, then do Y.
* When I click -> Do Say "hi"

HTML Example
===================

.. code-block:: html

    <!DOCTYPE html>
    <button onclick="alert(this.innerHTML);"
        Hello, world!
    </button>
    
