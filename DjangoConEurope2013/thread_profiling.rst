==============================
Thread Profiling in Python
==============================

by Amjith Ramamujam

    * Works for http://newrelic.com

This talk will give a tour of different profiling techniques available for Python applications. We'll cover specific modules in Python for doing function profiling and line level profiling. We'll show the short comings of such mechanisms in production and discuss how to do sampled profiling of specific functions. We'll finish with statistical profilers that use thread stack interrogation.

What's profiling?
==================

cProfile for profiling the performance of something

Usage::

    python -m CProfile sample.py

For big projects it can be big in response, so use **RunSnakeRun** (wxPython app) which gives you better data.

Google uses profiler and displays the results in their search engine. Which is why it's good to use in production. Unfortunately profiling eats up performance. So what do you do?

Targeted Profiling
==================

* Profile critical functions
* Do hybird stuff

New Relic targets
===================

* Web frameworks

    * Django, flask, etc
    * View layer
    * template layer
    * SQL calls
    

Threads for profiling
==============================

example:

.. code-block:: python

    import threading
    t = threading.Thread(target-handler)
    t.setDaemon(True)
    t.start()
    time.sleep(0.1)
    
**Pros:** 

    * Cross platform
    * mod_wsgi compliant
**Cons:** 
    
    * Inaccurate for CPI tasks
    * can't interrupt C-extensions
    
Inquire into what's going on
=============================

.. code-block:: python

    >>> import sys
    >>> frames = sys._current_frame()
    >>> print(frames)
    {1234: <frame>}
    >>> import traceback
    >>> traceback.extract_stack(frame)
    (...stuff here...)
    