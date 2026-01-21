# JavaScript Equality Operators: `=` vs `==` vs `===`

This repository explains the difference between JavaScript’s **assignment** and **equality** operators—a very common source of bugs in real-world applications.

---

## `=` (Assignment Operator)

**Purpose:** Assigns a value to a variable.

```js
let x = 10;
Assigns 10 to x

Does not compare values

Common mistake when used inside conditions

❌ Incorrect usage:

js
Copy code
if (x = 5) {
  // Assigns 5 to x and always evaluates to true
}
== (Loose Equality)
Purpose: Compares values after type conversion.

js
Copy code
5 == "5" // true
JavaScript converts "5" to 5 before comparing.

⚠️ Can lead to unexpected results:

js
Copy code
0 == false          // true
null == undefined  // true
=== (Strict Equality) ✅ Recommended
Purpose: Compares both value and data type.

js
Copy code
5 === "5" // false
No implicit type conversion occurs.

Examples:

js
Copy code
0 === false         // false
null === undefined // false
Comparison Table
Operator	Compares Value	Compares Type	Recommended
=	No	No	No
==	Yes	No	Avoid
===	Yes	Yes	Yes

Best Practice
Always use strict equality (===) unless type coercion is explicitly required.

js
Copy code
if (number % 2 === 0) {
  console.log("Even");
}
Summary
= assigns values

== compares values with type conversion

=== compares values and types (best practice)
