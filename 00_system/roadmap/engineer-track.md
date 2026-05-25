# Engineering

**Daily block:** 2 hours, every day, morning 
**Stack:** JavaScript → TypeScript → DOM → React → Rust → Swift 
**Rule:** Research every concept yourself. No AI-generated code during learning. Mastery bar on every concept before moving on.

---

## PHASE 1 — Months 1-3: JavaScript, TypeScript, DOM

---

### Stage 0: JavaScript Fundamentals

**Duration:** Weeks 1-6 **Resource:** javascript.info — work through chapter by chapter **Practice:** Exercism JavaScript track, matched to each sub-stage

---

#### 0.1 Language Basics

- `var`, `let`, `const` — scoping rules, reassignment vs mutation, why `const` is the default
- Primitive types vs reference types
- Memory model: stack vs heap implications
- Type coercion: == or ===
- The complete falsy list: `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, `NaN`
- Truthy edge cases: `"0"`, `"false"`, `[]`, `{}`
- Template literals
- Tagged template literals
- Destructuring: object, array, nested, with defaults, with rename, in function parameters
- Spread operator in arrays, objects, function calls
- Rest operator in destructuring and function parameters
- Optional chaining (`?.`) including with function calls and array access
- Nullish coalescing (`??`)
- Logical assignment operators (`||=`, `&&=`, `??=`)
- Short-circuit evaluation patterns
- Ternary expressions and when they hurt readability

---

#### 0.2 Functions

- Function declarations vs function expressions vs arrow functions
- Hoisting differences between declarations and expressions
- Arrow function specifics: no own `this`, no `arguments`, can't be constructors
- Parameters: default, rest, destructured
- Return values and implicit returns
- First-class functions (functions as values)
- Higher-order functions
- Pure functions vs side effects
- IIFEs and module patterns
- Function composition: `compose` and `pipe` implementations
- Currying and partial application
- Recursion and when to use it

---

#### 0.3 Scope, Hoisting, Closures

**Extra time here — this is the foundation of most JavaScript patterns**

- Lexical scope
- The scope chain
- Hoisting of `var`, `let`, `const`, function declarations, class declarations
- The temporal dead zone
- Function scope vs block scope
- **Closures** — the foundation of huge swaths of JavaScript
- Closure patterns: counters, private state, function factories, memoization, partial application
- Module pattern via closures
- The classic `for` loop with `setTimeout` and why `let` fixed it
- Closures and garbage collection

---

#### 0.4 The `this` Keyword

- `this` in global context (window vs `undefined` in strict mode)
- `this` in regular function calls
- `this` in method calls
- `this` in arrow functions (lexical binding, not bound)
- Explicit binding: `call`, `apply`, `bind`
- Differences and use cases for each
- `new` binding
- Precedence: new > explicit > implicit > default
- `this` in event handlers
- `this` in class methods

---

#### 0.5 Objects and Prototypes

- Object literals
- Shorthand property names and computed property names
- Property descriptors: `writable`, `enumerable`, `configurable`, `value`, `get`, `set`
- `Object.defineProperty`, `Object.defineProperties`
- Getters and setters
- The prototype chain
- `__proto__` vs `Object.getPrototypeOf` vs `Object.setPrototypeOf`
- `Object.create`
- Constructor functions and the `prototype` property
- ES6 classes — what they desugar to
- Class fields, static methods, private fields (`#`), private methods
- Inheritance via `extends`
- `super` keyword in constructors and methods
- `instanceof` and how it walks the prototype chain
- `Object.assign`, structured clone, spread for shallow vs deep copying
- Object methods: `keys`, `values`, `entries`, `fromEntries`, `freeze`, `isFrozen`

---

#### 0.6 Arrays and Iteration

- Array creation: literal, `Array.of`, `Array.from`, `new Array(n)`
- `map`, `filter`, `reduce`, `forEach`, `find`, `findIndex`, `findLast`, `some`, `every`
- `flat`, `flatMap`
- `sort` (comparator function, in-place mutation)
- `slice` vs `splice`
- `indexOf`, `lastIndexOf`, `includes`
- `concat`, `join`
- When to reach for `reduce` vs a loop
- `for...of` vs `for...in` vs classic `for`
- The iteration protocols: iterable, iterator, async iterator
- `Symbol.iterator` and building custom iterables
- Generators and `yield`
- `yield*` for delegation
- Async generators

---

#### 0.7 Asynchronous JavaScript

**Master deeply — the most important stage in Phase 1**

- The runtime model: call stack, web APIs, task queue, microtask queue
- The event loop: tick, render, idle
- Synchronous vs asynchronous execution
- Callbacks: callback hell, error-first conventions
- **Promises** — the state machine: pending, fulfilled, rejected
- Promise resolution: `.then`, `.catch`, `.finally`
- Promise chaining and return values
- Error propagation through promise chains
- `Promise.all` — fails fast on first rejection
- `Promise.allSettled` — always resolves with array of outcomes
- `Promise.race` — first to settle wins
- `Promise.any` — first to fulfill wins, rejects only if all reject
- `Promise.resolve` and `Promise.reject` for already-resolved values
- `async`/`await` and how it desugars to Promises
- `async` functions always return a Promise
- Error handling with `try`/`catch` in async functions
- `await` on non-Promise values
- Common pitfalls: forgotten `await`, `await` in loops (use `Promise.all` instead), unhandled rejections
- `setTimeout`, `setInterval`, `clearTimeout`, `clearInterval`
- `requestAnimationFrame` for visual updates
- `queueMicrotask` vs `setTimeout(0)` vs `requestAnimationFrame`
- The microtask queue is drained between every task

---

#### 0.8 Modules

- ES modules: `import`, `export`
- Named exports vs default exports
- `import * as ns`
- Dynamic imports with `await import()`
- Module resolution
- The difference between CommonJS (`require`) and ESM
- Module caching
- npm and `package.json` basics
- Semver
- `dependencies` vs `devDependencies` vs `peerDependencies`
- Conceptual understanding of bundlers

---

#### 0.9 Error Handling

- `Error` and its built-in subclasses: `TypeError`, `RangeError`, `SyntaxError`, etc.
- `try`/`catch`/`finally`
- Throwing errors
- Custom error classes extending `Error`
- `Error.cause` for chained errors
- Error propagation through synchronous and asynchronous code
- The Result pattern (concept — revisited in Rust)

---

#### 0.10 Capstone: Promise from Scratch

**The single highest-value exercise in JavaScript education**

- Read the Promises/A+ spec (short — read it fully)
- Implement a `MyPromise` class from scratch
- Implement: `then`, `catch`, `finally`, static `resolve`, `reject`, `all`, `allSettled`, `race`, `any`
- Run the official Promises/A+ test suite against your implementation
- When this passes, you understand async JavaScript permanently

---

### Stage 1: TypeScript

**Duration:** Weeks 7-10 **Resource:** Matt Pocock's totaltypescript.com (free Beginner's TypeScript first) + official TypeScript handbook **Practice:** type-challenges repo — warm and easy tiers daily

---

#### 1.1 Type Basics

- Primitives: `string`, `number`, `boolean`, `null`, `undefined`, `bigint`, `symbol`, `void`
- `any` — what it does and why to avoid it
- `unknown` — safe `any`, requires narrowing before use
- `never` — exhaustiveness, impossible states
- Type annotations on variables, parameters, return values
- Type inference — when to annotate, when to let TS infer
- Literal types
- Type widening and narrowing
- Union types (`A | B`)
- Intersection types (`A & B`)
- Type aliases vs interfaces — when each is appropriate
- Interface declaration merging (and when it bites you)

---

#### 1.2 Objects, Arrays, Tuples

