Destructuring in ES6

Destructuring allows us to extract values from arrays and objects; ES6 makes it simpler and easier.


Destructuring Arrays:

 var arrayOne = ['hello', 'there', 'bob'];


With ES5, each element in the array is assigned to its own variable.

 var greet = arrayOne[0];
 var where = arrayOne[1];
 var name = arrayOne[2];

console.log(greet, where, name);
returns => hello there bob


 In ES6, variables need to be assigned in the same order that the elements appear in the original array, and would appear as follows:

 var [greet, where, name] = arrayOne;

 console.log(greet, where, name);
 returns => hello there bob



Destructuring an object:

 var greeting = {
   greet: 'hello',
   where: 'there',
   name: 'bob'
 };


 With ES5, elements are being assigned to their own variables outside of the object:

 var greet = greeting.greet;
 var where = greeting.where;
 var name = greeting.name;

 console.log(greet, where, name);
 returns => hello there bob


 When using ES6, the same code can be reduced to one line in which the values in the object are all simultaneously set to the variable greeting:

 var {greet, where, name} = greeting;

 console.log(greet, where, name);
 returns => hello there bob


 let { length: len } = arrayOne;

 console.log(len);
 returns => 3

 for( i = 0; i < len; i++){
   console.log(i);
 };
