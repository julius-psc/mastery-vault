## The Year One Roadmap

**Start date:** May 20, 2026 **Target date for applications:** May 20, 2027 **Goal:** World-class design engineer at Linear / Vercel / Raycast / Cursor tier

**Daily commitment:** 4 hours focused learning (plus part-time lead product designer role from month 2 to month 8-9)

**Three tracks:** Engineering | Design | Illustration **Cross-cutting craft:** Motion

**Mastery bar (per concept, every track):**

1. Reproduce from blank file, from memory, no lookups
2. Explain each line / decision out loud
3. Three varied versions solving different problems

When all three pass, mark `status: mastered` in the concept note frontmatter. Re-test weekly via spaced repetition.

---

## Phase 1 — Months 1-3: Engineering Foundations + Figma Mastery via Job

**Time allocation:** Engineering 75% (3 hrs/day) | Design 10% (30 min/day side + job all-day) | Illustration 15% (1 hr/day)

---

### ENGINEERING TRACK — Phase 1

#### Stage 0: JavaScript Fundamentals (weeks 1-6)

##### 0.1 Language basics


##### 0.2 Functions

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

##### 0.3 Scope, hoisting, closures (extra time here)

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

##### 0.4 The `this` keyword

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

##### 0.5 Objects and prototypes

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

##### 0.6 Arrays and iteration

- Array creation: literal, `Array.of`, `Array.from`, `new Array(n)`
- `map`, `filter`, `reduce`, `forEach`, `find`, `findIndex`, `findLast`, `some`, `every`
- `flat`, `flatMap`
- `sort` (and the comparator function, in-place mutation)
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

##### 0.7 Asynchronous JavaScript (master deeply — this is the big one)

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

##### 0.8 Modules

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

##### 0.9 Error handling

- `Error` and its built-in subclasses (`TypeError`, `RangeError`, `SyntaxError`, etc.)
- `try`/`catch`/`finally`
- Throwing errors
- Custom error classes extending `Error`
- `Error.cause` for chained errors
- Error propagation through synchronous and asynchronous code
- The Result pattern (concept — will revisit in Rust)

##### 0.10 Capstone: Promise from scratch

- Read the Promises/A+ spec
- Implement a `MyPromise` class
- Methods: `then`, `catch`, `finally`, static `resolve`, `reject`, `all`, `allSettled`, `race`, `any`
- Pass the official Promises/A+ test suite

#### Stage 1: TypeScript (weeks 7-10)

##### 1.1 Type basics

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

##### 1.2 Objects, arrays, tuples

- Object type literal
- Optional properties (`?`)
- Readonly properties
- Index signatures
- Tuples
- Labeled tuple elements
- Variadic tuples with spread
- Array vs ReadonlyArray
- `as const` for literal narrowing

##### 1.3 Functions in TypeScript

- Function type signatures
- Optional and default parameters
- Rest parameters with tuple types
- Function overloads (declaration order matters)
- Generic functions
- Higher-order function types
- `void` vs `undefined` return type
- Contextual typing
- `this` parameter typing

##### 1.4 Type narrowing (master deeply)

- `typeof` guards
- `instanceof` guards
- Truthy/falsy narrowing
- Equality narrowing
- `in` operator narrowing
- Discriminated unions (master deeply)
- The `kind` / `type` / `_tag` discriminator convention
- User-defined type predicates (`x is T`)
- Assertion functions (`asserts x is T`)
- Exhaustiveness checking with `never` in `switch` statements

##### 1.5 Generics

- Generic functions
- Generic constraints (`extends`)
- Default type parameters
- Generic classes and interfaces
- `keyof` operator
- Indexed access types (`T[K]`)
- Mapping over object types
- Generic inference and when it fails

##### 1.6 Advanced types

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

##### 1.7 Modules and declarations

- Importing/exporting types
- `import type` and `export type`
- Ambient declarations (`declare`)
- `.d.ts` files
- Triple-slash directives (legacy awareness)
- Module augmentation

##### 1.8 Configuration

- `tsconfig.json` — every important flag
- `strict` and what it enables
- `target`, `module`, `moduleResolution`, `lib`
- `paths` and path aliases
- `verbatimModuleSyntax`
- `noUncheckedIndexedAccess`
- `exactOptionalPropertyTypes`

##### 1.9 Capstones

- Type-challenges repo: all warm tier, all easy tier, 5+ medium
- Build a typed generic fetch wrapper from scratch
    - Generic over response type
    - Discriminated union for success/error
    - AbortController support
    - Properly typed headers
    - Timeout handling

#### Stage 2: The Browser and the DOM (weeks 11-13)

