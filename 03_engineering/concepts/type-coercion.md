---
concept: type-coercion
discipline: engineering
language: javascript
status: learning
topic: language-basics
date_started: 2026-05-25
date_mastered:
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

I should always check for null, undefined or empty strings: 
```js
if (value !== null & value !== )
```

## My re-implementation from memory



## Where I got confused



## Mastery tests

- [ ] Wrote from blank file, from memory
- [ ] Explained each line out loud
- [ ] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |