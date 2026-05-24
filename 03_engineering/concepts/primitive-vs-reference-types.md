---
concept: primitive-vs-reference-types
discipline: engineering
language: javascript
status: mastered
topic: language-basics
date_started: 2026-05-24
date_mastered: 24/05/2026
tags:
  - "#status/learning"
  - "#disc/engineering"
related:
---
# Primitive vs Reference types

## What it is
Primitive data types (numbers, string, boolean, null, undefined, ...) are stored in a stack. A stack is a simple data structure that the computer uses to store and retrieve data quickly. A primitive data type on the stack can be found by the name of the variable that was used for declaration. When a primitive data type is created, data is added to the stack however it does NOT matter that both variables are assigned the same value.  
![[Screenshot 2026-05-24 at 10.37.04.png|470]]


Reference data types (objects, functions, collections, arrays, Dates, ...) are dynamic : they do not have a fixed size. The difference is that when you create a variable and assign it a reference data type, the computer does not store that data type into the variable (unlike primitive data types). Instead, the data type is stored in a heap and its pointer is stored in the stack. Now, when we assign a variable to an object, we actually assign the variable to the pointer that points to the object in the heap. If we create, like before, a second variable assigned to the first variable, this time a second object will NOT be created and instead both variables will point to the SAME object.
![[Screenshot 2026-05-24 at 11.24.51.png]]

```js
let object1 = {
name: 'Julius',
age: 19
}

let object2 = object1

object1.age = 18

console.log(object2) // Here the object2 will have the age 18 since object1 was updated and object2 points to the same object
```

## My re-implementation from memory
Today, I learnt about primitive and reference types and their differences. On the one hand, data types are strings, numbers, booleans, etc that can be assigned to variables and then stored in a stack. A stack is a data structure where data can be stored and retrieved. If a primitive data type is assigned to a variable, and then a second variable is declared and made equal to the first, in the stack there will be two identical data types made equal to two different variables. Reference data types on the other hand are objects, functions, arrays that don't have a defined size. Thus, when a data type is stored in a heap, a pointer pointing to that data type is stored in the stack. So a variable is actually assigned to an object's pointer. If a second variable is made equal to the first one, both variables will point to the object.
```js
let playerA = {username: "Julius", score: 10}
playerA.score = 20

let playerB = playerA

console.log(playerB.score) // This would return 20 since both players point to the same object
```

## Where I got confused
I've always had trouble learning about pointers and actual having a perspective of how it works. But thanks to this short FreeCodeCamp lesson: https://www.freecodecamp.org/news/primitive-vs-reference-data-types-in-javascript/, i've completely understood what pointers are.

## Mastery tests

- [x] Wrote from blank file, from memory
- [x] Explained each line out loud
- [x] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |