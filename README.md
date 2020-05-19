# CS569 Homework 02
### Generics Exercise
Create a generic class `Queue` that restricts its items to a specified type.
```javascript
const queue = new Queue<number>();
queue.push(0); // [0]
queue.push(1); // [0, 1]
queue.pop(); // returns 1 - [0]
queue.push("Asaad"); // ERROR : cannot push a string. Only numbers allowed
```
  
### Decorator Exercise
Create a Module called `available.ts` in TypeScript that exports one factory decorator `addAvailability` to be used as a decorator on any simple empty class, the decorator will add a new `boolean` property called `available`.  
Use your custom decorator in `app.ts`:
```javascript
@addAvailability(true) 
class Course {} 

console.log(new Course()); // object {available: true}

@addAvailability(false) 
class School {} 

console.log(new School()); // object {available: false}
```
Transpile your code to JS, then bundle it, and test your final bundle in the browser. Remember to enable decorators in `tsconfig.json`.
