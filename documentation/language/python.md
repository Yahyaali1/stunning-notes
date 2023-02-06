  ## Python 

* PYPYHTONPATH
* Basic Data Types
    * Numbers
    * Sequences & Understanding notations for access/slicing
        * Mutable
            * List
        * Immutable
            * Strings
            * Tuples
                * Can not change the reference of the object in particular position
        * `_iadd__` (+= , *=)
            * If implemented then object changed in place otherwise new object is returned
            * We need to be careful, things can start to get inefficient. 
        * Collections
            * Threadsafe
            * Queues
            * Array for floats 
                * Offer fast read/write
                * 
        * Built in operations
            * Sorted vs list.sorted
    * Maps
        * Un ordered
        * Only the keys needs to be hashable
            * Hashable means that both items are equal
        * Setdefault is far more efficient as compared to
            * If key in dict: else … 
        * __missing__
            * It will be called instead of raising a key error.
        * Dicts
            * Counter
                * Good for updating and maintaining the counts
            * Ordered Dict
            * Chain Dict ?
        * Immutable Maps
            * Sets
                * Only creation cost
                * Set literal is faster for set creation as compared to calling set constructor
        * Internal workings
            * Why fast ?
            * Why hashed?
            * Why unordered?
            * Why avoid changing while iterating ?
        * Notes
            * Space optimization (dicts take up space, if we are considering million of records)
            * 
    * 
    * Functions & scopes
        * 3 level of scopes
            * Local
            * Global 
            * Built in
        * List of arguments
        * Kwargs
        * Avoid mutable default values because they are declared only once. 
        * Order while calling the function is not necessary. 
            * Q: Check how arguments are processed in python. 
        * Functional Programming
            * List comprehension to replace sort, map or reduce
    * File structure
* References
    * Variables are labels
    * Del only removes label. Garbage collection is done afterwards. 
    * == compares on nested levels. Can be controlled via `__eq__` 
    * “Is” for comparison of references
* Modules
    * Can access all the attributes using `__dict__`
    * `__file__`
    * `__name__` is file name until imported. Otherwise it uses `__main__.`
    * Should be 
        * decoupled 
        * Singular purpose
        * Minimum overlap
    * From statement
        * **Only makes a copies, does not have a reference**
    * Can use `__all__` = [] for preventing exports
* Packages
    * `__init__`.py is called before the import
        * Can be leverage for lazy loading
    * Can use `__all__` = [] to prevent export of all variables
    * Relative imports vs absolute
        * Relative in case within same package
            * Easier to manage than hardcoded package names. Works either way 
            * **Works only inside a package**
            * **They also wouldn’t work if they are executed directly**
        * 
* Classes
    * Attributes resolution, if doesn’t exists in instance follow back to object
    * `__formate__`
            * For string formatting
    * Left to right
    * Inheritance
        * Searches from left to right
    * Object
        * 
    * Instance 
    * Class method get class instance as first param
    * Static method does not get anything
        * Ideally avoided. 

<!-- <p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip") -->

  
* Decorators
    * Synthetic sugar for passing callbacks
    * They are run as soon the module is loaded
    * Parameterized decorators
        * You need to define nested decorators or have a factory for it
    * Cache decorators for improving performance
    * 
* Closure
    * Free space for keeping variables. 
        * Generally used with decorators
        * While dealing with immutable object, we need to use nonlocal because if they are redeclared they are no longer part of free closure
* 
* Control Flows
    * Iter
        * If `__getitem__` is implemented, it will still work based on inner implementation 
    * Iterable 
        * When called with iter() returns iterator			
            * `__iter__` fulfills the iterable protocol by instantiating and returning an iterator. 
        * In short implements iterator interface eq `__next__` , `__iter__`
    * Generator
        * Suspended by yield statement
        * Yield from: for delegating responsibility to inner function 
        * next(generator()) produces the yielded value
        * Generator expression can be used for places where single loop is required
        * Filtering, mapping, reduction, merge 
            * Iter tool implementation are lazy
            * Saves tone of memory 
    * Promises/Futures
        * Async.io futures and concurrency futures
        * They are responsible for starting a future with executioner thread 
            * Methods
                * Thread executioner
                    * Time sharing
                * Process executioner
                    * Across cpu’s
                    * **This could occur within a non-main process spawned in another Pool and spawning processes from sub-processes is not allowed, hence we protect against this problem**
                * add_done_callback(): When the future is done do something. 
                * future.as_completed () `__next__` calls results on it
                * .map easier to use however results are expected in sequence
        * GIL
            * One thread is executed at one time. 
            * Lock is released when we are trying to do I/O.
                * Means that it is helpful that we can learn 
    * Async I/O
        * Design
            * Event loop
            * Events hooked with it
            * asyncio.async() ->>> Task Object
                * Can be cancelled
                * ​​asyncio.async(...) or loop.create_task(...).
            * Yield from for suspended the task 
            * Yield from syntax can be used for waiting on tasks
            * Coroutine requires event loop to be executed
        * Coroutine decorator
            * asyncio.sleep ()
            * Other sleep would make main thread go to sleep. 
            * 
* Datetime is the system time. 
* Timezone from django is the time from the settings