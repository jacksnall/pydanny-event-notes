====================
Mock your database
====================

by Marc Tamlyn

    * https://twitter.com/mjtamlyn
    * Pivotal figure in the giant Django CBV documentation refactor for 1.5

Databases are slow. Well, if the goal is 1 millisecond per test they are anyway. We want to avoid interacting with the database as much as possible when testing, especially if the tests aren't anything to do with the queries.

This talk will look at various ways of avoiding those pesky database queries and making tests faster!

Your database is slow
=======================

* When you are testing, hitting the database is slow. Connections, writing to disk, getting down to SQL, etc
* Why do you care?
* We want SPEED!
* The faster your test goes, the better.

Example
==========

.. code-block:: python

    def test_naive(self):
        label = RecordLabel.objects.create()
        artist = Artist.objects.create()
        track = Track.objects.create()
        # etc
        
* 8 database queries
* 5.2 seconds for 1000 runs on PostgreSQL
* 3.2 seconds for 1000 runs on SQLite3 running in memoery

Doesn't seem slow, but what if we are testing 40 models this way? Test factories make this worse!

