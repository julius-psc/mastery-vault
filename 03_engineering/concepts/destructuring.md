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

- Destructuring with Default Values: if a property or element doesn't exist, you can assign a fallback default value via the assignement operator =. However, default values are ONLY triggered if the property is missing or `undefined` (NOT `null`, `0` or `false` which will bypass the default value).

```js
// Objects w/ defaults
const settings = {theme: "light"};
const {theme, language="fr"} = settings // language defaults to "fr"

// Arrays w/ defaults
const numbers = [420]
const [player1, player2 = 0] = numbers // player2 defaults to 0

```

- Destructuring with Renaming (Alisasing) : this can be used when destructuring an object, the target variable can be renamed using a colon : which is useful for preventing variable clashes in the scope.
```js
const dbResp = {player_id = 2}

const {player_id: playerId} = dbResp

console.log(playerId) // 2
// console.log(player_id) would NOT work
```

- Combining Renaming + Default values : Placing the renaming colon first and then the default assignement.
```js
const info = {name: "Bob"}
const {name: userName, likes: likeCount = 0} = info

console.log(userName) // Bob
console.log(likes) // 0
```

- Nested Destructuring : Pluck data by destructuring nested objects in complex API
```js
const student = {
	first_name: "Julius",
	address {
		city: "Caen",
		postcode: 14000
	}
}

const { first_name, address: {city} } = student // address is NOT a variable
console.log(first_name) // Julius
console.log(city) // Caen
```

- Destructuring in function parameters : Instead of passing an entire object or array and then having to type `object.property` repeatedly inside the function, you can destructure parameters directly inside in the `()` of the function.
```js
const article = {reference_no = 3, price = 50}

// Use of default value
function calcTot({price, tva = 0.4}) {
	return price + (price * tva)
}

calcTot(article) // returns 70
```

- The Optional Object Fallback trick : If I call a function that destructures an object with no arguments, I will get a TypeError `Cannot destructure property of 'undefined'` which can be fixed by assigning an empty object default to the parameter block. 
```js
function displayPlayer({username="John Doe", rank="Noob"} = {}) {
	console.log(`${username} is a ${rank}`)
}

displayPlayer() // This should return John Doe is a Noob
```


## Mastery tests

- [ ] Wrote from blank file, from memory
- [ ] Explained each line out loud
- [ ] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |