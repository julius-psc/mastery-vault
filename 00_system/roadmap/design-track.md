# Designing

**Daily block:** 1.5 hours, every day, afternoon **Sub-tracks:** Figma mastery | UX systems thinking | Motion | Rive | Portfolio **Rule:** Design dissection happens every single day (20 min of your 1.5 hrs). Everything else rotates within the remaining time by phase.

---

## PHASE 1 — Months 1-3: Figma Mastery + Design Literacy

**Split:** 20 min daily dissection + 40 min Figma/reading + 30 min UX system work

---

### Daily Dissection (every single day, 20 min)

**Never skip this. It is the compounding habit of the entire design track.**

One entry per day in `04_design/library/`. Template: `dissection-template.md`

**What to capture:**

- Screenshot of the specific element (one screen, one interaction, one detail — not a whole app)
- What is the design decision here?
- Why does it work?
- Underlying principle (name it — visual hierarchy, affordance, progressive disclosure, etc.)
- Where else have you seen this pattern?
- What would you change, if anything?

**Rotation schedule — cycle weekly:**

- Week A: Linear, Vercel, Raycast
- Week B: Cursor, Arc, Stripe
- Week C: Figma, Notion, Framer
- Week D: Liveblocks, Mercury, Ramp, Pylon

**Also use:** Mobbin (mobile UI), Refero, Page Flows (user flows), Godly, Lapa Ninja

---

### Figma Mastery (at the job + 30 min solo daily)

The job gives you hands-on Figma practice daily. Your solo time deepens what the job demands. Push beyond what each task requires.

#### Component Architecture

- Components vs instances — the mental model
- Variants and variant properties in depth
- Component properties: boolean, instance swap, text, nested instance
- Component sets and naming conventions
- Slot patterns (creating flexible layouts)
- Nesting depth and performance considerations
- When to break up large components
- Main component vs detached instance — when to detach

#### Auto-Layout Deeply

- Direction, alignment, spacing
- Padding: uniform and individual sides
- Resizing modes: fill container, hug contents, fixed
- Min/max width and height
- Absolute positioning inside auto-layout frames
- Wrap behaviour
- Negative spacing
- Nested auto-layout patterns (the most common real-world pattern)
- When auto-layout makes things harder, not easier

#### Variables

- Variable types: color, number, string, boolean
- Variable collections and naming
- Modes: light/dark, mobile/desktop, brand variants
- Variable scoping (local vs library)
- Aliasing: semantic → primitive token structure
- Variables in auto-layout spacing and sizing
- Number variables for radii, spacing, sizing

#### Styles

- Color styles vs color variables (know when to use which)
- Text styles
- Effect styles (shadows, blurs)
- Grid styles
- When styles are appropriate vs variables

#### Advanced Prototyping

- Click, hover, drag, key trigger types
- Smart animate — how it works and when to use it
- Variables in interactions: set variable, conditional
- Conditional logic with if/else in prototypes
- Scroll behaviour: horizontal, vertical, sticky
- Overlay positions and transitions
- Easing curves and durations in Figma
- Building flows that closely match production behaviour

#### Libraries and Collaboration

- Local libraries vs published libraries
- Library publishing and update workflow
- Branching for major design changes
- Conflict resolution in shared files
- Version history and when to use it

#### Dev Mode

- Inspecting from the engineering perspective
- Variables in CSS output
- Code generation review (study the output, understand the gap)
- Annotations and redlines

#### Plugins Worth Knowing

