# Keyed Collections

**Keyed collections** store values using **keys** rather than numerical indexes.

```text
                Keyed Collections
                       |
       ┌───────────────┴───────────────┐
       |                               |
    Map-like                        Set-like
       |                               |
┌──────┴──────┐                 ┌──────┴──────┐
Map         WeakMap            Set          WeakSet
```

---

## Map

> A **Map** is a collection of **key-value pairs**.

```javascript
const user = new Map();
```

One important difference between `Map` and ordinary objects is that a `Map` can use many different types as keys. Objects can also be used as keys:

```javascript
const userObject = {
  name: "Jane",
};

const userData = new Map();

userData.set(userObject, "User information");
```

### Adding Values with `set()`

```javascript
const user = new Map();

user.set("name", "Jane");
user.set("age", 26);
user.set("role", "Developer");
```

### Getting Values with `get()`

```javascript
console.log(user.get("name"));
// Jane
```

```javascript
console.log(user.get("age"));
// 26
```

### Checking for a Key

```javascript
console.log(user.has("name"));
// true

console.log(user.has("email"));
// false
```

### Removing a Key

```javascript
user.delete("age");
```

### Number of Entries

```javascript
console.log(user.size);
```

### Iterating Over a Map

```javascript
const users = new Map([
  ["name", "Jane"],
  ["age", 26],
  ["role", "Developer"],
]);

for (const [key, value] of users) {
  console.log(key, value);
}
```

Output:

```text
name Jane
age 26
role Developer
```

---

## WeakMap

> A **WeakMap** is similar to a `Map`, but it has important restrictions. A `WeakMap` stores **key-value pairs where the keys must be objects or non-registered symbols**.

```javascript
const user = {
  name: "Jane",
};

const data = new WeakMap();

data.set(user, "Private information");

console.log(data.get(user));
// Private information
```

### Garbage Collection

A `WeakMap` does not prevent an object used as a key from being **garbage collected** when there are no other references to that object.

```text
                WeakMap
                  |
                  |
              ┌───▼───┐
              │ Object│
              └───────┘
                  ↑
              weak reference
```

If the object is no longer used anywhere else, JavaScript can eventually remove it and its associated `WeakMap` entry. This makes `WeakMap` useful for **object-associated metadata** without keeping those objects alive just because they are keys.

### WeakMap Keys

This works:

```javascript
const user = {};

const map = new WeakMap();

map.set(user, "Some data");
```

But this does not:

```javascript
map.set("name", "Jane");
// TypeError
```

because `"name"` is a string, not an object or non-registered symbol.

### WeakMap Opertions

Unlike `Map`, a `WeakMap`:

- cannot be iterated with `for...of`
- does not have a `size` property
- does not provide `keys()`, `values()`, or `entries()`
- only supports object/non-registered-symbol keys

Basic operations are:

```javascript
set()
get()
has()
delete()
```

---

## Set

A **Set** is a collection of **unique values**.

```javascript
const numbers = new Set();

numbers.add(10);
numbers.add(20);
numbers.add(30);
numbers.add(10);
```

If we try to add the same value again the Set still contains only one `10`.

```text
10 → duplicate → ignored
```

### Creating a Set

```javascript
const numbers = new Set([1, 2, 3, 3, 4, 4]);

console.log(numbers);
// Set(4) {1, 2, 3, 4}
```

This makes `Set` useful for removing duplicates.

```javascript
const numbers = [1, 2, 2, 3, 3, 4];

const uniqueNumbers = [...new Set(numbers)];

console.log(uniqueNumbers);
// [1, 2, 3, 4]
```

### Adding Values

```javascript
const fruits = new Set();

fruits.add("Apple");
fruits.add("Banana");
fruits.add("Mango");
```

### Checking a Value

```javascript
console.log(fruits.has("Apple"));
// true

console.log(fruits.has("Orange"));
// false
```

### Removing a Value

```javascript
fruits.delete("Banana");
```

### Set Size

```javascript
console.log(fruits.size);
```

### Iterating Over a Set

```javascript
const numbers = new Set([10, 20, 30]);

for (const number of numbers) {
  console.log(number);
}
```

---

## WeakSet

A **WeakSet** is similar to a `Set`, but it is specifically designed for storing **objects or non-registered symbols**.

```javascript
const weakSet = new WeakSet();

const user = {
  name: "Jane",
};

weakSet.add(user);
```

We can check whether an object is present:

```javascript
console.log(weakSet.has(user));
// true
```

And remove it:

```javascript
weakSet.delete(user);
```

### WeakSet Restrictions

A `WeakSet`:

- can only contain objects or non-registered symbols
- cannot contain primitive values such as strings or numbers
- cannot be iterated
- does not have a `size` property

Example:

```javascript
const weakSet = new WeakSet();

weakSet.add({ name: "Jane" }); // valid
```

But:

```javascript
weakSet.add("Jane");
// TypeError
```

---

# Map vs WeakMap vs Set vs WeakSet

| Feature          | Map             | WeakMap                                 | Set           | WeakSet                |
| ---------------- | --------------- | --------------------------------------- | ------------- | ---------------------- |
| Stores           | Key-value pairs | Key-value pairs                         | Unique values | Unique objects/symbols |
| Keys             | Any value       | Objects / non-registered symbols        | —             | —                      |
| Primitive values | Yes             | Values can be any type, keys restricted | Yes           | No                     |
| Iterable         | Yes             | No                                      | Yes           | No                     |
| `size`           | Yes             | No                                      | Yes           | No                     |
| Weak references  | No              | Yes                                     | No            | Yes                    |
