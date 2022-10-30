# CS569 Homework

### Generics Exercise
Create a generic class `Queue` that restricts its items to a specified type.
```javascript
const queue = new Queue<string>();
queue.push("Asaad"); // ["Asaad"]
queue.push("Mike"); // ["Mike", "Asaad"]
queue.pop(); // returns "Asaad" and queue = ["Mike"]
queue.push(2022); // ERROR : cannot push a number. Only strings are allowed!
```
### Review Design Patterns
Review and implement the following design patterns in JavaScript:
* Singleton pattern
* Observer pattern
* Decorator pattern
