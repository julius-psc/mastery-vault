---
concept: destructuring
discipline: engineering
language: javascript
status: learning
topic: language-basics
date_started: 2026-06-14
date_mastered:
tags:
  - "#status/learning"
  - "#disc/engineering"
related:
---

# Destructuring

## What it is
Destructuring is a newly introduced syntax in ES6 (new JS update) that allows you to unpack and lighten values from heavier arrays or properties from objects into variables of their own = reduces repetition and improves readability.

- Object Destructuring: extracts values by targeting the keys of an object (key-value pairs)
```js 
const player = {name: "Julius", age: 19}

const {age, name} = player // Order doesn't matter

console.log(age) // 19
console.log(name) // Julius
```

- Array Destructuring: extracts values based on their index positions with square brackets.
```js
const ranks = ["Bronze", "Silver", "Gold"]

const [firstRank, ,thirdRank] = ranks // You can skip values

console.log(firstRank) // Bronze
console.log(thirdRank) // Gold
```

- Destructuring with default values: if a property or element doesn't exist, you can assign a fallback default value via the assignement operator =. However, default values are ONLY triggered if the property is missing or `undefined` (NOT `null`, `0` or `false` which will bypass the default value).

```js
// Objects w/ defaults
const settings = {theme: "light"};
const {theme, language="fr"} = settings // language defaults to "fr"

// Arrays w/ defaults
const numbers = [420]
const [player1, player2 = 0] = numbers // player2 defaults to 0

```

- Destu

## Where I got confused



## Mastery tests

- [ ] Wrote from blank file, from memory
- [ ] Explained each line out loud
- [ ] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |