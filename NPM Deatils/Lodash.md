**Lodash** is a modern JavaScript utility library that provides **helpful functions for common programming tasks** such as:

* Array manipulation
* Object handling
* Function control
* Deep cloning
* Debouncing
* and much more!

It helps write **cleaner, shorter, and more readable code**.

---

## 📥 Installation

```bash
npm install lodash
```

Then import it in your file:

```js
const _ = require('lodash'); // CommonJS
// or
import _ from 'lodash'; // ES Modules
```

---

## 🔧 Lodash Core Features (With Examples)

---

### 🔁 1. **Array Utilities**

#### `_.chunk(array, size)`

Split array into chunks

```js
_.chunk(['a', 'b', 'c', 'd'], 2);
// => [['a', 'b'], ['c', 'd']]
```

---

#### `_.compact(array)`

Removes falsey values (like `false`, `0`, `''`, `null`, `undefined`, `NaN`)

```js
_.compact([0, 1, false, 2, '', 3]);
// => [1, 2, 3]
```

---

#### `_.uniq(array)`

Removes duplicates

```js
_.uniq([1, 2, 2, 3]);
// => [1, 2, 3]
```

---

### 🧠 2. **Object Utilities**

#### `_.get(object, path, defaultValue)`

Safely get a nested value

```js
const obj = { user: { name: 'Sangram' } };
_.get(obj, 'user.name'); // => 'Sangram'
_.get(obj, 'user.age', 25); // => 25 (default)
```

---

#### `_.merge(object, otherObject)`

Deep merge two objects

```js
const a = { user: { name: 'Sam' } };
const b = { user: { age: 30 } };
_.merge(a, b);
// => { user: { name: 'Sam', age: 30 } }
```

---

### 🔁 3. **Collection Utilities**

#### `_.map()`

Works like `Array.prototype.map`, but works on both arrays and objects.

```js
_.map([1, 2, 3], n => n * 2); // => [2, 4, 6]
_.map({ a: 1, b: 2 }, val => val * 2); // => [2, 4]
```

---

#### `_.filter()`

Filters a collection based on a condition

```js
_.filter([1, 2, 3, 4], n => n % 2 === 0);
// => [2, 4]
```

---

### ⏳ 4. **Function Utilities**

#### `_.debounce(func, wait)`

Delays execution of a function until after a certain delay (used in search, resize, etc.)

```js
const debouncedSearch = _.debounce(() => {
  console.log("Searching...");
}, 300);

window.addEventListener('input', debouncedSearch);
```

---

#### `_.throttle(func, wait)`

Ensures function runs at most once every X milliseconds

```js
const throttledScroll = _.throttle(() => {
  console.log("Scrolling...");
}, 1000);

window.addEventListener('scroll', throttledScroll);
```

---

### 🧱 5. **Cloning and Equality**

#### `_.cloneDeep(value)`

Creates a deep clone of a value

```js
const a = { name: 'Sam', hobbies: ['reading'] };
const b = _.cloneDeep(a);
b.hobbies.push('coding');
// a remains unchanged
```

---

#### `_.isEqual(a, b)`

Checks deep equality between two values

```js
_.isEqual({ a: 1 }, { a: 1 }); // true
_.isEqual([1, 2], [2, 1]);     // false
```

---

### 🔠 6. **String Utilities**

#### `_.camelCase()`, `_.kebabCase()`, `_.snakeCase()`

```js
_.camelCase('Hello world'); // => 'helloWorld'
_.kebabCase('Hello world'); // => 'hello-world'
_.snakeCase('Hello world'); // => 'hello_world'
```

---

## 💡 Why Use Lodash?

* ✅ Works consistently across browsers
* ✅ Saves time from writing repetitive utility code
* ✅ Handles edge cases better than native JS methods
* ✅ Used heavily in React/Node projects

---

## 🧪 Lodash in Real Projects

### 💻 In React: Debounce Search

```js
import _ from 'lodash';

const handleInput = _.debounce((e) => {
  console.log("Search query:", e.target.value);
}, 300);

<input onChange={handleInput} />
```

---

### 🔐 In Node.js: Deep Clone Request Object

```js
const clone = _.cloneDeep(req.body);
```

---

## 📌 Lodash Alternatives

* Native JavaScript (`Array.map`, `Object.keys`)
* [`Underscore.js`](https://underscorejs.org/)
* `Ramda` – More functional programming
* `Rambda` – Smaller Ramda

---

## 🔗 Lodash Docs

Official website: [https://lodash.com](https://lodash.com)
Full API Docs: [https://lodash.com/docs/](https://lodash.com/docs/)

---