##### 2.1 The DOM as data structure

- The document tree
- Node types: Element, Text, Comment, Document
- `querySelector`, `querySelectorAll`, `getElementById`, `getElementsByClassName`, `getElementsByTagName`
- NodeList vs HTMLCollection (live vs static)
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
- Property vs attribute (the `value` vs `value` attribute gotcha)

##### 2.2 Events (master event delegation)

- The event flow: capture → target → bubble
- `addEventListener` — options object: `capture`, `once`, `passive`, `signal`
- Why you never use `onclick=` in HTML
- Event delegation patterns
- `event.target` vs `event.currentTarget`
- `event.preventDefault()`, `event.stopPropagation()`, `event.stopImmediatePropagation()`
- Event types: mouse, pointer, touch, keyboard, focus, form, drag, custom
- The pointer event model (preferred over mouse + touch)
- Keyboard events: `key` vs `code`, modifier keys
- Form events: `input`, `change`, `submit`, `reset`, `focus`, `blur`
- Custom events with `CustomEvent`
- Dispatching events
- Passive event listeners and scroll performance
- AbortController for removing listeners declaratively

##### 2.3 Async browser APIs

- `fetch` in depth
- Request options: `method`, `headers`, `body`, `credentials`, `mode`, `cache`, `redirect`, `signal`
- Headers API (`Headers` constructor, `append`, `set`, `get`)
- Response object: `status`, `statusText`, `ok`, `headers`, `url`, `body`
- Parsing: `.json()`, `.text()`, `.blob()`, `.arrayBuffer()`, `.formData()`
- Streaming responses (concept)
- AbortController and AbortSignal
- AbortSignal.timeout
- AbortSignal.any
- Common HTTP status codes and their semantic meaning
- HTTP methods and their idempotency
- CORS: same-origin, cross-origin, simple vs preflight requests
- The `Origin` and `Access-Control-*` headers
- Credentials and cookies in CORS
- Reading the Network tab in DevTools — make it a habit

##### 2.4 The rendering pipeline (critical for design engineering)

- Parse → DOM tree → CSSOM → render tree → layout → paint → composite
- What triggers reflow (layout)
- What triggers repaint
- What triggers composite-only updates
- The compositor thread
- Why `transform` and `opacity` are special
- `will-change` and its costs
- `contain` property for scoping reflows
- The Performance tab in DevTools — actually use it
- Layers and the layer panel
- Frame budget at 60fps (16.67ms) and 120fps (8.33ms)
- Long tasks and the long task API

##### 2.5 The event loop in the browser

- Tasks vs microtasks (revisit from 0.7 with browser context)
- Where rendering fits in the loop
- Why long synchronous work blocks the UI
- `queueMicrotask` vs `setTimeout(0)` vs `requestAnimationFrame`
- `requestIdleCallback` and when it's appropriate
- The render steps: style → layout → paint → composite
- Animation frame scheduling

##### 2.6 Observers

- IntersectionObserver: viewport visibility
- IntersectionObserver options: `root`, `rootMargin`, `threshold`
- MutationObserver: DOM changes
- ResizeObserver: element size changes
- PerformanceObserver: performance entries
- Observer cleanup (`disconnect`)

##### 2.7 Forms

- Form elements: `input`, `textarea`, `select`, `button`
- Input types and their semantic meaning
- Form values and the `FormData` API
- HTML5 validation attributes
- Custom validation with `setCustomValidity`
- `:valid` and `:invalid` CSS pseudo-classes
- The submit event and `preventDefault`
- File inputs and the File API
- Working with `FileReader`

##### 2.8 Storage

- `localStorage` vs `sessionStorage`
- The 5-10MB limit
- Synchronous nature and blocking
- `JSON.stringify` / `JSON.parse` patterns
- Storage events for cross-tab sync
- Cookies — when they're appropriate
- IndexedDB (just enough awareness — async, structured, much larger limits)
- The Cache API (concept)

##### 2.9 Capstones (build in vanilla JS, no framework)

- Todo list with localStorage persistence
- Search input with debouncing and AbortController for stale request cancellation
- Drag-and-drop reorderable list
- Modal with full focus trap (accessibility)
- Infinite scroll list with IntersectionObserver
- Toast notification system

---

### DESIGN TRACK — Phase 1

The job teaches you Figma hands-on daily. Your side practice is exposure + reading.

#### Daily dissection (20 min/day, every day)

- One entry per day in `04_design/library/`
- Rotate sources: Linear, Vercel, Raycast, Cursor, Arc, Stripe, Figma, Notion, Framer, Liveblocks, Mercury, Ramp, Pylon
- Capture screenshot, write: design decision, why it works, underlying principle, where else seen, what you'd change

