# CS569 Homework 02
### Generics Exercise
We have a function `homework` which takes object, and key of this object, and string value. The purpose of this function is to create a new object with concatenated property object[key] with third argument.

The question - How to type generic types `T` and `K` in the definition of `homework` function in order to achieve compile time guarantee that `obj[key]` can be only `string`.
```javascript
const homework =
  <T, K>(obj: T, key: K, payload: string): T => {
    const prop = obj[key]; // compile error should not be here
    return { ...obj, [key]: prop.concat(payload) }; // compile error should not be here
}
// tests
const test = { fieldStr: 'text', fieldNum: 1, fieldStr2: 'text' };
homework(test, 'fieldStr', 'test'); // should be ok 
homework(test, 'fieldNum', 'test'); // should be error fieldNum is not string field 
homework(test, 'notExistingField', 'test'); // should be error - no such field 
homework(test, 'fieldStr2', 'test'); // should be ok 
```
### Working with Webpack
1. Install `typescript` transpiler globally: `npm i –g typescript`
2. Create `tsconfig.json`: `tsc --init` and set `outDir: './js'`
3. Create two `ts` module files and convert them to `js` using: `tsc`
4. In `js` folder, create `html` file that is using those generated `js` files, run a web server `http-server` and notice how browsers cannot understand the `import` statement
5. Run `npm init -y` and then install `webpack` as a development dependency: `npm i webpack webpack-cli --save-dev`
6. Add the following script to `package.json`: 
```javascript
{ "build" : "webpack ./app.js -o ./bundle.js" }
```
7. Run `npm run build` and it will bundle all `js` files into one.
8. Use the `bundle.js` file and test the results in the browser.
  
### Decorator Exercise
Create a Module called `available.ts` in TypeScript that exports one factory decorator `addAvailability` to be used as a decorator for a simple empty class with a new `Boolean` property called `available`.  
Use your custom decorator in `app.ts`:
```javascript
@addAvailability(true) 
class Course {} 

console.log(new Course()); // object {available: true}

@addAvailability(false) 
class School {} 

console.log(new School()); // object {available: false}
```
Transpile your code to JS, then bundle it, and test your final bundle in the browser.
