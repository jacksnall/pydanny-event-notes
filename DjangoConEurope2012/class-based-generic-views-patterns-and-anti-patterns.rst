========================================================
Class-based Generic Views: patterns and anti-patterns
========================================================

* BY BRUNO RENIÉ
* CBVs added in Django 1.3
* https://speakerdeck.com/u/brutasse/p/class-based-views-patterns-and-anti-patterns

.. note:: couldn't keep up with his code samples

Controversy
============

Blog posts last week

* Luke Plant
* Nick Coghlan

What are views in Django?
=========================

"A view is a callable that takes a requests and returns a response"


Deprecation
=============

* Functional views are not deprecated
* Generic functional views are

Pre Django-1.3 Django CBVs
==============================

* Admin
* RSS feeds
* Sitemaps

CBV API
========

.. code-block:: python

    class View(Object):
    
        @classonlymethod
        def as_view(cls, **init):
            def view(request, *args, **kwargs):
                self = cls(**init)
                return self.dispatch(request, *args, **kwargs)
                
        # TODO find the rest
        
Declarative vs Imperative
==========================

* CBVs have a much steeper learning curve
* ccbv.co.uk is a handy resource

Usage Tips for Django CBVs
===========================

* try to keep urls.py for URL definition and nothing else
* Keep decorators in views.oy

Decorating
----------

.. code-block:: python

    # TODO show Python 2.7 version here

    class MyView(generic.ListView):
        pass
    # Complete this
    
MRO, extend, don't override
------------------------------

Unless you're 100% sure of what you're doing

Case Studies
=============

Useful recipes

Form processing
-----------------

TODO - get the form processing example

Nested Navigation
-------------------

# TODO - get example

Pagination
-----------

# TODO - get example

Registration
--------------

.. code-block:: python

    from le_social.registration import views
    
    class Register(views.Register):
        form_class = blah
        
    # TODO get example
    
Settings
--------------

Don't set so many settings:

.. code-block:: python

    from le_social.registration import views

    class Activate(views.Activate):
        expires_in = 3600 * 24 * 7 # 7 days

Shooting yourself in the foot
==============================

The problems with using CBVs

The 500 Error
--------------

.. code-block:: python

    class Handler500(generic.TemplateView):
        template_name = '500.html'
        
No matter what goes into this, it will throw out blank pages.