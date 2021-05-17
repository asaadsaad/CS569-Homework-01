# CS569 Homework 01
### Object Typing
Object literal may only specify known properties, add the necessary changes to allow adding optional property `z` as a number, and another property of any letter as a string.
```javascript
interface Point {
    x: number;
    y: number;
}

const point1: Point = { x: 2, y: 4};
const point2: Point = { x: 3, y: 6, z: 9 };
const point3: Point = { x: 4, y: 8, z: 12, name: "Asaad"};
```
  
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
Create a decorator called `addressify` in TypeScript to be used on any empty class, the decorator will add two `number` properties `x` and `y` as per this example:
```javascript
@addressify(2)(4) 
class Street {} 

console.log(new Street()); // object {x: 2, y: 4}
```
Transpile your code to JS, and test your code. Remember to enable decorators in `tsconfig.json`.
