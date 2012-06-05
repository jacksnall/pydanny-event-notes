===============
It's about time
===============

by Aymeric Augustin

* Django core dev

.. note:: OMG he talks with incredible speed.

RFC 3339
=========

* Current era
* Stated offset
* universal time
* instant in time

.. code-block:: python

    from datetime import datetime
    datetime(
        year=2012, month=6, day=5
        hour=16, minute=10, second-0,
        microsecond=0,
        tzinfo=FixedOffset(120)
    )
    
