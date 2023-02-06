// Js-Basics: https://www.youtube.com/watch?v=W6NZfCO5SIk
// Js-Advance/React : https://www.youtube.com/watch?v=NCwa_xi0Uuc 
// Arrow Function: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions 
// Desctructing: https://hacks.mozilla.org/2015/05/es6-in-depth-destructuring/


```javascript
// Normal statements end with ";"

// Declaring a variable using "let"

let x = 1;

//Log can be performed using 
console.log(x);

//----------------------------------------------------------------------------------------------------------------------------------------------------
//BASIC PERMITIVE DATA TYPES

//int,boolean,string,undefined,null

//int 
let integer = 1;
console.log(integer);

//boolean 
let amHuman = true;
console.log(amHuman);

//string can be declared using single or double quotes
let myName = "Yahya";
let myFriendName = 'John';
console.log(myName+' and my friend\'s name is '+myFriendName);

//---------------------------------------------------------------------------------------------------------------------------------------------

//Any variable that value will remain same throughout the program can be declared using const.
const nameOfHome = "Earth"

console.log(nameOfHome);

//-----------------------------------------------------------------------------------------------------------------------------------------------

//undeclared variables has "undefiend value" and type 
let myFutureBestFriend; 
console.log(myFutureBestFriend);

//"null" can be used to replace value within the variable 

myName=null;
console.log(myName);
//null value can be replaced again with value 
myName= "Yahya";
console.log(myName);
//--------------------------------------------------------------------------------------------------------------------------------------------->
//Notes
//All the variables have dynamic types. For example if the variables has integer value this can be reassigned to string as well
//without having a error. 

console.log('Type of myName'+typeof(myName));
myName = 1;

console.log('MyName type has changed');
console.log(typeof(myName));

//--------------------------------------------------------------------------------------------------------------------------------------------->

//REFERENCE TYPE

//Other data type is Java script is "object" type
//we can define custom object or reference type. 

let person = {
    name : 'YAHYA',
    age: 23
};
console.log(person)
//Allows the properties to be accessed by "." or using brackets 
console.log('Person Name \n');
console.log(person.name);
//using brackets
console.log(person['name']);

//using brackets allows to cover the use case such as we can select property on run time 
//EXAMPLE

let selection = 'name'

console.log(person[selection]);

//------------------------------------------------------------------------------------------------------------------------------------------------

//Arrays are also part of object type 
//We can access properties of arrays using the "."

let integerToFive = [1,2,3,4,5];
console.log(integerToFive);

//individual elements can be accessed using brackets

console.log(integerToFive[1]);
//Other properties
console.log(integerToFive.length);

//Arrays can contain dynamic binding as well, furthermore they can extend dynamically as well 

integerToFive[5]=6;
console.log(integerToFive[5]);

integerToFive[0] = "Ali"

console.log(integerToFive[0]);

//------------------------------------------------------------------------------------------------------------------------------------------------

//Function can be declared using the prototype below 

function sayMyName(name){
    console.log('Hello '+name);

}

sayMyName(myFriendName);

//if parameter value is not assigned it will still fun normally. As the parameter will have undefined value

sayMyName();

//--------------------------------------------------------------------------------------------------------------------------------------------->
import {Person} from "./advance.js"

console.log(new Person())


//ARROW FUNCTION
//They are more like in line functions
//Example

let numbers = [1, 2, 3, 4, 5];

const square = x => {
  return x * x;
};

//if we have no parameters we can write function as

const withOutParm = () => {
  return 1;
};

//If are function only returns the value we can use

const returnOnlyOne = () => 1;

for (let i = 0; i < numbers.length; i++) {
  numbers[i] = square(numbers[i]);
}

console.log(numbers);

//Arrow function also don't rebind "this" key word.

//------------------------------------------------------------------------------------------------->

//DESTRUCTING
//Concept of allocating properties and values to variables.

let [a, b, c] = numbers;

console.log(a);
//Few values can be skiped as well

let [x] = numbers;
console.log(x);

//Array can be extracted as well for assignment

let [head, ...tail] = numbers;
console.log(tail);

//---------------------------------------------------------------------------------------------------------->

//Complex examples of this invovles working with complex objects in structure.
let complex = {
  first: 1,
  second: {
    third: 3,
    third_second: 3.2
  }
};
//The property names need to be mentioned inorder to destruct
let { first: first_part, second: middle_part } = complex;

console.log(middle_part);
//-------------------------------------------------------------------------------------------------------------->
//Another example is to use it with functions
function forDestructing([first, second]) {
  console.log(first);
}

forDestructing([1, 2]);

//-------------------------------------------------------------------------------------------------------------->
//CLASSES
//constrcutor function
export class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
//constructor only called with "new" keyword
console.log(new Person("Yahya", 23).name);

//Can perform inheritence
class Employee extends Person {
  constructor(name, age, salary) {
    super(name, age);
    this.salary = salary;
  }
}

//^ Export key word is added to export any function,class to other files.
//Can be aggregated in this form

export default { Person, Employee };

//default is for non named exports.

//-------------------------------------------------------------------------------------------------------------->

//ARRAY MAP
const colors = ["red", "green", "blue"];

items = colors.map((color, index) => {
  return "<li>" + color + index + "</li>";
});

//using template literals
let items_template = colors.map((color, index) => {
  return `<li>${color}</li>`;
});

//-------------------------------------------------------------------------------------------------------------->
//spread operator is to help with task similar to concatination
//Operator on the array
const first = [1, 2, 3];
const first_second = [2, 3, 4];

let combined = [...first, ...first_second];
console.log(combined);

//this operator works on the objects as well
let ram = {
  capacity: 2
};
let processor = {
  clock: 2.3
};
let computer = { ...ram, ...processor };
console.log(computer);
```