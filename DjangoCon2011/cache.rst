===================================
Cache rules everything around me
===================================

By Jacob Burch

 * Engineer at Revsys with me
 * Former CTO of Mahalo

By Noah Silas

 * Engineer at Causes.com
 * Former head architect of Mahalo
 
Intro to caching
====================

 * Caching is post-process data
 * Stored in a key/value store
 * Usually Done to:
 
    * Speed up your app
    * Lesson load on third party apps
    
Big Picture
====================

Jacob's rule of architecture
------------------------------

 * No rules only principals
 * Start with assumptions/advice
 * Benchmark/inspect before you break principals
 
Ask some questions
------------------

 * Do you really need caching? Caching adds...
 
    * complexity
    * additional point of failure
    
 * Modern database are stupidly optimized
 
    * May be all you need!
    
*There are only two things in Computer Science, cache invalidation and naming things* - Phil Karlton

Relying on your cache always being up
------------------------------------------

 * Rely on a single canonical data source
 * This data source IS NOT YOUR CACHE
 

Common Cache Patterns
---------------------- 

 * Rollup values often called like settings
 * Only do it for common data calls
 * What's easy:
 
    * cache invalidation is relatively easy
    
 * What's hard
 
    * Known when to invalidate
    
Thundering herd problem
------------------------

 * If everything in your cache tries to reload at once because you had a service outage
 * Huge load on your system and third party apps
 
    * You may get throttled by other systems

The New Hotness Pattern
------------------------------

 * Cache Forever, Invalidate, explicitly
 
    * Keep the cache forever
    * Invalidate only when the data changes
    * Add the data back right then and only for that bit
    
 * Use celery or deferred to handle long processes
 
Key-holding
-------------

 * How about storing cache keys in a file?
 
How to avoid Cache Invalidation Hell
========================================

Yay!

What's in the box
-----------------

 * django.core.cache
 
    * simple setup
    * Multi Cache Support
    
 * django.core.cache.backends (best way)
 
    * memcached.MemcachedCache
    * memcached.PyLibMCCache

Implementation best Practices
========================================

stuff here