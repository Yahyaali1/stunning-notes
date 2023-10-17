## Patters

Simpler approaches to complex problems 



## Complexity

Cause of Complexity:
- State
- Code volume
- Flow 

* Output of a function should be finite. External factors should not cause flaky results

_Simple code will have simple test cases_

Complexity Levels
* Local 
  * State Complexity
  * Example: Avoid external control of state on a given function.
  * Handler functions (That delegate task and might have switch statements)
    * Testing: Check for delegated function called or not
  * Function to perform singular task only
    * Testing: Check for the result it self
```javascript
const my = () => {
  switch (this.case) {
    //this.case is bad because it makes the function behavior hard to test
    case '1':
      return console.log('')

    default:
      return ''
  }
  
}

```
* Macro

## OOP

Naming Conventions
* Model naming around "Nouns"
* Functions around "verbs"

Data structures or iterators 