- Object type literal
- Optional properties (`?`)
- Readonly properties
- Index signatures
- Tuples
- Labeled tuple elements
- Variadic tuples with spread
- Array vs ReadonlyArray
- `as const` for literal narrowing

---

#### 1.3 Functions in TypeScript

- Function type signatures
- Optional and default parameters
- Rest parameters with tuple types
- Function overloads (declaration order matters)
- Generic functions
- Higher-order function types
- `void` vs `undefined` return type
- Contextual typing
- `this` parameter typing

---

#### 1.4 Type Narrowing

**Master deeply — this is core TypeScript thinking**

- `typeof` guards
- `instanceof` guards
- Truthy/falsy narrowing
- Equality narrowing
- `in` operator narrowing
- Discriminated unions
- The `kind` / `type` / `_tag` discriminator convention
- User-defined type predicates (`x is T`)
- Assertion functions (`asserts x is T`)
- Exhaustiveness checking with `never` in `switch` statements

---

#### 1.5 Generics

- Generic functions
- Generic constraints (`extends`)
- Default type parameters
- Generic classes and interfaces
- `keyof` operator
- Indexed access types (`T[K]`)
- Mapping over object types
- Generic inference and when it fails

---

#### 1.6 Advanced Types

- Conditional types (`T extends U ? X : Y`)
- Distributive conditional types
- The `infer` keyword
- Mapped types (`{ [K in keyof T]: ... }`)
- Mapped type modifiers (`+readonly`, `-readonly`, `+?`, `-?`)
- Key remapping with `as`
- Template literal types
- String manipulation types: `Uppercase`, `Lowercase`, `Capitalize`, `Uncapitalize`
- Built-in utility types: `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`, `Exclude`, `Extract`, `NonNullable`, `Parameters`, `ReturnType`, `ConstructorParameters`, `InstanceType`, `Awaited`
- Recursive types

---

#### 1.7 Modules and Declarations

- Importing/exporting types
- `import type` and `export type`
- Ambient declarations (`declare`)
- `.d.ts` files
- Triple-slash directives (legacy awareness)
- Module augmentation

---

#### 1.8 Configuration

- `tsconfig.json` — every important flag
- `strict` and what it enables
- `target`, `module`, `moduleResolution`, `lib`
- `paths` and path aliases
- `verbatimModuleSyntax`
- `noUncheckedIndexedAccess`
- `exactOptionalPropertyTypes`

---

#### 1.9 Capstones

**Type-challenges:**

- All warm tier
- All easy tier
- At least 5 medium tier

**Typed fetch wrapper from scratch (~100 lines):**

- Generic over response type
- Discriminated union return type for success/error
- AbortController support
- Properly typed headers including auth
- Timeout handling
- This is the Revolut interview question — solved permanently

---

### Stage 2: The Browser and the DOM

**Duration:** Weeks 11-13 **Resource:** MDN Web Platform docs, read like a textbook not a reference **Watch:** Jake Archibald's "In The Loop" YouTube talk (30 min, watch 3 times)

---

#### 2.1 The DOM as Data Structure

- The document tree
- Node types: Element, Text, Comment, Document
- `querySelector`, `querySelectorAll`, `getElementById`, `getElementsByClassName`, `getElementsByTagName`
- NodeList vs HTMLCollection (live vs static — understand the difference)
- Element creation: `createElement`, `createTextNode`
- Inserting: `appendChild`, `insertBefore`, `append`, `prepend`, `before`, `after`, `replaceWith`
- Removing: `removeChild`, `remove`
- Cloning: `cloneNode`
- `textContent` vs `innerText` vs `innerHTML`
- XSS implications of `innerHTML`
- `insertAdjacentHTML` and its positions
- `dataset` and `data-*` attributes
- `classList`: `add`, `remove`, `toggle`, `contains`, `replace`
- `getAttribute`, `setAttribute`, `removeAttribute`
- Property vs attribute (the `value` attribute gotcha)

---

#### 2.2 Events

**Master event delegation — changes how you think about event handling**

- The event flow: capture → target → bubble
- `addEventListener` options object: `capture`, `once`, `passive`, `signal`
- Why you never use `onclick=` inline in HTML
- Event delegation patterns
- `event.target` vs `event.currentTarget`
- `event.preventDefault()`, `event.stopPropagation()`, `event.stopImmediatePropagation()`
- Event types: mouse, pointer, touch, keyboard, focus, form, drag, custom
- The pointer event model (preferred over separate mouse + touch)
- Keyboard events: `key` vs `code`, modifier keys
- Form events: `input`, `change`, `submit`, `reset`, `focus`, `blur`
- Custom events with `CustomEvent`
- Dispatching events
- Passive event listeners and scroll performance
- AbortController for removing listeners declaratively

---

#### 2.3 Async Browser APIs

- `fetch` in depth
- Request options: `method`, `headers`, `body`, `credentials`, `mode`, `cache`, `redirect`, `signal`
- Headers API: `Headers` constructor, `append`, `set`, `get`
- Response object: `status`, `statusText`, `ok`, `headers`, `url`, `body`
- Parsing: `.json()`, `.text()`, `.blob()`, `.arrayBuffer()`, `.formData()`
- Streaming responses (concept awareness)
- AbortController and AbortSignal
- `AbortSignal.timeout`
- `AbortSignal.any`
- Common HTTP status codes and semantic meaning
- HTTP methods and their idempotency
- CORS: same-origin, cross-origin, simple vs preflight requests
- The `Origin` and `Access-Control-*` headers
- Credentials and cookies in CORS
- **Habit: read the Network tab in DevTools after every fetch call**

---

#### 2.4 The Rendering Pipeline

**Critical for design engineering — this is the substrate of all motion work**

- Parse → DOM tree → CSSOM → render tree → layout → paint → composite
- What triggers reflow (layout recalculation)
- What triggers repaint
- What triggers composite-only updates (cheapest)
- The compositor thread
- Why `transform` and `opacity` are special (compositor thread only)
- `will-change` and its costs
- `contain` property for scoping reflows
- The Performance tab in DevTools — use it on real pages
- Layers and the layer panel
- Frame budget at 60fps (16.67ms per frame) and 120fps (8.33ms)
- Long tasks and the Long Task API

---

#### 2.5 The Event Loop in the Browser

- Tasks vs microtasks (revisit from 0.7 with browser context)
- Where rendering fits in the loop
- Why long synchronous work blocks the UI
- `queueMicrotask` vs `setTimeout(0)` vs `requestAnimationFrame`
- `requestIdleCallback` and when it's appropriate
- The render steps: style → layout → paint → composite
- Animation frame scheduling

---

#### 2.6 Observers

- `IntersectionObserver` — viewport visibility
- `IntersectionObserver` options: `root`, `rootMargin`, `threshold`
- `MutationObserver` — DOM changes
- `ResizeObserver` — element size changes
- `PerformanceObserver` — performance entries
- Observer cleanup with `.disconnect()`

---

#### 2.7 Forms

- Form elements: `input`, `textarea`, `select`, `button`
- Input types and their semantic meaning
- Form values and the `FormData` API
- HTML5 validation attributes
- Custom validation with `setCustomValidity`
- `:valid` and `:invalid` CSS pseudo-classes
- The submit event and `preventDefault`
- File inputs and the File API
- Working with `FileReader`

---

#### 2.8 Storage

- `localStorage` vs `sessionStorage`
- The 5-10MB limit
- Synchronous nature and blocking implications
- `JSON.stringify` / `JSON.parse` patterns
- Storage events for cross-tab sync
- Cookies — when they're appropriate vs localStorage
- IndexedDB (awareness — async, structured, much larger limits)
- The Cache API (concept)

