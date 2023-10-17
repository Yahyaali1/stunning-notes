Q: What is a service in feather js ? How are we using it to listen to function calls

q: Configure functions How are they working exactly

## App

_App object holds all the objects that app will ever interact it. It is like a giant class that has all the associated
options with it._

Is the object that has all the associated services and configurations

* .use
    * Can register service using 'use' ```use(name, instance, {methods: ['get', 'custom']})```
        * Note that a server side app.service(path) only allows the original service name
        * (e.g. app.service(':userId/messages')) and does not parse placeholders.
        * To get a service with route paramters use .lookup
* .configure
    * Can register service that requires app instance using 'configure' Can be used to segregate things into different
      files
* Setup/listen
    * For starting server
* .get
    * For fetching app wide things

___

## Service

Service is the protocol for interaction with data.

- <span style="color:yellow">**Required signature**</span>
    - Must be async
    - Must have id, data and params as params
- **Params has information about**
    - provider, user, authentication, query, headers, connection
- Has CRUD operation function. **At least on of them should be implemented**
- Can add custom methods as well

```javascript 
    Service { async find(params){} }  
    app.use('/my-service', Service); 
```

- Services registered with Rest api with be mapped to
  [CRUD](https://crow.docs.feathersjs.com/guides/basics/services.html#service-methods) functions
- Database adapters provided by feathers
    - They can be further extended for customization
- Service registered become events emitter as well
    - Called after (create, update, patch and remove) returns.
    - Q: what data in returned event ?

```javascript
app.service('myservice').on('created', data => {
})
```

* `.hooks`
* `.publish` Used for scoket io ??
* `.on`
* `.emit`
* `.removeListener`

___

## Hooks

Service and App both can have hooks

Redundant logic across different services

- Pluggable logic design. That is required across different services
- Can be registered on around, before, after, & delete for CRUD operations
- Receives a context and can return it as well
    - Context is object with editable properties

```javascript
app.service('message').hooks({
  "before": {
    create: [(context) => {
      context["newthing"] = 1
      return context
    }]
  },
  "after": {},
  "error": {},
  "around": {}
})
```

**Hooks Context**

* Has some readonly and write only properties
* Read only
    * App, service, path, method,
* Write able
    * params,
    * Id (in specific cases only)
    * .data available to create update & patch
*

When to use Service ?

- Does multiple things
- Interacts with db or storage

Q: How do we interact with multiple services or multiple objects ? Q: How do I access current user ?

___

## Events

* Based on Node events emitter module
* Available with Services and for app as well
* Can be added custom events as well ```app.service("me").emit('callMe', {data: 'hello'})```

___

## Errors

Can be used from require(''@feathersjs/errors')

Helps with handling events such as NotFound

express handles errors for REST API only. Need to handle other errors using hooks or middleware

```javascript
import { FeathersError } from '@feathersjs/errors'

class UnsupportedMediaType extends FeathersError {
  constructor(message, data) {
    super(message, 'UnsupportedMediaType', 415, 'unsupported-media-type', data)
  }
}

const error = new UnsupportedMediaType('Not supported')

console.log(error.toJSON())
```

## Configuration

Path with configs Is handling everything with https://github.com/node-config/node-config/wiki/Environment-Variables

``/config/*.json``

* Allows handling of global variables or configs for the system

## Transport Layer

1. Express
    
    A version of original express
* Offers:
  * Rest API
  * Error Handling

**Few overlapping cases**

Q: Express uses `.use` from middleware. Feathers uses it for registering a service if it is a object for service


## Authentication Flow


