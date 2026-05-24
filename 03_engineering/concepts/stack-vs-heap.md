---
concept: stack-vs-heap
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

# Stack vs Heap

## What it is

The stack is a location of memory where temporary variables are stored. It works in a LIFO (Last In First Out) manner which means that the item that is last stored is the first one to be taken out again. The characteristics of the stack are : 
- Fixed Size : The stack has a limited size so if too much data is pushed to it, this can lead to a stack overflow
- Fast Access : Variables on the stack are quick to allocate and deallocate because memory is managed by moving a pointer up and down the stack. 
- Function Scope : Stack memory is tied to function calls. When a function is called, its variables are pushed onto the stack and when that function returns, the variables are removed which frees up memory.
In JS, primitive data types and references to objects are stored on the stack
```js
function add(a, b) {
	let sum = a + b // 'a', 'b' and sum are stored on the stack
return sum; // they are removed from the stack after return
}
```


The heap is a location of memory that is used for dynamic memory allocation. It is free-form which allows for allocation and deallocation of blocks of memory at any time.  The characteristics of the heap are : 
- Dynamic Size : The heap has a much larger and flexible memory. 
- Slower Access : Accessing data on the heap is slower than accessing on a stack which can be due to having to find free space for new allocations of memory. 
- Garbage collection : Unused memory in JS is automatically retrieved which helps minimize memory leaks but can introduce slowness due to garbage retrieval cycles. 
In JS, reference data types are stored in the heap. 
```js
let person = {
	name: 'Bobby',
	age: 13
} // Here, in the stack, the variable person actually stores a pointer to the object stored in the HEAP.
```

Variables on the stack have a short lifetime by existing SOLELY within the function scope. Variables on the heap can continue to live as long as they are referenced which allows more complex data structures and longer lifetimes. 

## My re-implementation from memory

Today I learnt the difference between the stack and the heap. Both are regions of the memory however both serve different purposes. The stack is a more fast and efficient 
region of memory where primitive data types and references to primitive data types are stored. It operates in a LIFO manner (Last In First Out) which means the last piece of data that is stored in the stack is the first one to be taken out. Thus, finding via the stack is a lot more quick however memory size is fixed which means too much data can cause a stack overflow. The heap is a more dynamic region of memory where reference data types are stored. Here, memory size is NOT fixed and is dynamic meaning more complex and long data structures can be stored such as objects. The heap does not operate in a LIFO manner which makes indexing longer. It is free-form which allows for allocation and de-allocation at any given time. A difference between the stack and the heap is that data types that live on the stack have a SHORT lifetime that lives in the function scope whereas data types that live on the heap live on as long as they are referenced which allows more complex data structures.

## Mastery tests

- [x] Wrote from blank file, from memory
- [x] Explained each line out loud
- [x] Date mastered: 

## Re-test history

| Date | Notes |
|------|-------|
| | |