#### Active Figma mastery at the job (push beyond what tasks require)

**Component architecture**

- Components vs instances
- Variants and variant properties
- Component properties: boolean, instance swap, text, nested instance
- Component sets and naming conventions
- Slot patterns
- Nesting depth and performance considerations
- When to break up large components

**Auto-layout deeply**

- Direction, alignment, spacing
- Padding (uniform, individual)
- Resizing: fill container, hug contents, fixed
- Min/max width and height
- Absolute positioning inside auto-layout
- Wrap behavior
- Negative spacing
- Nested auto-layout patterns

**Variables**

- Variable types: color, number, string, boolean
- Variable collections
- Modes (light/dark, mobile/desktop, brand A/B)
- Variable scoping
- Aliasing variables (semantic → primitive)
- Variables in auto-layout
- Number variables in spacing, sizing, radius

**Styles**

- Color styles vs color variables
- Text styles
- Effect styles
- Grid styles
- When to use styles vs variables

**Advanced prototyping**

- Click, hover, drag, key trigger types
- Smart animate
- Variables in interactions (set, conditional)
- Conditional logic with if statements
- Scroll behavior: horizontal, vertical, sticky
- Overlay positions
- Easing curves and durations
- Building interaction flows that match production behavior

**Libraries and collaboration**

- Local libraries vs published libraries
- Library publishing and updates
- Branching for major changes
- Conflict resolution

**Dev Mode**

- Inspecting from the engineer side
- Variables in CSS output
- Code generation review

**Plugins worth knowing**

