==================================================
Asynchronous and event-driven PyOpenCL programming
==================================================

* by Tomasz Rybak

    * tomasz.rybak@post.pl
    * Debian Maintainer of PyOpenCL and PyCUDOA
    * Currently working at CodiLime
    * Worked at University of Geneva

Description
===========

	OpenCL is the library, API, and programming language intended to help with performing computations on different computing devices like ordinary CPUs, graphical cards (GPU), specialized chips or FPGAs. OpenCL provides different profiles offering various capabilities (e.g. kernel compilation during runtime, executing native binary code, embedded function libraries) to allow to support different device types. Programming GPUs in Python is easy thanks to PyOpenCL (and PyCUDA). Not everything offered by OpenCL can be used in Python though, because OpenCL is defined assuming usage of the C language. Some functionalities, like calling function in response to event, require providing pointer to C function; fortunately such requirements show themselves only in the most sophisticated use cases. PyOpenCL helps with achieving high performance through asynchronous event-driven programming by allowing us to use many queues and many devices and by mixing synchronous and asynchronous calls. We can create quite sophisticated computation workflow and OpenCL will take try to use the available hardware, e.g. by concurrently call code and transfer data at the same time. New OpenCL versions allow for splitting one physical device into many logical ones (fission) which can be used to reserve some computing capabilities for usage in time-sensitive manner. We can also attach many devices to once shared context which allows to write code performing different tasks and computations in parallel. Some of the features offered by PyOpenCL are similar to those present in Python. Performing asynchronous computations on GPUArray and retrieving results later is similar to Python's Futures. So far it is impossible to retrieve Futures from GPUArray (to integrate GPU and CPU computing) but this seems to be the case of missing functionality, not incompatibility preventing it from happening. I want to show that creating programs performing quite sophisticated computations might be easy thanks to Python and PyOpenCL. I would also like to start discussion about current PyOpenCL limitations and to get feedback from PyOpenCL users.
	
Increasing hardware parallelism
===============================

* More's law, increasing transistor density
* Power wall
* Chip's frequency doesn't increase anymore
* We get more cores instead
* No more automatic performance improvements
* Different programming models
* OpenCL has emerged as a standard intended to help with programming over this obstacle.

Summary: Use OpenCL to access the power of graphics cards as math processors

OpenCL
=======

* Standard maintained by Khronos
* Similar to OpenGL

    * Extensions
    * Different models for different devices

* Compile dor binary kernels run on cores separate from CPU
* Based on C
* Includes events and asynchronous execution

Basic OpenCL programming model
==============================

* Execution units hierarchy

    * Hosts
    * Platforms
    * Computing devices
    * Computing units
    * Processing elements
    
* Memory hierarchy

    * Global memory
    * Constant memory
    * local memory
    * Private memory
    
* Relaxed consistency of memory access
* Cache

Execution run-time hierarchy
==============================

* Context
* Queue
* Work-group

    * A bunch of threads go into a work group
    * Which means you can have 100 threads run in a group, or 1000.

* Work-item

Execution Models
==================

* Task parallelism

    * One thread running computations
    * Possibility of running many threads at the same time
    * Require out-of-order queue or many queues
    
* Computation parallelism

    * Many 
    
TODO - Get the parts I missed

PyOpenCL
=========

* ... and PyCUDA
* Python wrapper for OpenCL
* Not only wrapper

    * Pythonic
    * Object oriented
    
* Stable but still work in progress

    * extensions
    * high level programming
    
OpenCL programming workflow
============================

1. Compile kernels
2. Prepare data
3. Transfer data to device
4. Run computations
5. After finishing computations get results from device
6. Free resources

Event based programming done in Python
==========================================

* Instruct OpenCl to run computations
* Don't wait for data
* Computation will get to you when it's done

.. code-block:: python

    event = pyopencl.enqueue_copy(queue, a, agpu)
    event.wait()
    
    event = program.increase(queue, a.shape, None, a_gpu)

    # later code
    queue0 = pyopencl.CommandQueue(context)
    queue1 = pyopencl.CommandQueue(context)    
    event = pyopencl.enqueue_copy(queue)
    
    
Event-related objects
=======================

* Not all PyOpenCL functions and methods accept list of event to wait for
* We can wait for these events manually
* Or we can create a marker or barrier to force the end of a queue

Fission
=========

* Splitting one physical device into many logical ones.
* Can be used to reserve some computational power
* Solution similar to CPU virtualization
* No problems with device-to-device memory transfers

Where PyOpenCL helps
=====================

Provides:

    * Array
    * Random number generators
    * Single pass element-wise expressions
    * Reduction
    * Parallel scan
    
Designed so you aren't writing C code from scratch all the time to make your computations work fast in the graphics cards.



