===============================
Building secure Django websites
===============================

* by Erik Romijn

    * hello@solidlinks.nl

Three Areas
============

* Integrity

    * Internal consistency or lack of corruption in electronic data

* Confidential

    * To keep data secret that was intended to be secrity

* Available

    * ability to be used or obtained
    
How cookies and sessions work
==============================

.. parsed-literal::

    Set-cookie: name: value
    Cookie: name=value
    
Sessions
----------

.. parsed-literal::

    sessionid=8f70xxxxa3d9
    session: {
        key: 8f70xxxxa3d9,
        user: Erik
    }

If you can access the session of another user, you can impersonate the other user.    

Cross Site Request Forging
---------------------------

Fortunately for us, if you use POST, Django by default has CSRF protection enabled via:

.. code-block:: django

    <form>
        {% csrf_token %}
        ....
    </form>    

XSS Injection
==============

Injecting HTML or JavaScript into things like field data

.. code-block:: html

    <p>Injecting issues <script>alert("I'm a JavaScript injection!");</script></p>
    
Reflected vs. Stored XSS
==========================

* Previous examples are reflected XSS

    * Have to try the user into visiting my link
    
* Other possibility is stored XSS

    * Store some data which is later sent back to users, e.g. blog comments