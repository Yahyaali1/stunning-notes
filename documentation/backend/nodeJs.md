### [Node Js](https://nodejs.dev/en/learn/)

- Node Distinct Features
  - Runs in non blocking manner
  - Resumes once the resource such as I/O is available
  - Will use CommonJs or ES modules
  - Will use V8 javascript engine for code compilation

### Node Std Library
- Networking utilities
  - Http
    - For creating server
    - req & response objects
      - Http.serverResponse, IncomingMsg 
      - They can be used to set and read headers and other familiar operations

___
### Async Behavior 
Recommended Function patterns 
* Initiator
  * Takes input from sources and calls functions on it
* Middleware
  * Takes input a function and input and returns a function
* Terminator
___
Methods for Attacking async behavior
- Serial Operation. 
  - Perform next operation after the first operation finishes
- Parallel
  - With or Without limit

___
Blocking vs NonBlocking Code
- Blocking 
  - No other execution takes place during that time

___
Paths 
``` require("path") ```
Helpful in resolving the path only. Does not ensure if the path exist or not.
* Resolve to get absolute path.
  
___
File reading Writing 
* Using "fs"
  * Has sync alternative or fs/promise for promise based utility
* This reads complete file into memory 
  * This can have memory implications. We should try streams for large files

```javascript
const fs = require('fs/promises')
async function example() {
  try {
    const data = await fs.readFile('/Users/joe/test.txt', { encoding: 'utf8' });
    console.log(data);
  } catch (err) {
    console.log(err);
  }
}
example();
```
____

### Node Cli 
* ```node app.js```
* ```nodemon app.js``` a dependency for watching live changes 
* ```userId=123 node app.js``` is available with `process.env.userId`
* We generally user .env file in combination with `require('dotenv').config();`
  

### Command line args

* Using readLine module 
____
State Management
* In Memory 
* I/O
* Global storage does not always guarantee results

___
Events
* Can use events module for emitting and listening to events 
  ```javascript
  const emitter = new EventEmitter()
  emitter.emit('event')
  emitter.on('event', () =>{})
  ```


___
### NPM
- Dev dependencies
  - Testing libraries that have no role in prod build
- Optional Dependencies
  - Should not fail build if unable to install it
  - 

### Exports

```javascript 
module.exports = app 
// single variable exported from a file


exports.app = app 
// multiple value exported from a file
```

### Common js
```  javascript
// file names.js
expore.myName = "yahya" 

const {myName} = require("names.js")

```
### ES
- Need to ensure file is a module. We can use mjs extension to do that. Or by using "module" in package.json
```javascript
import http from "http"

```