---

#### 2.9 Capstones

**Build all of these in vanilla JS — no framework**

1. Todo list with `localStorage` persistence
2. Search input with debouncing and `AbortController` for stale request cancellation
3. Drag-and-drop reorderable list
4. Modal with full focus trap (teaches accessibility)
5. Infinite scroll list with `IntersectionObserver`
6. Toast notification system with queue management

---

### Phase 1 Engineering Milestones (end of month 3)

- [ ] Stage 0 complete — every sub-concept has passed the three mastery tests
- [ ] Stage 1 complete — type-challenges warm + easy done, fetch wrapper built
- [ ] Stage 2 complete — all 6 vanilla JS capstones built and working
- [ ] Promise-from-scratch passes the official test suite
- [ ] Can explain closures, the event loop, and prototypes without notes

---

## PHASE 2 — Months 4-6: React, Rust, Swift

---

### Stage 3: React

**Duration:** Weeks 14-17 **Resource:** react.dev — work through "Learn" section completely, do every exercise **Rebuild:** Every Stage 2 vanilla capstone in React after completing Stage 3

---

#### 3.1 Mental Model

- What React is: a library producing a tree of elements you re-render efficiently
- JSX and how it compiles (`React.createElement` / `jsx-runtime`)
- The virtual DOM and reconciliation
- Fiber architecture (concept — don't go deep yet)
- Components as functions
- Why React exists: the problem with direct DOM manipulation at scale

---

#### 3.2 Components and Props

- Function components
- Props as function arguments
- Prop destructuring
- Children and the `children` prop
- Render props (legacy but worth understanding)
- Conditional rendering patterns: `&&`, ternary, early return
- Lists and keys
- Why keys matter — connect to reconciliation algorithm
- Fragments and the `<></>` shorthand
- Portals and when to use them

---

#### 3.3 State and Effects

**Spend the most time here of any React section**

- `useState` — when state updates, what triggers re-renders
- State updater functions vs values (functional updates)
- Lazy initial state
- State batching in React 18+
- `useReducer` — when to reach for it over `useState`
- `useEffect` and the dependency array
- The mental model: effects synchronize with external systems
- Read "You Might Not Need an Effect" on react.dev (essential)
- Cleanup functions
- Strict mode and double-invocation in development
- `useLayoutEffect` vs `useEffect` — when each fires
- `useInsertionEffect` (rarely needed, awareness only)

---

#### 3.4 Refs and the DOM

- `useRef` for DOM access
- `useRef` for mutable values that don't trigger re-renders
- When to use ref vs state (genuinely separate use cases)
- `forwardRef` (legacy in React 19+, awareness)
- The new `ref` as a prop in React 19+
- `useImperativeHandle`

---

#### 3.5 Performance and Memoization

- When components re-render and why
- The re-render cascade
- `useMemo` — when it's worth it (less often than you think)
- `useCallback` — when it's worth it
- `React.memo`
- The cost of premature optimization
- React DevTools profiler — use it on your capstones

---

#### 3.6 Context

- `useContext`
- When context is appropriate vs prop drilling vs state library
- Re-render pitfalls with context
- Splitting contexts (state vs dispatch pattern)
- Provider patterns

---

#### 3.7 Custom Hooks

- Building custom hooks
- The rules of hooks and why they exist
- Composition patterns
- Naming conventions
- When a custom hook is the wrong abstraction

---

#### 3.8 Forms in React

- Controlled vs uncontrolled inputs
- When to use each
- `useFormState` and form actions (React 19+)
- Working with refs for uncontrolled forms
- Libraries: react-hook-form (concept — know when to reach for it)

---

#### 3.9 Data Fetching Patterns

- Manual fetching with `useEffect` and why it's tricky
- Loading and error states
- Cancellation with `AbortController` in effects
- Race conditions in async effects (and how to prevent them)
- The `use` hook for Promises (React 19+)
- When to reach for TanStack Query (concept — understand the problem it solves)

---

#### 3.10 Capstones

**Rebuild all Stage 2 vanilla capstones in React.** Notice exactly what React does for you and what you still have to do yourself.

**Build a typed generic `useQuery`-like hook from scratch (~200 lines):**

- Caching by key
- Loading state
- Error state
- Refetching
- Deduplication of in-flight requests
- This is the exercise that makes React data fetching permanent knowledge

---

### Stage 4: Rust Fundamentals

**Duration:** Weeks 18-22 **Resource:** The Rust Programming Language book (doc.rust-lang.org/book) — all chapters **Practice:** Rustlings (official Rust exercises repo) — one chapter per day

---

#### 4.1 Setup and Tooling

- Installing Rust via rustup
- cargo: `new`, `build`, `run`, `test`, `check`, `clippy`, `fmt`
- The module system: `mod`, `mod.rs`, `lib.rs`, `main.rs`
- `Cargo.toml` and dependency management

---

#### 4.2 Ownership

**The famous wall — sit with it. Don't rush past it.**

- Stack vs heap (understand the physical difference)
- The three ownership rules
- Move semantics
- The `Copy` trait
- The `Clone` trait
- The borrow checker as a teacher, not an obstacle

---

#### 4.3 References and Borrowing

- Immutable references (`&T`)
- Mutable references (`&mut T`)
- The borrowing rules: many readers OR one writer, never both simultaneously
- Reference scope and non-lexical lifetimes
- Dereferencing with `*`
- Slices: `&[T]`, `&str`

---

#### 4.4 Lifetimes

- Why lifetimes exist (dangling reference prevention)
- Lifetime annotations syntax
- The three lifetime elision rules
- The `'static` lifetime
- Lifetimes in structs
- Lifetimes in function signatures

---

#### 4.5 Type System

- Primitive types
- Tuples and arrays
- Structs: regular, tuple, unit
- `impl` blocks
- Methods vs associated functions
- **Enums — master deeply, Rust enums are the heart of the language**
- Enum variants with data (can hold any type)
- Pattern matching with `match`
- Match exhaustiveness (compiler enforces)
- `if let`, `while let`, `let else`

---

#### 4.6 Error Handling

- `Result<T, E>` and `Option<T>`
- The `?` operator
- Custom error types
- `From` impls for error conversion
- `panic!` vs recoverable errors
- The `thiserror` crate (for libraries)
- The `anyhow` crate (for applications)

---

#### 4.7 Traits and Generics

- Defining traits
- Implementing traits
- Default methods
- Trait bounds
- Generic functions and structs
- Trait objects (`dyn Trait`)
- Static vs dynamic dispatch
- The `From` / `Into` traits
- The `Display` / `Debug` traits
- The `PartialEq` / `Eq` / `PartialOrd` / `Ord` traits
- Derive macros (`#[derive(...)]`)

---

#### 4.8 Collections

- `Vec<T>`
- `String` and `&str` (and the difference)
- `HashMap<K, V>`
- `HashSet<T>`
- `BTreeMap`, `BTreeSet`
- The iterator trait
- Common iterator methods: `map`, `filter`, `fold`, `collect`, `enumerate`, `zip`, `chain`, `flatten`
- Iterator adapters vs consumers (lazy vs eager)

---

#### 4.9 Modules, Crates, Workspaces

- The module system in depth
- Visibility: `pub`, `pub(crate)`, `pub(super)`
- Re-exports
- Workspaces for multi-crate projects

---

#### 4.10 Async Basics (light touch — Rust async comes back in Phase 3)

- `async`/`await` syntax
- Futures conceptually
- Tokio runtime introduction
- `tokio::spawn`

---

#### Capstone

- Complete all Rustlings exercises
- Build 3 small CLI tools in pure Rust:
    1. A file watcher that prints changes to stdout
    2. A hash calculator (MD5/SHA256) for files
    3. A markdown-to-HTML converter

---

### Stage 5: Swift Fundamentals

**Duration:** Weeks 23-25 **Resource:** The Swift Programming Language book (swift.org — free) + Paul Hudson's Hacking with Swift for SwiftUI

---

#### 5.1 Language Basics

- `var` vs `let`
- Type inference and explicit annotations
- Optionals: `?`, `!`, `if let`, `guard let`, `??`
- Value types vs reference types (struct vs class — the key distinction)
- Closures
- Functions and methods

---

#### 5.2 Type System

- Protocols
- Protocol extensions
- Generics
- Associated types in protocols
- Opaque types (`some Protocol`)
- Existentials (`any Protocol`)

---

#### 5.3 Pattern Matching

- `switch` statements (exhaustive by default)
- `if case`, `for case`, `guard case`
- Enum cases with associated values
- Where clauses in patterns

---

#### 5.4 Memory and Concurrency

- ARC (Automatic Reference Counting) basics
- Strong, weak, unowned references
- Retain cycles and how to prevent them
- Capture lists in closures
- Structured concurrency: `async`/`await`, `Task`, `TaskGroup`
- Actors
- `@MainActor` for UI updates

---

#### 5.5 SwiftUI Basics

- The `View` protocol
- Property wrappers: `@State`, `@Binding`, `@ObservedObject`, `@StateObject`, `@EnvironmentObject`
- View modifiers
- Layout containers: `HStack`, `VStack`, `ZStack`, `Grid`
- Animation basics
- Navigation with `NavigationStack`

---

#### Capstone

- Build a small native menu bar app in pure SwiftUI
- It should: live in the menu bar, open a popover, have at least one stateful interaction

---

### Phase 2 Engineering Milestones (end of month 6)

- [ ] Stage 3 complete — all React capstones built, `useQuery` hook works
- [ ] Stage 4 complete — Rustlings done, 3 CLI tools shipped
- [ ] Stage 5 complete — SwiftUI menu bar app running natively
- [ ] Can explain the React re-render model without notes
- [ ] Can explain Rust ownership without notes

---

## PHASE 3 — Months 7-9: Rust Depth + Application Project

---

### Stage 6: Rust Depth

**Duration:** Weeks 27-30 **Resource:** Rust for Rustaceans by Jon Gjengset + his "Crust of Rust" YouTube series

---

#### 6.1 Advanced Ownership Patterns

- `Rc<T>` for shared ownership (single-threaded)
- `Arc<T>` for shared ownership (multi-threaded)
- `RefCell<T>` for interior mutability (single-threaded)
- `Mutex<T>` for interior mutability (multi-threaded)
- `RwLock<T>` for many-reader-one-writer
- When each is appropriate
- The `Send` and `Sync` marker traits
- Sharing data across threads safely

---

#### 6.2 Advanced Traits

- Associated types vs generic parameters (when to use which)
- Default associated types
- Trait inheritance (`trait B: A`)
- Marker traits
- Operator overloading
- The orphan rule and the newtype pattern

---

#### 6.3 Async in Depth

- Futures and the `Future` trait
- Poll-based futures internals
- Pin and Unpin
- Tokio runtime internals
- Channels: `mpsc`, `oneshot`, `broadcast`, `watch`
- Spawning, joining, cancellation
- Async traits (native or via `async-trait` crate)
- Streams

---

#### 6.4 Macros

- Declarative macros (`macro_rules!`)
- Procedural macros (concept — use existing ones, don't write yet)
- Common useful macros in the ecosystem
- The `derive` macro mechanism

---

#### 6.5 Common Patterns

- Builder pattern
- Newtype pattern
- Typestate pattern (encode state in types)
- Error handling strategy: `thiserror` for libraries, `anyhow` for applications

---

#### Capstone

- Build one substantial async CLI tool (parallel file downloader, real-time log tailer, or benchmarking tool)
- Read Rust for Rustaceans cover to cover
- Watch all "Crust of Rust" episodes

---

### Stage 7: Application Project

**Duration:** Weeks 31-39 **This is Flowivate, or whatever you decide to build. macOS native, Tauri + Swift.**

---

#### Principles

- **Design-first every slice.** Spec in Figma before writing one line of code.
- **Vertical slices.** Each slice ships end-to-end before starting the next.
- **Ship the design system in code first.** Tokens, typography, components before features.
- **Each slice introduces one new technical concept.** Don't learn and build simultaneously.
- **No AI code generation.** Use AI for conceptual questions only.

---

#### Suggested Slice Order

1. **Design system in code** — tokens (OKLCH color, 8pt spacing, type scale), Radix UI primitives as base, full component library
2. **Static screens** — all screens designed and built with no interactivity
3. **Local state and interactions** — forms, toggles, selection, keyboard navigation
4. **Persistence** — localStorage or SQLite via Tauri's `tauri-plugin-sql`
5. **External API integration** — use your typed fetch wrapper from Stage 1.9
6. **Tauri shell** — wrap as native macOS app, understand the IPC model fully
7. **First Rust feature** — global keyboard shortcut, file system watcher, native notification
8. **Advanced state** — optimistic updates with rollback on failure
9. **Swift integration** — menu bar UI, deeper native macOS APIs
10. **Motion polish** — every interaction reviewed for craft, nothing left unanimated that should be

---

### Phase 3 Engineering Milestones (end of month 9)

- [ ] Rust depth complete — async CLI tool shipped
- [ ] Application project: slices 1-7 shipped
- [ ] App runs natively on macOS
- [ ] Rust and Swift integrated at the Tauri boundary
- [ ] Design system built entirely in code

---

## PHASE 4 — Months 10-12: Application Project Polish + Portfolio Site

---

### Application Project: Final Polish

- Slice 8: Advanced state (optimistic updates + rollback)
- Slice 9: Swift integration depth (menu bar, native notifications, Spotlight)
- Slice 10: Performance work — measure with Instruments, fix real bottlenecks
- Slice 11: Motion polish — every interaction reviewed, nothing left
- Write the full case study (this becomes the hero portfolio piece)

---

### Portfolio Site Engineering

**Stack:** Next.js, deployed to Vercel

**Requirements:**

- Lighthouse 100 on performance
- WCAG 2.2 AA accessibility minimum
- Mobile-first, perfect at every breakpoint
- Motion as primary design material (not decoration)
- Custom design — no template

**Features to build:**

- Homepage with animated hero
- Work section (case studies)
- Writing section (blog with MDX)
- About page
- Optional: playground/lab for motion experiments
- Optional: live learning garden (exported from Obsidian)

---

### Phase 4 Engineering Milestones (end of month 12)

- [ ] Application project fully shipped and publicly accessible
- [ ] Portfolio site live at custom domain
- [ ] Lighthouse 100 across all pages
- [ ] All case studies published
- [ ] 15+ essays published

---

## Application Targets

### Tier 1 — Dream

Linear, Vercel, Raycast, Cursor, Liveblocks, Framer, Arc / Browser Company

### Tier 2 — Strong

Stripe, Figma, Notion, Mercury, Ramp, Rippling, Webflow, Anthropic design team

### Tier 3 — Volume

Strong YC W26/S26 product-led startups, well-funded European startups in fintech/dev tools/AI

### Strategy

- Cold outreach beats applying blindly. Engage with work for months before reaching out.
- Referrals beat cold outreach. Build real relationships throughout the year on Twitter.
- Custom every application. Reference specific work at the specific company.
- Negotiate. Junior engineers consistently leave 20-30% on the table.
- Apply in January 2027 — Q1 hiring is hottest.