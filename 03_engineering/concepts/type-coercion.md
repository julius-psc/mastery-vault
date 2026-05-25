---
concept: type-coercion
discipline: engineering
language: javascript
status: mastered
topic: language-basics
date_started: 2026-05-25
date_mastered: 25/05/2026
tags:
  - "#status/learning"
  - "#disc/engineering"
related:
---

# Type Coercion

## What it is
Type Coercion is when JS automatically converts one type of value into another without user intervention. There are 3 types of coercion : String, Number and Boolean
```js
console.log(5 + "10") // Output : 510
```

- String Coercion : Occurs when the string is combined with a non-string via (+). JS converts numbers and booleans into strings before concatentation.
```js
console.log(5 + "2") // Output : "52"
console.log("40" + true) // Output : "40true"
```
- Number Coercion : JS converts the string into a number
```js
console.log("5" - 2) // Output : 3
console.log("5" * 2) // Output : 10
```
- Boolean Coercion : JS treats the true value as '1' and false as '0'
```js
console.log(Boolean("hi")) // Output : true
console.log(Boolean(0)) // Output : false
```

To compare different data types, if I use the comparaison operator (= =), coercion will be allowed which will cause issues. The fix is to use the strict equality (= = =) operator.
```js
console.log(5 == "5") // Output : true
console.log(5 === "5") // Output : false (CORRECT)
```

I should use explicit manual conversion to avoid chances of any errors in my code. Example : `console.log(Number("123"))`

I should always check for null, undefined or empty strings so that only non-null and defined values are allowed.
```js
if (value !== null & value !== undefined) {
	console.log("The value exists")
}
```

To correctly convert numerical values part of a string, I should use `parseInt` and `parseFloat`. 
```js
console.log(parseInt("3jdqwlkdjqkwl")) // Output : 3
```

I should use the the `isNan()` method to check if a number is a NaN instead of comparing it. 
```js
if (isNaN(value)) {
	console.log("Not a number")
}
```
## My re-implementation from memory
Type coercion happens when JS automatically converts a data type into another. There are 3 different type coercions : String, Number and Boolean. Errors can happen due to automatic type coercion and so I should apply the following steps : I should use the strict equality operator (= = =) instead of (= =). I should use explicit manual conversion when I want to change a data type into another to avoid bugs further down the road. To fetch the number in a string, I should use parseInt or parseFloat and to check that a number is a NaN, I should use the isNaN() method.

## Mastery tests

- [x] Wrote from blank file, from memory
- [x] Explained each line out loud
- [x] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |