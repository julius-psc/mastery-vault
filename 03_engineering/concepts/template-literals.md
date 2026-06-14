---
concept: template-literals
discipline: engineering
language: javascript
status: learning
topic: language-basics
date_started: 2026-06-14
date_mastered: 14/06/2026
tags:
  - "#status/learning"
  - "#disc/engineering"
related:
---

# Template Literals

## What it is
Template literals are JS string literals (which means characters enclosed by '' or "") that allow for string interpolation and multi-line strings. They are enclosed by backticks.

- String interpolation : embedding variables and expressions directly into the string
```js
const user = 'Julius'
const age = 19

const message = `Hey ${user}, you are going to be ${age + 1} next year.`
console.log(message)
```

- Multi-line strings : any identation or newline chars typed between the backticks will be preserved and displayed.
```js
const poem = `Roses are red,
Violets are blue, 
You smell like poo.`

// So here, the poem would have the identation as of a poem.
```

Tagged templates are an advanced way to use template literals via a `tag` function. It's a way of sending a template literal through a filter function before it is turned into a regular string. 
```js
function ban(strings, value) {
	if (value == "not-allowed") {
		value = "ILLEGAL X"
	}
	
	return `${strings[0]}${value}${strings[1]}`
}

const statement = "not-allowed"

const message = ban`I can't tell you what it is because it is ${statement}.`

console.log(message)

// I can't tell you what it is because it is ILLEGAL X.
```

## Where I got confused
I didn't quite understand what a tagged template function is but now I have completely understood. It's a function in which a template literal is passed to where it is filtered before being returned into a regular string.


## Mastery tests

- [x] Wrote from blank file, from memory
- [x] Explained each line out loud
- [ ] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |