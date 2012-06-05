========
Keynotes
========

Jacob Kaplan-Moss
=================

.. code-block:: django

    {{ keynote }}

* jacob**@jacobian**.org
* Keynotes are hard.
* Researched to find different types of keynotes

    * Announcements
    
        * Steve Jobs
    * Technical Tour-de-force
    
        * David Beasley style
        
    * State of...
    
        * West Wing style
        * Make it dramatic
        
    * Celebration
    * (Constructive) Criticism
    
        * Cal Henderson's 2008 DjangoCon talk
    
    * Inspiration
    
        * Neil Gaiman
        * Adam Savage
        
Se he's going to do the following talks:
-----------------------------------------

* Technical
* State of...
* Celebration
* Criticism
* Inspirational

Technical Talk
-----------------

.. note:: @jacobian pointed me out and embarrassed me so I didn't finish copying out his sphinx example.

Sphinx is awesome::

    .. code-block:: html+django
        
Useful Sphinx stuff for authentication-protected static files:

    * **static**: http://lukearno.com/projects/static
    * **barrel**: http://lukearno.com/projects/barrel    
    
These sorts of integrated components are an incredible indicator of some of the awesomeness of Python

State of Django Talk
---------------------

* Django is doing very well
* Each release has more and more incredible stuff added.
* "Always feels like we are not moving as fast as we should, but when you look at what's been accomplished it's amazing. Especially since forward compatibility has been pretty well maintained."
* Django 1.5 should give us

    * Python 3 support
    * Composite keys
    
Celebration
-----------

* This year has seen a ridiculous amount of adoption for Django.
* There is no longer an industry where Django does not exist.
* Django is now considered boring compared to things like node.js. Exciting is good when you are trying something new, but "exciting" and "production" should never be combined in the same sentence.

    * See this article http://blog.pinboard.in/2010/01/technical_underpinnings/
    
* Notable tech acquisition for Instagram.

Criticism
----------

* HTML5 issues

    * Bruno's floppyforms handles the form elements for you: see http://django-floppyforms.rtfd.org/
    
* Real-time 

    * State of the art: parallel MVC stacks.
    * Mentioned Meteor framework as state of the art.
    * You are fooling yourself if you don't realize that Meteor style systems are not the future of web development.
    * Are we doomed to callback hell?

.. code-block:: javascript

                    });
                });
            });
        });
    });
        
Can we not do client/server apps purely in Django?
    
.. code-block:: python

    url('people/1/', person_detail)
    
    def person_detail(request, pk):
        ctx['person'] = get_object_or_404(Person, pk=pk)
        return (request, template, ctx)
        
    {{ person.first_name }}

Inspirational Talk
-----------------------

Jacob's uncle, a lawyer asks: "But if you give it away, how will you make money?"

* By giving it away, people have made a ton of money with Django
* Jacob is doing quite well

Summary
----------

* Huge community brought in by our boring, stable system.
* Now we can get really crazy with Django
* Make good art

Karen Tracey - Django and the Community
===================================================

* http://twitter.com/km_tracey
* Been programming since 1987
* Django Core dev for a while.
* Crossword puzzle constructor since 2001
* Cat rescuer since 2009

.. note:: I've been programming since 1980. See http://mytechne.com/user/pydanny/programming-languages/. I win on the age game. So there.

Why?
----

* Django's community is one of it's greatest strengths

Her Django story
------------------

* Django open-sourced a year earlier
* Django 0.96

Puzzle Database
----------------

* Aid in constructing puzzles, accessible from construction tool
* Amassed over ~5 years
* ~5,000 puzzles, ~100,000 unique entries, ~500,000 clues

Project: Web front-end for database
------------------------------------

* Primary goal: better ability to see data in crossword puzzle tool
* Secondary goal: learn Python