- Iconify (icon import)
- Variables Import/Export
- Design Lint
- Figma to Code (study output, don't ship)
- Anima
- Material Theme Builder

#### Reading (weekly, 2-3 hrs)

- _Refactoring UI_ by Adam Wathan and Steve Schoger — read twice in Phase 1
- _The Linear Method_ (linear.app/method) — read multiple times
- _The Design of Everyday Things_ by Don Norman
- Rauno Freiberg's website (rauno.me) — every post
- Emil Kowalski (emilkowal.ski) — every post

#### Weekly UX system map

- Pick one feature in a product you use daily
- Map every state, transition, edge case, empty state, error state, loading state
- Examples: Linear's command palette, Raycast's quicklinks, Notion's slash commands
- 12 maps by end of Phase 1

---

### ILLUSTRATION TRACK — Phase 1

This is foundation-building. Not producing portfolio pieces yet — building visual literacy and basic tool fluency.

#### Tools

- Figma (vector illustration)
- Blender (3D — free, industry standard)
- Photoshop or Affinity Photo (grain and raster work)

#### 1A — Composition fundamentals (week 1-2)

- The rule of thirds applied to UI illustration
- Visual hierarchy in illustration (eye path)
- Negative space and breathing room
- Balance: symmetric, asymmetric, radial
- Focal points: contrast, isolation, scale, color
- Leading lines
- Framing and edges

#### 1B — Light and shadow (week 2-3)

- Direct light vs ambient light vs bounce light
- Three-point lighting (key, fill, rim)
- Soft shadows vs hard shadows
- Ambient occlusion — what it does to a render
- Color temperature (warm vs cool light)
- Light direction and mood

#### 1C — Color theory for illustration (week 3-4)

- Color wheel basics revisited
- Color harmonies: complementary, analogous, triadic, split-complementary
- Saturation vs value
- Limited palettes and why they work
- Analyzing Linear's, Raycast's, Vercel's illustration palettes

#### 1D — Isometric geometry (week 4-5)

- True isometric (30°) vs game isometric (26.57°)
- The isometric grid
- Building forms from primitives
- Setting up isometric grids in Figma
- Setting up an orthographic camera in Blender at isometric angles
- The Linear FIG style: line work, subtle gradients, schematic feel, annotation typography

#### 1E — Blender absolute basics (week 5-8)

- Interface and viewport navigation
- Object mode vs edit mode
- Adding primitives
- Transforms: move, rotate, scale (G, R, S shortcuts)
- The 3D cursor
- Modifiers basics: Bevel, Subdivision Surface, Boolean, Array, Mirror
- The Donut tutorial by Blender Guru (canonical first project, ~6 hours)
- Materials and the Principled BSDF shader
- Camera setup for isometric renders
- Lighting setups
- Rendering with Eevee (real-time)

#### 1F — First isometric pieces (week 9-13)

- Model 3 simple objects in Blender
- Render in stylized line work style
- One vector recreation in Figma of a Linear FIG illustration
- Document techniques in your vault

#### Weekly practice (one 3-hour block + 30 min daily)

- Build vocabulary of references in `05_illustration/references/`
- Save 5+ illustrations per week with technique notes

---

### Phase 1 Milestones (end of month 3)

- Stages 0-2 mastered with three-test bar passed on every concept
- Job role active with portfolio rights clarified in contract
- Figma at advanced level: components, auto-layout, variables, variants, advanced prototyping with logic
- 80+ entries in design library
- 12 UX system maps done
- _Refactoring UI_, _Linear Method_, _Design of Everyday Things_ finished
- 4-6 Blender pieces in early Linear style
- Daily Obsidian streak: 90+ days
- First essays drafted if blog started

---

## Phase 2 — Months 4-6: React, Rust, Motion Fundamentals, Illustration Depth

**Time allocation:** Engineering 60% (2.5 hrs/day) | Design 15% (45 min/day side + job) | Illustration 25% (1 hr/day)

---

### ENGINEERING TRACK — Phase 2

#### Stage 3: React (weeks 14-17)

##### 3.1 Mental model

- What React is: a library producing a tree of elements you re-render efficiently
- JSX and how it compiles (`React.createElement` / `jsx-runtime`)
- The virtual DOM and reconciliation
- Components as functions
- Why React exists: the problem with direct DOM manipulation at scale

##### 3.2 Components and props

- Function components
- Props as function arguments
- Prop destructuring
- Children and the `children` prop
- Render props (legacy but worth knowing)
- Conditional rendering patterns: `&&`, ternary, early return
- Lists and keys
- Why keys matter — connect to reconciliation
- Fragments and the `<></>` shorthand
- Portals

##### 3.3 State and effects

- `useState` — when state updates, what triggers re-renders
- State updater functions vs values
- Lazy initial state
- State batching in React 18+
- `useReducer` — when to reach for it over `useState`
- `useEffect` and the dependency array
- The mental model: effects synchronize with external systems
- "You Might Not Need an Effect" — read on react.dev
- Cleanup functions
- Strict mode and double-invocation in dev
- `useLayoutEffect` vs `useEffect`
- `useInsertionEffect` (rarely needed, awareness only)

##### 3.4 Refs and the DOM

- `useRef` for DOM access
- `useRef` for mutable values that don't trigger re-renders
- When to use ref vs state
- `forwardRef` (legacy in React 19+, awareness)
- The new `ref` as a prop in React 19+
- `useImperativeHandle`

##### 3.5 Performance and memoization

- When components re-render
- The re-render cascade
- `useMemo` and when it's worth it
- `useCallback` and when it's worth it
- `React.memo`
- The cost of premature optimization
- React DevTools profiler

##### 3.6 Context

- `useContext`
- When context is appropriate vs prop drilling vs state library
- Re-render pitfalls with context
- Splitting contexts (state vs dispatch)
- Provider patterns

##### 3.7 Custom hooks

- Building custom hooks
- The rules of hooks and why they exist
- Composition patterns
- Naming conventions

##### 3.8 Forms in React

- Controlled vs uncontrolled inputs
- When to use each
- `useFormState` and form actions (React 19+)
- Working with refs for forms
- Libraries: react-hook-form (concept only)

##### 3.9 Data fetching patterns

- Manual fetching with `useEffect` and why it's tricky
- Loading and error states
- Cancellation with AbortController
- Race conditions in async effects
- The `use` hook for Promises (React 19+)
- When to reach for TanStack Query (concept only)

##### 3.10 Capstones

- Rebuild Stage 2 vanilla capstones in React
- Build a typed generic `useQuery`-like hook from scratch (~200 lines)
    - Caching, loading, error, refetching, deduplication

#### Stage 4: Rust Fundamentals (weeks 18-22)

##### 4.1 Setup and tooling

- Installing via rustup
- cargo: `new`, `build`, `run`, `test`, `check`, `clippy`, `fmt`
- The module system: `mod`, `mod.rs`, `lib.rs`, `main.rs`
- `Cargo.toml` and dependencies

##### 4.2 Ownership (the famous wall — sit with it)

- Stack vs heap
- The three ownership rules
- Move semantics
- The `Copy` trait
- The `Clone` trait
- The borrow checker as teacher

##### 4.3 References and borrowing

- Immutable references (`&T`)
- Mutable references (`&mut T`)
- The borrowing rules: many readers OR one writer, never both
- Reference scope and non-lexical lifetimes
- Dereferencing with `*`
- Slices (`&[T]`, `&str`)

##### 4.4 Lifetimes

- Why lifetimes exist
- Lifetime annotations
- The three lifetime elision rules
- The `'static` lifetime
- Lifetimes in structs
- Lifetimes in function signatures

##### 4.5 Type system

- Primitive types
- Tuples and arrays
- Structs: regular, tuple, unit
- `impl` blocks
- Methods vs associated functions
- Enums (master deeply — Rust enums are the heart of the language)
- Enum variants with data
- Pattern matching with `match`
- Match exhaustiveness
- `if let`, `while let`, `let else`

##### 4.6 Error handling

- `Result<T, E>` and `Option<T>`
- The `?` operator
- Custom error types
- `From` impls for error conversion
- `panic!` vs recoverable errors
- The `thiserror` and `anyhow` crates (concept only)

##### 4.7 Traits and generics

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
- Derive macros

##### 4.8 Collections

- `Vec<T>`
- `String` and `&str`
- `HashMap<K, V>`
- `HashSet<T>`
- `BTreeMap`, `BTreeSet`
- The iterator trait
- Common iterator methods: `map`, `filter`, `fold`, `collect`, `enumerate`, `zip`, `chain`
- Iterator adapters vs consumers

##### 4.9 Modules, crates, workspaces

- The module system
- Visibility (`pub`, `pub(crate)`)
- Re-exports
- Workspaces

##### 4.10 Async basics (light touch)

- `async`/`await` syntax
- Futures conceptually
- Tokio runtime introduction
- `tokio::spawn`

##### Capstone

- Complete Rustlings
- Build 3 small CLI tools in pure Rust (a file watcher, a hash calculator, a markdown-to-html converter)

#### Stage 5: Swift Fundamentals (weeks 23-25)

##### 5.1 Language basics

- `var` vs `let`
- Type inference and annotations
- Optionals: `?`, `!`, `if let`, `guard let`, `??`
- Value types vs reference types (struct vs class)
- Closures
- Functions and methods

##### 5.2 Type system

- Protocols
- Protocol extensions
- Generics
- Associated types in protocols
- Opaque types (`some Protocol`)
- Existentials (`any Protocol`)

##### 5.3 Pattern matching

- `switch` statements
- `if case`, `for case`, `guard case`
- Enum cases with associated values
- Where clauses in patterns

##### 5.4 Memory and concurrency

- ARC basics
- Strong, weak, unowned references
- Capture lists in closures
- Structured concurrency: `async`/`await`, `Task`, `TaskGroup`
- Actors
- `@MainActor`

##### 5.5 SwiftUI basics

- The `View` protocol
- Property wrappers: `@State`, `@Binding`, `@ObservedObject`, `@StateObject`, `@EnvironmentObject`
- View modifiers
- Layout containers: `HStack`, `VStack`, `ZStack`, `Grid`
- Animation basics
- Navigation

##### Capstone

- Small native menu bar app in pure SwiftUI

---

### DESIGN TRACK — Phase 2

Motion fundamentals start here. This is the most consequential addition to your design practice.

#### Motion principles (research deeply, weeks 14-17)

**M1 — Disney's 12 principles applied to UI**

- Squash and stretch → elastic easing on press states
- Anticipation → loading states, hover previews
- Staging → focal hierarchy through motion
- Straight ahead vs pose-to-pose → procedural vs keyframed
- Follow-through and overlapping action → inertia, secondary motion
- Slow in and slow out → easing curves
- Arcs → natural curved paths
- Secondary action → contextual motion supporting primary
- Timing → duration as expression
- Exaggeration → emphasis
- Solid drawing → consistent physical model
- Appeal → personality through motion

Watch Alan Becker's "12 Principles" YouTube series. Then _Designing Interface Animation_ by Val Head.

**M2 — Easing curves**

- Linear, ease-in, ease-out, ease-in-out
- Cubic bezier — every point on the curve
- Material Design easing curves
- Apple's standard curves
- Custom curves for specific feelings
- Use cases mapped to curves

**M3 — Spring physics (the modern default)**

- Stiffness, damping, mass
- Critical, under, over damping
- Why springs feel more natural than curves
- Framer Motion's spring API
- React Spring as alternative

**M4 — Duration**

- Micro-interactions: 100-200ms
- Standard transitions: 200-400ms
- Emphasis: 400-800ms
- Why anything longer is usually wrong

**M5 — Choreography**

- Parent-child timing
- Stagger
- Sequencing
- Origin and direction (transforms from where attention is)

**M6 — Motion as communication**

- Motion as state change vs decoration
- Motion as feedback
- Motion as hierarchy
- Motion as personality

**M7 — Performance**

- `transform` and `opacity` only on compositor thread
- Why other properties cause layout thrashing
- `will-change` and its costs
- The 60fps target (16.67ms) and 120fps push (8.33ms)

#### Implementation tools

**Stage M-CSS (week 18, focused)**

- `transition` property and all sub-properties
- `@keyframes` and `animation` shorthand
- `cubic-bezier()` syntax
- `animation-timeline` and scroll-driven animations
- View Transitions API

**Stage M-FM (weeks 19-21)**

- Framer Motion (now `motion` library)
- Basic `motion` components
- `animate`, `initial`, `exit`, `transition`
- `variants` for choreography
- `AnimatePresence` for exit animations
- Layout animations (`layout`, `layoutId`)
- Gestures: `drag`, `tap`, `hover`, `focus`
- Shared layout transitions
- `useScroll`, `useTransform` for scroll-linked motion
- `useSpring`, `useMotionValue`, `useMotionValueEvent`

#### Weekly motion recreations (weeks 14-26)

- Week 14: Linear's hover states on dashboard items
- Week 15: Raycast's command palette open/close
- Week 16: Vercel's homepage hero animation
- Week 17: Arc's tab switcher
- Week 18: Linear's modal entrance with backdrop blur
- Week 19: Notion's drag-to-reorder
- Week 20: Cursor's tab transitions
- Week 21: Stripe's number ticker animations
- Week 22: Liveblocks' cursor animations
- Week 23: Linear's command palette filtering
- Week 24: Framer's drag interactions
- Week 25: Mercury's account switcher
- Week 26: Spring physics study (recreate Linear's springy interactions)

By end of Phase 2: 12+ motion recreations, each a standalone React component, organized in a private playground.

#### Continue daily dissection and reading

---

### ILLUSTRATION TRACK — Phase 2

You go from beginner to genuinely competent.

#### 2A — Blender intermediate (weeks 14-17)

- The modifier stack in depth
- Edge loops and basic topology
- Modeling clean low-poly objects
- Materials in the shader editor
- Procedural materials with noise nodes
- Stylized rendering with Freestyle (line work)
- Geometry Nodes basics
- Lighting setups for product illustration mood
- Render passes and compositing basics

#### 2B — Schematic technical illustration aesthetic (weeks 18-19)

- Wireframe + filled hybrid look
- Line weight hierarchy
- Annotation typography (mono fonts, leader lines)
- Grid backgrounds and registration marks
- FIG_01 / FIG 0.2 conventions
- Color palette restraint

#### 2C — Grain, noise, texture (weeks 20-22)

- Procedural noise types: Perlin, Simplex, Worley, Voronoi
- Film grain and analog warmth
- Photoshop noise + blend modes
- CSS / SVG `feTurbulence`
- WebGL noise shaders (intro)
- Gradient mesh techniques in Figma / Illustrator
- The "blurred light columns" Raycast aesthetic

#### 2D — Shaders introduction (weeks 23-26)

- What a shader is — vertex vs fragment
- GLSL basics: variables, functions, math
- The Book of Shaders — first 5 chapters
- Common patterns: gradients, noise, distortion
- Shadertoy as study resource
- React Three Fiber + drei (intro)

#### Practice

- Weeks 14-15: 3 complete Blender objects in Linear style
- Weeks 16-17: 2 faithful Linear FIG recreations
- Weeks 18-20: 3 Raycast/Vercel-style grainy gradient pieces
- Weeks 21-22: First 3 simple shaders on Shadertoy
- Weeks 23-26: Combine techniques — first signature original piece

---

### Phase 2 Milestones (end of month 6)

- React + Rust + Swift fundamentals locked
- 12+ motion recreations
- Motion principles articulable from first principles
- 3+ polished Linear-style illustrations
- 3+ polished Raycast-style pieces
- First shaders working
- Job role at midpoint with shipped work
- First essays published (start month 4 latest)
- 150+ design library entries

---

## Phase 3 — Months 7-9: Rive, Advanced Motion, Marketing Site Recreations, Application Project

**Time allocation:** Engineering 50% (2 hrs/day) | Design 25% (1 hr/day) | Illustration 25% (1 hr/day)

The job ends partway through this phase. Side work accelerates.

---

### ENGINEERING TRACK — Phase 3

#### Stage 6: Rust Depth (weeks 27-30)

##### 6.1 Advanced ownership patterns

- `Rc<T>` for shared ownership (single-threaded)
- `Arc<T>` for shared ownership (multi-threaded)
- `RefCell<T>` for interior mutability (single-threaded)
- `Mutex<T>` for interior mutability (multi-threaded)
- `RwLock<T>` for many-reader-one-writer
- When each is appropriate
- The `Send` and `Sync` marker traits
- Sharing data across threads

##### 6.2 Advanced traits

- Associated types vs generic parameters
- Default associated types
- Trait inheritance (`trait B: A`)
- Marker traits
- Operator overloading
- The orphan rule and the newtype pattern

##### 6.3 Async in depth

- Futures and the `Future` trait
- Poll-based futures
- Pin and unpin
- Tokio runtime internals
- Channels: `mpsc`, `oneshot`, `broadcast`, `watch`
- Spawning, joining, cancellation
- Async traits (`async-trait` crate or native)
- Streams

##### 6.4 Macros

- Declarative macros (`macro_rules!`)
- Procedural macros (concept, use existing ones)
- Common useful macros in the ecosystem
- The `derive` macro mechanism

##### 6.5 Common patterns

- Builder pattern
- Newtype pattern
- Typestate pattern
- Error handling: `thiserror` for libraries, `anyhow` for applications

##### Capstone

- Read _Rust for Rustaceans_ by Jon Gjengset
- Watch his "Crust of Rust" series on YouTube
- Build one substantial CLI tool with async (parallel file downloader, benchmarking tool, real-time log tailer)

#### Stage 7: Application Project Begins (weeks 31-39)

Whatever you want to build. A productivity app, a creative tool, a developer utility, a personal app — your call. macOS native via Tauri + Swift bridge. The principles:

- **Design-first.** Spec each slice in Figma before coding.
- **Vertical slices.** Each slice ships end-to-end.
- **Ship the design system in code.** Build your token system, components, motion all in code.
- **Each slice teaches one new technical thing.** Don't combine learning + building.

**Suggested slice order:**

1. Static screens with full design system (tokens, typography, components built from Radix primitives)
2. Local state and interactions
3. Persistence (localStorage or sqlite via Tauri)
4. External API integration with typed fetch wrapper
5. Tauri shell — wrap as native macOS app
6. First Rust feature (file system, global shortcut, native notification)
7. Advanced state with optimistic updates and rollback
8. Keyboard shortcuts + menu bar via Swift
9. Performance work — measure and optimize
10. Motion polish — every interaction reviewed for craft

---

### DESIGN TRACK — Phase 3

#### Rive (weeks 27-30)

- The Rive editor — interface, tools
- The runtime model
- State machines: inputs, states, transitions
- Animations and timelines
- Blend states
- Listeners
- Integration with React via `@rive-app/react-canvas`
- State machine inputs from React
- Production patterns: complex hover states, loading animations, marketing centerpieces
- One serious Rive piece by end of month 8

#### Marketing site recreations (the proof-of-craft work)

**Month 7-8: Linear's homepage** (~3 weeks)

- All motion, all transitions, all interactions
- Frame as a study, credit original
- Document techniques in case study format

**Month 8: Vercel's homepage** (~3 weeks)

- Particular focus on Three.js parts
- React Three Fiber implementation
- Performance optimization

**Month 9: Raycast's homepage** (~3 weeks)

- Grainy hero recreation
- Animation choreography
- Scroll-linked motion

Each becomes a major portfolio piece.

#### Advanced UX deepening

- Information architecture deep
- Service blueprints (when appropriate)
- Onboarding design principles
- Empty/error/edge states as first-class concern
- Designing for keyboard-first users
- Accessibility deeply: WCAG 2.2 AA, screen reader testing (VoiceOver), keyboard navigation, focus management, ARIA when necessary

#### Advanced visual

- Build a perceptually uniform color system (OKLCH-based)
- Design a typeface pairing for a hypothetical product (display + body + mono)
- Design an icon set from scratch (Lucide base + 20 custom)
- Pixel-perfect recreations of 5 marketing layouts in code

---

### ILLUSTRATION TRACK — Phase 3

You're producing portfolio-quality work now.

#### Advanced Blender

- Complex geometry
- Advanced materials with full node-graph work
- Cinematic lighting setups
- Geometry Nodes for procedural geometry
- Compositing in Blender

#### Advanced shaders

- Noise-based effects
- Ray marching basics
- Fragment shader patterns
- 2D SDFs
- Signed distance fields for shapes

#### Compositing

- Combining 3D renders with vector overlays
- Type integration
- Grain and color grading layers
- The "Linear FIG" look as a composite of 3D + vector + type

#### Personal style development

- Identify what your visual signature is
- Build a recognizable vocabulary

#### Practice

- Month 7: one polished "Linear FIG" original (~10 hrs)
- Month 8: one polished Raycast-style piece with real concept (~10 hrs)
- Month 9: one signature piece combining 3D + grain + shader + type (~15-20 hrs)

---

### Phase 3 Milestones (end of month 9)

- Rust + Swift fluency
- 3 marketing site recreations live (Linear, Vercel, Raycast)
- One serious Rive piece
- First shaders working in production
- Application project: 4-5 vertical slices shipped
- 3 polished signature illustrations
- Job complete with case study material if possible
- 8-10 essays published
- 250+ design library entries

---

## Phase 4 — Months 10-12: Synthesis, Portfolio Rebuild, Applications

**Time allocation:** Engineering 35% | Design 40% | Illustration 25%

Everything converges into what gets you hired.

---

### What you build in this phase

#### The portfolio site itself (weeks 40-46)

Built in Next.js, deployed to Vercel. Custom design, no template. The site itself is a portfolio piece.

**Required qualities:**

- Loads instantly (Lighthouse 100 performance)
- Accessible (WCAG 2.2 AA minimum, ideally AAA on color)
- Has personality (POV visible in 5 seconds)
- Motion as primary design material
- Your illustration work as visual identity
- Mobile-first, exquisite on every breakpoint

**Structure:**

- Homepage with strong POV
- About page with your story (the 18-year-old narrative used deliberately)
- Work section with 4-6 detailed case studies
- Writing section with all essays
- Optional: playground/lab section with motion experiments
- Optional: live learning site as digital garden

#### Case studies for the portfolio

- Application project as hero piece (full case study)
- 3 marketing site recreations
- 2-3 product redesign case studies done in Phase 3
- Motion library (12-24 micro-interactions as interactive gallery)
- Illustration body of work
- Job's case study if NDA permits, high-level otherwise

Each case study is a narrative:

1. Problem and context
2. Constraints
3. Explorations
4. Decisions and tradeoffs
5. Result with shipped detail
6. Reflection

#### The blog

- All essays from months 4-12 consolidated
- 12-16 essays by year end
- Topics show your POV: design decisions, technical deep dives, dissections, opinions

#### Application phase (weeks 46-52)

**Strategy:**

- Cold outreach beats applications. Find design engineers at target companies on Twitter/LinkedIn. Engage with their work for months before reaching out. When you reach out, lead with work, not story.
- Twitter built over the year is the watering hole.
- Referrals beat cold outreach. Build relationships throughout the year.
- Custom every application.

**Targets:**

- **Tier 1:** Linear, Vercel, Raycast, Cursor, Liveblocks, Framer, Arc / Browser Company
- **Tier 2:** Stripe, Figma, Notion, Mercury, Ramp, Rippling, Webflow, Anthropic design team
- **Tier 3:** Strong YC W26/S26 product-led startups, well-funded European startups in fintech/dev tools/AI

---

### Daily and Weekly Rhythm

#### Daily structure

- **Morning block (2 hrs):** hardest discipline — usually engineering
- **Afternoon block (1-2 hrs):** second discipline
- **Evening (30-60 min):** illustration or motion (visual work, less cognitively demanding)
- **End of day (90 sec):** Obsidian daily log

#### Weekly structure

- Mon-Sat: 4 hrs focused practice + job 3 days/week
- Sunday morning: 30 min weekly review in Obsidian
- Sunday afternoon: off, non-negotiable

#### Monthly review

- First Sunday of each month, 1 hour
- Summary note: `02_weekly/YYYY-MM-monthly.md`
- Review mastered concepts, realizations, patterns
- Adjust pacing if needed, never abandon the order

---

### Non-negotiables

1. **Never break the streak.** A 20-min day counts. A skipped day does not.
2. **Mastery bar applies to every concept.** Three tests. No exceptions.
3. **Sunday afternoon off.** Recovery is part of the work.
4. **Weekly spaced re-tests.** This is what makes learning permanent.
5. **Public output starts month 4.** One essay every two weeks minimum.
6. **Daily Obsidian log.** 90 seconds. No exceptions.
7. **Verdyct stays closed.** No checking in.
8. **The order is the order.** Impatient-Julius defers to calm-Julius.

---

### What success looks like on May 20, 2027

- Deep fluency in TypeScript, Rust, Swift
- React mastery with internals understood
- Tauri-based macOS app shipped publicly
- 15+ essays published showing how you think
- Portfolio site that competes with rauno.me / emilkowal.ski tier
- 6+ substantial case studies
- Motion practice articulable from first principles
- Body of original illustration work in a recognizable style
- Lead product designer credential on CV
- Twitter following of practitioners in the field
- Real relationships in the design engineering community
- Ready to apply to Linear / Vercel / Raycast / Cursor with credibility