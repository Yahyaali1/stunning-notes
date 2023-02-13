# Server & Services 

Express application 

* Routing
  * app.METHOD(path, handler)
    * Path is the desired route, handler is the corresponding functions
    * HANDLERS
      * Can be multiple functions 
      * use `next()` for passing control to next handler
        * Are the req and res passed along as it is ? 
  * ```.all(/path, handler)```
    * For running the handler on all HTTP method for a given path. 
      * Smart use of `next()`, can be used to pre process data or request 
      * 
  * app.use
    * For handling middleware 
  *  