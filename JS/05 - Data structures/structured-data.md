# Structured Data

**Structured data** represents information in a format that can be easily stored, transmitted, and processed. In JavaScript, one of the most common structured data formats is **`JSON`**.

## JSON

> **JSON** stands for **JavaScript Object Notation**. Despite its name, JSON is a **language-independent data format**. It is commonly used for exchanging data between:

- frontend and backend
- web APIs
- servers
- databases
- configuration files

```json
{
  "name": "Jane",
  "age": 26,
  "role": "Developer"
}
```

### JSON Structure

JSON supports several types of values:

- strings
- numbers
- booleans
- `null`
- objects
- arrays

Example:

```json
{
  "name": "Jane",
  "age": 26,
  "isDeveloper": true,
  "skills": ["HTML", "CSS", "JavaScript"],
  "address": null
}
```

### JSON Object

A JSON object contains **key-value pairs**. JSON keys must be enclosed in **double quotes**.

```json
{
  "name": "Jane"
}
```

This is valid JSON.

But:

```javascript
{
  name: "Jane";
}
```

is a JavaScript object, not valid JSON.

### JSON vs JavaScript Object

JSON and JavaScript objects look similar, but they are not the same thing.

#### JavaScript Object

```javascript
const user = {
  name: "Jane",
  age: 26,
};
```

#### JSON

```json
{
  "name": "Jane",
  "age": 26
}
```

JSON is **text/data representation**, while a JavaScript object is an actual JavaScript value in memory.

### Converting JavaScript to JSON

JavaScript provides **`JSON.stringify();`**. It converts a JavaScript value into a JSON string.

```javascript
const user = {
  name: "Jane",
  age: 26,
};

const jsonUser = JSON.stringify(user);

console.log(jsonUser);
```

Result:

```text
{"name":"Jane","age":26}
```

Notice that the result is a **string**.

```javascript
console.log(typeof jsonUser);
// "string"
```

---

### Converting JSON to JavaScript

**`JSON.parse();`** converts a valid JSON string into a JavaScript value.

```javascript
const jsonUser = '{"name":"Jane","age":26}';

const user = JSON.parse(jsonUser);

console.log(user.name);
// Jane
```

### JSON with Arrays

JSON can also represent arrays.

JavaScript:

```javascript
const skills = ["HTML", "CSS", "JavaScript"];

const jsonSkills = JSON.stringify(skills);

console.log(jsonSkills);
// ["HTML","CSS","JavaScript"]
```

### JSON Limitations

JSON supports a smaller set of data types than JavaScript. JSON supports:

```text
String
Number
Boolean
null
Object
Array
```

JSON does **not** directly represent values such as:

```text
undefined
Symbol
BigInt
Function
Map
Set
Date
```
