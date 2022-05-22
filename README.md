# CS569 Homework 01

### Generics Exercise
Create a generic class `Queue` that restricts its items to a specified type.
```javascript
const queue = new Queue<string>();
queue.push("Asaad"); // ["Asaad"]
queue.push("Mike"); // ["Mike", "Asaad"]
queue.pop(); // returns "Asaad" and queue = ["Mike"]
queue.push(2022); // ERROR : cannot push a number. Only strings are allowed!
```
