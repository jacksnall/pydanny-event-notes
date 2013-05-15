============================================
Processing payments for the paranoid
============================================

* By Andy McKay

    * @andymckay
    * Works at Mozilla

The Mozilla Marketplace is the app store for Firefox OS and this Django powered site takes payments from users. 

Combined with issues like localisation, identity and scale - we are processing payments through Django. This talk will cover the marketplace, the architecture of the system and how we cope with all the paranoia.

Who should be paranoid?
========================

Everyone should be paranoid:

    * Developers
    * Users
    * banks
    * Everyone
    
Mozilla Marketplace
=====================

* Powered by Django
* Don't call it an "app store"
* accepts payments
* Powered by open source project 'zamboni'

.. note:: 

    Report bugs to Mozilla via their reporting system and they'll pay you.

Steps for purchase
=====================

1. Set up your account with Mozilla
2. Purchase and use an app
3. Mozilla bills your carrier

Vulnerabilities they had to consider
========================================

* XSS

Mozilla Content Security Policy
--------------------------------

* MDN docs
* Github blog