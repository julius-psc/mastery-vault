---
concept: variables
discipline: engineering
language: javascript
status: learning
topic: language-basics
date_started: 2026-05-23
date_mastered:
tags:
  - "#status/learning"
  - "#disc/engineering"
related:
---

# Variables

## What it is

Variables in any coding language are used to store data values. They can be identified via unique names that are called identifiers. In JS, there are 3 different types of variables : 
- var can be declared, re-assigned and updated:
```js
var hello = 'Hello'
var hello = 'Z'
hello = 'Wagwan'
```
- let can be declared, updated but not re-assigned:
```js
let car = 'Red'
// let car = 'Blue' is NOT allowed
car = 'Yellow'
```
- const can be declared but not updated: 
```js
const dog = True
// dog = False is NOT allowed
```


Scope in JS is the context / environnement in which variables are relevant and can be used. For example, variables that are declared inside of a function cannot be used / aren't visible from outside of the function. In JS, there are 2 types of scopes which are Global (variables accessible in the full file / environnement) and Local (variables ONLY accessible inside of a specific function (called Lexical scope) or modules (called Modular scope)). 

Reassignement (Changing the variable) : When a variable is pointed to a new value
```js
let name = 'Joe'
name = 'Bob'
```

Mutation (Changing the data) : When you modify the inside of an existing object / array. 
```js
// const goals = 3
// goals = 2 is NOT allowed

const goals = [2, 3]
goals.push(5) // Here, the array's inside is changed

```

If multiple variables reference the same object, changing data in one object can make changes across a whole program
```js
const playerOne = {username: "Julius"}
const playerTwo = playerOne // In memory, both point to the same object in memory

playerTwo.username = "Poppy"

console.log(playerOne.username) // This would return 'Poppy'
```

Const is the default variable choice for developpers as variables rarely need to be reassigned after being declared initially. It is a convention to use `const` in top priority, then `let` and very rarely, if not ever, `var`.

## My re-implementation from memory

Today, I learnt about `var`, `const` and `let` and their differences :
- `var` : Declared, then can be re-assigned and mutated
- `const` : Declared, then can NOT be re-assigned or mutated
- `let` : Declared, then can be re-assigned but NOT mutated

I learnt about the different scopes. Scope is the environment / location in which variables can be accessible from. There are different types of scopes : Global (variables are accessible from everywhere in the file), Local (only in a specific bordered out environement), Modular (variables can only be accessed in the module) and Lexical (variables can only be accessed in functions)

Reassignement corresponds to changing the variable to a new one whereas mutation is changing the actual content of the object or the array. 

## Where I got confused



## Connects to

- [[ ]]

## Mastery tests

- [ ] Wrote from blank file, from memory
- [ ] Explained each line out loud
- [ ] Wrote three varied versions solving different problems
- [ ] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |