=============================================
Transifex: Beautiful Python app localization
=============================================

by Dimitris Glezos

Intro
======
 
* Github for translations
* Develop for an international audience

Workflow
=========

* Mark translatable strings
* Release string freeze
* Translator: VCS checkout
* Translate w/special tools
* Get 'em files back

    * SSH, email, tickets

* For every frigging release

Python & Gettext
====================

.. sourcecode:: python

    # TODO show Django import
    from gettext import gettext as _
    
    thing = _("I'm going to be translated")
    
.. sourcecode:: jinja

    {% load i18n %}
    
    {% trans "person" %}
    
    {% blocktrans count ppl|length as num %}
    TODO show moar
    
* Generates PO files

How to render PO files
=========================

TODO: show the command-line actions for pure Python and Django

Traditional model of translations
================================

* Content owner/developer
* Localization manager
* Content management system
* Developers

Existing solutions before Transifex
==================================================

* Emails to translation agencies

    * loss of control
    * Expensive

* Build own L10N system

    * Lots of work
    * Expensive

Transifex
===========

* SaaS product
* Open source platform
* Built for developers to maintain

Simpler model of translations
==============================

* Content owner/developer
* Content Management System
* Transifex

Transifex size of project
=========================

* 17,000 users
* 3,000 products

Tech
=======

* Django, Python, PostgreSQL, MongoDB, Redis
* Celery AMQP
* Django Add-ons
* Mercurial, Git

Workflow automation
=====================

.. parsed-literal::

    $ pip install transifex-client
    $ tx set --auto-local -r myrproj.myres --source-lang en etc...
    
Creates a local .tx file that set sup the configuration file. This can be uploaded to git.

.. parsed-literal::

    # commands to interact with Transifex 
    $ tx pull --source
    $ tx push --translations
    
Workflow automation
======================

* Continious integration
* VCS commit hooks
* API to translate content
* Services on Github and Bitbucket
* Heroku Addon

Nifty features
===========================

* Social interactivity, comes with a onboarded community