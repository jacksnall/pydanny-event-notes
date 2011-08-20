=========
Keynotes
=========

Audrey Roy
============

Audrey was opening keynote speaker. I'm partial but I think she rocked it. :)

Mary Gardiner
================

Mary Gardiner spoke about:

    * Be an open source super hero and try to change the world
    * Find a project that helps people and get involved!

Sample projects:

   * plover http://plover.
   * Software Carpentry http://software-carpentry.com
   * calibre TODO get link
   * Sugar TODO get link
   
Raymond Hettiger
================

LA's own Raymond Hettiger talked about `What makes Python Awesome?`

    * Other languages are awesome, how is Python better?
    * Most Python releases are GPL-compatible. This makes it free.
    * Going to a closed source language means you are trapped.
    * Commercial distributions like ActiveState and Enthought
    * Python has Zen. Internalized as core developers and internalized by community devs
    
    
Community
---------
    
    * Mailing lists
    * Newsgroups? HA HA HA
    * Python User Groups
    
PyPI
----

    * Repo for Python programming language
    * Over 16,000 packages
    * `pip install ordereddict` works for Python 2.5!
        
Killer apps
------------
    
    * Zope, Django, Pyramid
    * Numpy and Scipy
    * Bittorrent and Twisted
    * YouTube
    * Blender and Maya
    * Win32 - Factoid: Me, @pydanny, has done all his windows programming using cpython and Win32!
        
Easy to learn!
---------------------
    
    * Good teachers.
    * Think how fast you got the types and control structures in Python. General 3 hours
    * In a day you can learn special methods and stdlib
    * Critical because if you need good Python developers it doesn't take long to get up to speed. Converting developers takes:
    
        * C takes 2 years to get competent
        * Java takes 6 months to get competent
        * Python takes a week to get competent
        
    * Rapid development cycle
    
        * Scripting languages are unbeatable for development speed
        * Programs are grown organically
        * Interactive testing lets people work with their code results immediately.
        * Bang out real code fast
            
Economy of expression
---------------------

 * Not many words or characters to get things done.
 * clear English means non-coders can understand your work
 * **Pydanny factoid**: One of the first times I wrote Python on a whiteboard for a boss at NASA/SAIC they thought it was very legible pseudo code representing a complex process.
    
.. sourcecode:: python

    hashmap = {}
    for path, dirs, files in os.walk('.'):
        for filename in files:
            # fill this out from the slides
            
Beauty Counts
-------------

 * Readability is the #1 mentioned characteristics of why organizations choose Python
 * The beautiful appearance on the page directly affects a programmer's sense of joy
 * Makes us go home and write code
 * If you can read other people's code that makes it easier to maintain
 * Because we all `mostly` share the same idiom it means we can read each other's code. That doesn't stifle creativity - it just means we can get along.
 
    * As a parent I can say I would have *loved* having a formal uniform at school. As a geek in school I would have loved that too. :P

Interactive Prompt (REPL)
----------------------------------------

    * Python experts don't memorize Python
    * They use the interactive prompt often (I try to write tests...)
    * This is a killer features that runs circles around compiled languages
    
        * Python shell
        * IPython 
        * BPython (My favorite)

Behind the Scenes
------------------

Philosophy of core dev

 * Conservative growth
 * `We read Knuth so you don't have to`
 * Aim for simple implementation
 
Protocols
----------

To interact with these we have defined protocols

 * DBAPI
 * Hashlib
 * Compression
 * WSGI for the web
 * Conversion protocols
