# Variable Naming Rules

JavaScript has specific rules for naming variables. A variable name can contain:

- Letters (`a-z`, `A-Z`)
- Digits (`0-9`)
- Underscore (`_`)
- Dollar sign (`$`)

However, there are some restrictions.

1. Rule 1 — Cannot Start With a Number

This is invalid: `let 1name = "Jane";`
This is valid: `let name1 = "Jane";`

2. Rule 2 — Names Can Start With Letters

This is valid: `let age = 26;`

3. Rule 3 — `_` Can Be Used

```javascript
let user_name = "Jane";
let _name = "Jane";
```

However, JavaScript developers commonly prefer **camelCase** for regular variable names.

```javascript
let userName = "Jane";
```

4. Rule 4 — `$` Can Be Used

```javascript
let $price = 100;
let user$ = "Jane";
```

Although valid, `$` is not normally necessary for ordinary variable names.

5. Rule 5 — Spaces Are Not Allowed

This is invalid: `let user name = "Jane";`

6. Rule 6 — Variable Names Are Case-Sensitive

JavaScript treats uppercase and lowercase letters as different.

```javascript
let name = "Jane";
let Name = "John";
let NAME = "Developer";
```

These are three different variables.

7. Rule 7 — Reserved Keywords Cannot Be Used

JavaScript has reserved words that have special meanings. Such as:

```javascript
let
const
var
function
class
return
if
else
for
while
```

8. Rule 8 — Variable Names Cannot Contain Hyphens

This is invalid: `let user-name = "Jane";`

JavaScript interprets `-` as the subtraction operator.

---

# Naming Conventions

Although JavaScript gives us certain naming rules, developers also follow **naming conventions** to make code readable.

1. camelCase - JavaScript commonly uses **camelCase** for variables and functions. The first word begins with lowercase, and subsequent words begin with uppercase letters.

```javascript
let firstName = "Jane";
let totalPrice = 500;
let userAccountBalance = 1000;
```

2. Descriptive Names - Prefer names that explain what the value represents.

```javascript
let productPrice = 500;
let productQuantity = 20;
```

3. Avoid Unnecessary Abbreviations

Instead of:

```javascript
let usrNm = "Jane";
```

Prefer:

```javascript
let userName = "Jane";
```