- Iconify (icon import from any icon set)
- Variables Import/Export
- Design Lint (consistency checking)
- Figma to Code (study the output, don't ship it)
- Anima
- Material Theme Builder

---

### Reading (weekly, absorbed across the 1.5 hr block)

Work through in this order. Don't rush. Read each one to understand, not to finish.

**Months 1-2:**

- _Refactoring UI_ by Adam Wathan and Steve Schoger — read it twice. The most practical book on UI design that exists. Apply every principle to real work immediately.
- _The Linear Method_ (linear.app/method) — read multiple times. The clearest articulation of how a great software company thinks about product.

**Month 2-3:**

- _The Design of Everyday Things_ by Don Norman — slow read. Foundational theory on affordances, signifiers, mental models. Change how you look at everything designed.

**Ongoing (weekly posts, rotate):**

- rauno.me — every post, multiple reads
- emilkowal.ski — every post, multiple reads
- Linear engineering and product blog
- Vercel engineering blog
- Stripe blog
- Figma engineering blog

---

### Weekly UX System Map (1 per week, 45 min)

This addresses your stated gap: you think about flows but not yet about systems.

**The exercise:** Pick one specific feature in a product you use. Map its complete state space — not the happy path, everything.

**What to map:**

- Every state the feature can be in
- Every possible transition between states
- Empty states (no data yet)
- Loading states (data in flight)
- Error states (something went wrong)
- Edge cases (what if the list has 10,000 items? What if the name is 200 characters?)
- Success states
- Destructive action confirmation flows

**Suggested features (one per week for 12 weeks):**

1. Linear's command palette (cmd+K)
2. Raycast's quicklinks
3. Notion's slash command menu
4. GitHub's issue creation flow
5. Figma's component swap
6. Linear's cycle management
7. Raycast's calculator
8. Notion's database view switcher
9. Stripe's payment flow
10. Arc's space switching
11. Linear's inbox
12. Vercel's deployment flow

Document each in `04_design/case_studies/ux-map-YYYY-MM-DD-[product]-[feature].md`

---

### Phase 1 Design Milestones (end of month 3)

- [ ] 80+ design library entries
- [ ] Figma at advanced level: components, auto-layout, variables, variants, advanced prototyping
- [ ] Portfolio rights clarified in job contract
- [ ] 12 UX system maps complete
- [ ] _Refactoring UI_ read twice and applied
- [ ] _Linear Method_ and _Design of Everyday Things_ finished
- [ ] Can articulate why specific design decisions work using named principles

---

## PHASE 2 — Months 4-6: Motion Fundamentals + Framer Motion

**Split:** 20 min daily dissection + 70 min motion study/implementation

---

### Motion Principles (weeks 14-17, research each concept yourself)

**This is the most consequential thing you will add to your design practice. Don't rush it.**

---

#### M1 — Disney's 12 Principles Applied to UI

Research each principle, then write its UI equivalent in your concept note.

- **Squash and stretch** → elastic easing on press states, bounce on landing
- **Anticipation** → loading indicators before action, hover previews before click
- **Staging** → focal hierarchy through motion (what moves first draws the eye)
- **Straight ahead vs pose-to-pose** → procedural vs keyframed animation
- **Follow-through and overlapping action** → inertia, secondary motion after primary stops
- **Slow in and slow out** → easing curves (the default for almost everything)
- **Arcs** → natural curved paths rather than linear movement
- **Secondary action** → contextual motion supporting the primary action
- **Timing** → duration as expression of weight, importance, energy
- **Exaggeration** → controlled overshoot for emphasis
- **Solid drawing** → consistent physical model (things don't defy physics without purpose)
- **Appeal** → personality through motion (your app's character)

**Watch:** Alan Becker's "12 Principles of Animation" YouTube series **Read:** _Designing Interface Animation_ by Val Head (every chapter)

---

#### M2 — Easing Curves

- Linear: for continuous motion (progress bars, spinners) — not general use
- Ease-in (accelerate): for exits (things leaving the screen)
- Ease-out (decelerate): for entrances (things entering the screen) — most common
- Ease-in-out: for elements moving from one position to another on screen
- `cubic-bezier(x1, y1, x2, y2)` — understand every point on the curve
- Material Design easing curves and their rationale
- Apple's standard curves (UIKit) and when to match them
- Custom curves for specific emotional tones
- Tool: easings.net for visual comparison

---

#### M3 — Spring Physics

**The modern default for product interfaces**

- Stiffness (how fast it moves toward target)
- Damping (how much oscillation is suppressed)
- Mass (how heavy it feels)
- Critical damping — no oscillation, fastest to settle (most buttons)
- Underdamping — overshoots and bounces (playful, elastic)
- Overdamping — slow, never overshoots (deliberate, heavy)
- Why springs feel more natural than easing curves for most UI motion
- Framer Motion's spring API: `stiffness`, `damping`, `mass`, `bounce`, `duration`
- React Spring as an alternative approach

---

#### M4 — Duration

- Micro-interactions (hover, press, toggle): 100-200ms
- Standard transitions (modal open, panel slide): 200-400ms
- Emphasis animations (success state, celebration): 400-800ms
- Anything over 800ms is usually wrong — feels slow
- Duration communicates weight: heavier elements move slower
- Duration communicates importance: more important = slightly longer
- 120fps display implications: you have 8.33ms per frame instead of 16.67ms

---

#### M5 — Choreography

- Parent-child timing: parent animates first, then children follow
- Stagger: each child delayed by 30-60ms from the previous
- Sequence: one thing finishes before the next starts
- Overlap: things animate simultaneously (for speed, not clarity)
- Origin and direction: transforms should originate from where the user's attention is
- Reading order: left-to-right, top-to-bottom stagger for lists

---

#### M6 — Motion as Communication

- Motion as **state change indicator** (the primary purpose)
- Motion as **feedback** (the action registered, something happened)
- Motion as **hierarchy** (what's more important moves differently)
- Motion as **personality** (the product's character expressed in movement)
- Motion as **decoration** — avoid this unless the context is explicitly playful
- The test: if the animation were removed, would the user miss information? If yes, it communicates. If no, reconsider.

---

#### M7 — Performance

- Only `transform` and `opacity` can be animated on the compositor thread (cheapest)
- All other properties (width, height, margin, left, top) trigger layout recalculation (expensive)
- `will-change: transform` hints the browser to promote an element to its own layer
- Costs of `will-change`: memory usage, layerisation overhead — use sparingly
- Measuring animation performance in the Performance tab (look for jank frames)
- The 60fps target: each frame must complete in 16.67ms
- The 120fps target on ProMotion displays: 8.33ms per frame

---

### CSS Transitions and Animations (week 18, dedicated)

**Research every property yourself. Build examples for every concept.**

- `transition` property: `property`, `duration`, `timing-function`, `delay`
- Transitioning multiple properties
- `transition: all` — why it's usually wrong
- `@keyframes` declaration
- `animation` shorthand: `name`, `duration`, `timing-function`, `delay`, `iteration-count`, `direction`, `fill-mode`, `play-state`
- `animation-fill-mode`: `forwards`, `backwards`, `both`
- `animation-direction`: `alternate`, `reverse`
- `cubic-bezier()` in CSS
- CSS custom properties in animations
- `animation-timeline` (new) — scroll-driven animations
- `scroll-timeline` and `view-timeline`
- The View Transitions API — single-page transitions natively in the browser
- `@starting-style` — animating elements as they appear in the DOM

---

### Framer Motion / Motion Library (weeks 19-21)

**Resource:** motion.dev docs — read every page **Practice:** Weekly recreation challenges (see below)

- Installing and importing `motion` components
- `motion.div`, `motion.span`, etc.
- `animate` prop: final state
- `initial` prop: starting state
- `exit` prop: leaving state
- `transition` prop: how it gets there (duration, ease, spring, delay)
- `variants` for named animation states and choreography
- `AnimatePresence` for exit animations (elements leaving the DOM)
- Layout animations with `layout` prop
- Shared layout transitions with `layoutId`
- Gestures: `whileHover`, `whileTap`, `whileDrag`, `whileFocus`, `whileInView`
- Drag: `drag`, `dragConstraints`, `dragElastic`, `dragMomentum`
- `useScroll` and `useTransform` for scroll-linked animation
- `useSpring` for spring-based derived values
- `useMotionValue` for raw motion values
- `useMotionValueEvent` for reacting to motion value changes
- `MotionConfig` for global transition settings
- `LazyMotion` for code splitting

---

### Weekly Motion Recreations (weeks 14-26)

**One per week. Every recreation is a standalone React component saved to your playground.** **Format for each: reference screenshot/recording + your code + notes on technique in Obsidian**

- Week 14: Linear's hover states on dashboard items
- Week 15: Raycast's command palette open/close
- Week 16: Vercel's homepage hero animation
- Week 17: Arc's tab switcher
- Week 18: Linear's modal entrance with backdrop blur
- Week 19: Notion's drag-to-reorder block
- Week 20: Cursor's tab transitions
- Week 21: Stripe's number ticker (animated counting)
- Week 22: Liveblocks' multiplayer cursor positions
- Week 23: Linear's command palette filtering (items animating in/out)
- Week 24: Framer's drag interaction with snap points
- Week 25: Mercury's account switcher
- Week 26: Spring physics study — recreate Linear's springy list interactions

**By end of Phase 2:** 12+ motion recreations as a private playground. These become portfolio material.

---

### Phase 2 Design Milestones (end of month 6)

- [ ] 150+ design library entries
- [ ] Motion principles internalized — can articulate easing and duration choices from first principles
- [ ] CSS transitions and animations mastered
- [ ] Framer Motion mastered — all major APIs used in real recreations
- [ ] 12 motion recreations complete
- [ ] Job role at midpoint with concrete shipped work
- [ ] First essays published (must start month 4)

---

## PHASE 3 — Months 7-9: Rive, Advanced Motion, Marketing Site Recreations

**Split:** 20 min daily dissection + 70 min implementation (Rive / marketing sites / advanced UX)

---

### Rive (weeks 27-30)

**Resource:** rive.app/docs — work through everything **Why now:** Framer Motion is locked. Rive requires a new editor paradigm but shares the motion concepts you've built.**

#### Rive Concepts

- The Rive editor interface — artboards, animations, state machines
- Drawing tools and vector paths in Rive
- Bones and constraints for complex animations
- The runtime model: design once, animate everywhere
- **State machines** — the core of production Rive work:
    - Inputs: boolean, number, trigger
    - States and transitions
    - Conditions on transitions
    - Blend states (interpolating between animations)
    - Listeners (fire code on state entry/exit)
- Timeline animations vs state machine animations

#### Integration with React

- `@rive-app/react-canvas` package
- The `useRive` hook
- The `useStateMachineInput` hook for controlling state from React
- Fitting modes and alignment
- Handling load states
- Performance: Rive's WebGL renderer

#### What to Build in Rive

- A complex hover state animation (button, card, icon)
- A loading animation with multiple states (idle, loading, success, error)
- A marketing centerpiece animation with state machine inputs
- One serious Rive piece you're proud of — saved to portfolio playground

---

### Marketing Site Recreations (months 7-9)

**Three complete marketing site recreations. Each is a major portfolio piece.** **Frame each as a study, credit the original. Document process in case study format.**

#### Month 7-8: Linear's Homepage

The benchmark. Intense motion choreography, clean typography, 3D FIG illustrations.

**Focus areas:**

- All scroll-linked motion (`useScroll` + `useTransform`)
- All page transitions
- All hover interactions
- The FIG illustration section (3D via Blender or Three.js)
- Typography and spacing at pixel level
- Performance — must stay 60fps throughout

**Document:**

- Every significant motion decision (why this easing, why this duration)
- Every technical challenge and how you solved it
- Build time and what slowed you down

---

#### Month 8-9: Vercel's Homepage

Heavy Three.js usage. Particle systems. Gradient backgrounds. Clean typography with strong visual hierarchy.

**Focus areas:**

- React Three Fiber + drei setup
- Globe or mesh animation (whatever their current hero uses)
- Gradient backgrounds and grain effects
- Scroll choreography
- Light/dark mode transitions

**New concepts to learn for this:**

- React Three Fiber: `<Canvas>`, `useFrame`, `useThree`, `useLoader`
- drei helpers: `OrbitControls`, `Stars`, `MeshDistortMaterial`, `Float`
- GLSL shaders from within React Three Fiber
- Lenis smooth scroll library

---

#### Month 9: Raycast's Homepage

Grainy gradient hero. Bold typography. Fast, confident transitions.

**Focus areas:**

- Grain effect recreation (SVG filter or WebGL shader)
- The "blurred light column" hero background
- Typography-first layout
- GSAP for specific animations (practice this library here)
- Animation choreography on scroll

**New tools for this:**

- GSAP ScrollTrigger
- `@gsap/react` integration
- SVG `feTurbulence` + `feDisplacementMap` for grain

---

### Advanced UX Deepening (ongoing, weeks 27-39)

**Read and apply, one concept per week:**

#### Information Architecture

- IA vs navigation — what's the actual difference
- Card sorting methodology
- Tree testing
- The relationship between IA and search
- When to reorganise IA vs add better search

#### Flow Design Principles

- The job-to-be-done framework (JTBD)
- Task flows vs user flows vs wireflows
- Designing for decision fatigue
- Default values as design decisions
- Friction: where to add it (confirmation dialogs for destructive actions), where to remove it (reducing required fields)

#### Onboarding Design

- The "aha moment" and designing toward it
- Progressive disclosure in onboarding
- Empty state as onboarding
- The cost of forcing account creation
- Onboarding for power users vs new users

#### States as First-Class Concerns

- Empty states — not an afterthought, a designed experience
- Error states — specific, actionable, not blame-assigning
- Loading states — progress indication, skeleton screens, optimistic UI
- Offline states
- Permission-denied states
- Edge cases: very long strings, zero items, maximum items, special characters

#### Accessibility Depth

- WCAG 2.2 AA requirements (know them, not just know of them)
- VoiceOver on macOS — actually test your work with it
- Keyboard navigation: tab order, focus management, focus traps
- ARIA roles, states, properties — when to use and when HTML semantics suffice
- Colour contrast: 4.5:1 for normal text, 3:1 for large text
- Reduced motion: `prefers-reduced-motion` media query
- Designing for keyboard-first users (this is your audience at Linear/Raycast/Cursor)

---

### Advanced Visual Craft (weeks 27-39)

One focused session per week on each:

#### Color

- OKLCH color space — why it's perceptually uniform where HSL is not
- Building a full color system from scratch in OKLCH
- Chroma.js or culori.js for programmatic color work
- Accessible color palette generation (P3 gamut awareness)
- Analysing Linear's, Vercel's, Stripe's palettes in OKLCH

#### Typography

- Typeface anatomy in depth (x-height, cap height, ascenders, descenders, optical size)
- Variable fonts and OpenType features
- Optical sizing (`font-optical-sizing`)
- Contextual alternates, stylistic sets
- Tabular numerals in data-heavy UI (essential)
- Vertical rhythm and baseline grids
- The specific typefaces used at top companies: Inter, Geist, Söhne, ABC Diatype, GT America, Switzer, Berkeley Mono, JetBrains Mono
- _Practical Typography_ by Matthew Butterick (read online — free)

#### Iconography

- Stroke weight relative to context
- Optical adjustment for circles vs squares at same size
- Grid systems for icon design
- Designing 20 custom icons on top of a Lucide base
- When to use icons vs text vs both

#### Layout

- Recreate 5 marketing layouts pixel-perfect in CSS (no framework, just CSS Grid and Flexbox)
- Study every spacing decision — write down the rule each follows

---

### Phase 3 Design Milestones (end of month 9)

- [ ] 250+ design library entries
- [ ] 3 marketing site recreations live (Linear, Vercel, Raycast)
- [ ] One serious Rive piece complete
- [ ] WCAG 2.2 internalized — testing with VoiceOver
- [ ] OKLCH color system built for application project
- [ ] 8-10 essays published
- [ ] Advanced visual: color, type, icons studied with notes

---

## PHASE 4 — Months 10-12: Portfolio Build + Applications

**Split:** 20 min daily dissection + 70 min portfolio design/case studies

---

### Portfolio Site Design

**The site itself is a portfolio piece. Design it as such.**

**Reference benchmarks — study every one:**

- rauno.me
- emilkowal.ski
- paco.me
- joshwcomeau.com
- malte.me
- julianburr.de
- hamishw.com
- lee.so

**Required qualities:**

- Personality visible in 5 seconds
- Motion as primary design material (not sprinkled on top)
- Illustration work as visual identity
- Loads instantly — performance is part of the design
- Accessible
- Mobile-first
- No template — every decision yours

**Structure:**

- Homepage with strong first impression
- Work section — 4-6 detailed case studies
- Writing section — all essays
- About page — your story, used deliberately
- Optional: playground/lab section (motion experiments, shader demos)
- Optional: live learning garden (public Obsidian window)

---

### Case Study Production

**Each case study follows this exact narrative structure:**

1. **Problem and context** — what was being solved and why it mattered
2. **Constraints** — time, technical, business, team
3. **Explorations** — what was tried and killed, with visuals
4. **Decisions and tradeoffs** — why you chose what you chose
5. **Result** — shipped detail, screenshots, recordings, live link
6. **Reflection** — what you'd do differently

**Case studies to produce:**

- Application project (hero piece — most detailed)
- Linear homepage recreation (process + final result)
- Vercel homepage recreation
- Raycast homepage recreation
- 2-3 product redesign studies (UX system maps from Phase 1 expanded)
- Motion library (12-24 recreations as interactive gallery)
- Illustration body of work
- Lead designer job work (if NDA permits — negotiate before month 10)

---

### Blog

- 12-16 essays published by year end
- One every two weeks from month 4 onward
- Topics that show your POV:
    - Design decisions you made in your project and why
    - Dissections of specific products
    - Technical deep dives (how you built a specific animation, shader, component)
    - Opinions on direction of software design
    - Learning reflections (month milestones)

---

### Application Strategy

**Referrals beat applications.** Start building relationships in month 4 on Twitter.

**Timeline:**

- Months 4-9: engage publicly on Twitter, post work, reply thoughtfully
- Month 10: portfolio site live, start direct outreach to people you know
- Month 11: applications open, referrals activated
- Month 12: interviewing, negotiating

**The cold outreach template that works:**

> "I've been studying [specific thing they made]. I rebuilt [specific part] and learned [specific thing]. I'd love to show you [specific portfolio piece] when you have 10 minutes."

Lead with work. Never lead with "I'm looking for a job." The job offer comes after they see the work.

---

### Phase 4 Design Milestones (end of month 12)

- [ ] Portfolio site live at custom domain
- [ ] 5-6 case studies published
- [ ] 12-16 essays live
- [ ] Applications sent to all three tiers
- [ ] At least one referral from someone inside a target company
- [ ] 300+ design library entries — a full year's worth