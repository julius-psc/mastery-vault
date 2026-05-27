# Illustration

**Daily block:** Alternates with Motion — illustration on odd days, motion on even days **Typical session:** 1-1.5 hours **Tools:** Figma (vector) | Blender (3D) | Photoshop or Affinity Photo (raster/grain) | VS Code with GLSL extension (shaders) **Target aesthetic:** Linear FIG illustrations | Raycast grainy gradients | Vercel Three.js compositions

---

## The Three Aesthetics You Are Learning to Produce

**1. The Linear FIG Aesthetic** Isometric 3D objects (Blender-rendered or vector), stylized line work, ambient occlusion in corners, 1-2 accent colors on near-black background, annotation typography in mono (FIG_01 labels, leader lines), schematic technical feel. Clean, instrument-like, purposeful.

**2. The Raycast / Vercel Gradient Aesthetic** Volumetric light columns, heavy grain overlay, deep dark backgrounds, selective color bloom (usually one or two saturated hues against near-black), blurred and diffused light sources. Feels physical and analog despite being digital.

**3. The WebGL / Shader Aesthetic** Procedural, code-generated visuals. Noise fields, signed distance fields, ray marching, particle systems. Appears on Vercel, Stripe, and Framer homepages. Requires GLSL knowledge.

By Phase 3 you can produce all three. By Phase 4 you have a personal signature that blends them in a recognisable way.

---

## PHASE 1 — Months 1-3: Visual Literacy + Blender Foundations

**Session structure (1-1.5 hrs per illustration day):**

- Weeks 1-4: theory and visual analysis (no production yet)
- Weeks 5-8: Blender Donut tutorial
- Weeks 9-13: first isometric pieces

---

### 1A — Composition Fundamentals (weeks 1-2)

Research each concept. Write a concept note. Find 3 examples in the wild.

- **Rule of thirds** applied to UI illustration (not photography — the application is different)
- **Visual hierarchy in illustration** — where the eye goes first, second, third, and why
- **Negative space** — how much breathing room the Linear illustrations have vs how cluttered most illustrations feel
- **Balance** — symmetric (stable, formal), asymmetric (dynamic, modern), radial (centred, unified)
- **Focal points** — how they are created: contrast in value, isolation, scale difference, color accent
- **Leading lines** — guiding the eye to the focal point
- **Framing and edges** — how objects are cropped at the artboard boundary
- **Depth** — overlapping, size scaling, atmospheric perspective, value shift

- [ ] **Study exercise:** Take 10 Linear FIG illustrations. For each, sketch the compositional skeleton (just lines showing where focal points and leading lines are). Document in your illustration studies folder.

---

### 1B — Light and Shadow (weeks 2-3)

- **Direct light** — hard, defined shadows, strong highlights
- **Ambient light** — soft, fills shadows, reduces contrast
- **Bounce light** — light reflected off surfaces onto other surfaces
- **Three-point lighting setup** — key light (main), fill light (soften shadows), rim light (separate subject from background)
- **Ambient occlusion** — the darkening that occurs where surfaces meet, in corners, in recesses. This is the subtle effect that gives Linear illustrations their depth.
- **Soft shadows vs hard shadows** — distance and size of light source determine this
- **Color temperature** — warm key light (sun-like) with cool fill (sky-like) is a classic combo
- **Light direction and emotional impact** — top-down light is neutral, side light is dramatic, under light is sinister

**Study exercise:** Take 5 Linear FIG illustrations. Identify: where is the key light coming from? Is there ambient occlusion? What is the shadow direction? Document with annotations.

---

### 1C — Color Theory for Illustration (weeks 3-4)

- **Color wheel** — hue, saturation, value (HSV not RGB)
- **Color harmonies:**
    - Complementary (opposite on wheel) — high contrast, vibrant
    - Analogous (adjacent on wheel) — harmonious, calm
    - Triadic — balanced, diverse
    - Split-complementary — contrast without harshness
- **Saturation and mood** — high saturation = energetic, low saturation = sophisticated
- **Value (lightness) as structure** — composition reads in value before color
- **Limited palettes** — why they work: coherence, focus, professionalism
- **Analyzing Linear's palette:** near-black background, one or two accent colors (usually blues or greens), white wireframe lines, subtle gradient tones
- **Analyzing Raycast's palette:** black background, vivid red/pink/blue light bleed, grain texture
- **Analyzing Vercel's palette:** pure black, pure white, subtle gradients, no decorative color

**Study exercise:** Extract the color palette from 5 illustrations you admire. Build them as Figma color swatches. Write a 3-sentence analysis of each.

---

### 1D — Isometric Geometry (weeks 4-5)

- **True isometric vs game isometric:**
    - True isometric: all three axes at equal angles (30° from horizontal)
    - Game isometric: 26.57° (2:1 pixel ratio) — looks different
    - Linear uses true isometric
- **The isometric grid** — setting it up in Figma (angle: 30°)
- **Building basic forms:** cube, rectangular prism, cylinder (approximated), sphere (approximated)
- **Stacking and compositing forms** — how to build complex objects from primitives
- **Setting up the isometric camera in Blender:**
    - Camera type: Orthographic
    - Rotation: X=54.7356°, Z=45° (true isometric)
    - Scale to fit your object
- **The Linear FIG visual style specifically:**
    - White wireframe outlines (`viewport` in Blender or Freestyle)
    - Dark fill for face surfaces
    - Subtle gradient on faces (light from above-left typically)
    - Ambient occlusion baked in
    - Optional: schematic annotation (FIG_01, leader lines, mono font labels)

**Study exercise:** Draw a cube in true isometric in Figma using only the pen tool and the isometric grid. Then draw a stack of three cubes. This teaches the geometry before Blender does it automatically.

---

### 1E — Blender Absolute Basics (weeks 5-8)

**Start here: The Donut Tutorial by Blender Guru (YouTube)** About 6 hours of content. Do it slowly. Understand every step. Do not rush.

After the donut, you should know:

**Interface:**

- Viewport navigation: orbit (middle mouse / trackpad), pan, zoom
- Numpad views (1, 3, 7 for front, right, top — 5 for ortho/perspective)
- Object mode vs Edit mode (Tab to toggle)
- The outliner, properties panel, timeline

**Modeling:**

- Adding primitives: `Shift+A`
- Transforms: G (grab/move), R (rotate), S (scale) + X/Y/Z to constrain axis
- The 3D cursor and using it as pivot point
- Extrude (E), Inset (I), Loop cut (Ctrl+R)
- The modifier stack:
    - Bevel (chamfer edges)
    - Subdivision Surface (smooth geometry)
    - Boolean (combine/subtract shapes)
    - Array (repeat geometry)
    - Mirror (symmetry)
    - Solidify (give flat surfaces thickness)
- Edge loops and basic topology (why topology matters for subdivision)

**Materials:**

- The Principled BSDF shader — Base Color, Metallic, Roughness, Normal
- The shader editor (node-based)
- Emission shader for glowing elements
- Material slots and assigning materials to faces

**Rendering:**

- Eevee vs Cycles (use Eevee for speed in Phase 1)
- Basic lighting: Area light, Sun light, Point light
- Rendering to PNG
- Ambient occlusion in Eevee render settings

**Camera:**

- Adding a camera
- Setting orthographic projection
- The isometric camera setup (X=54.7356°, Z=45°)
- Rendering at 1:1 or 4:3 for illustrations

---

### 1F — First Isometric Pieces (weeks 9-13)

**Goal: produce 4-6 pieces. Quality is low. Learning is high. Don't judge the output.**

**Piece 1 — Week 9:** Simple stacked slabs. Three rectangular boxes stacked with slight offset. Isometric camera. White line render style. Study the Linear FIG 0.2 illustration.

**Piece 2 — Week 10:** Grouped cubes. Six cubes arranged in a cluster (similar to Linear FIG 0.3). Focus on getting the line render right.

**Piece 3 — Week 11:** Layered cards/panels. Flat rectangular panels stacked with perspective offset (similar to Linear FIG 0.4). Add a Figma UI element composited on top.

**Piece 4 — Week 12:** A device or abstract object of your choice. Apply what you've learned.

**Piece 5-6 — Week 13:** Attempt to recreate one Linear FIG illustration as faithfully as possible. Choose the one that interests you most.

**For each piece, document in Obsidian:**

- The reference you were working from
- Techniques you used
- What went wrong
- What you'd do differently

---

### Phase 1 Illustration Milestones (end of month 3)

- [ ] Composition, light, shadow, color theory concept notes complete
- [ ] Blender Donut finished
- [ ] 4-6 isometric pieces in Linear style (rough, not portfolio quality)
- [ ] 50+ illustration references saved with technique notes
- [ ] Isometric camera setup memorised

---

## PHASE 2 — Months 4-6: Blender Intermediate + Grain + Shaders Intro

**Session structure:** Alternate illustration/motion days. Illustration sessions: 1-1.5 hrs. **Weeks 14-17:** Blender intermediate **Weeks 18-22:** Grain, noise, texture **Weeks 23-26:** Shaders introduction

---

### 2A — Blender Intermediate (weeks 14-17)

**The modifier stack in depth:**

- Bevel with `Weight` mode (selective beveling)
- Subdivision Surface with crease edges
- Boolean with exact solver
- Array with object offset for complex patterns
- Screw modifier for rotational objects
- Solidify for panels and flat objects
- Displace for surface variation

**Edge loops and topology:**

- Why clean topology matters (subdivision deformation)
- Avoiding ngons (faces with more than 4 sides) in subdivision objects
- Pole management (where 5+ edges meet)
- Using the knife tool

**Materials in depth:**

- The node editor fully
- Mixing shaders with `Mix Shader`
- Procedural textures: `Noise Texture`, `Voronoi Texture`, `Wave Texture`
- Normal maps and bump maps
- Metallic and clearcoat setups
- Transparent materials (glass, acrylic)

**Stylized rendering:**

- **Freestyle** — Blender's non-photorealistic line renderer
    - Line sets and line styles
    - Edge types: Silhouette, Crease, Edge Mark
    - Line thickness and color
    - Getting the Linear wireframe look from Freestyle
- **Workbench renderer** for flat, schematic looks
- **Geometry Nodes** introduction:
    - The node editor for geometry
    - Distribute Points on Faces
    - Instance on Points
    - Simple procedural patterns

**Lighting setups for illustration:**

- The three-point setup in 3D
- HDRI lighting for realism
- Rim lighting to separate objects from background
- Area lights positioned for the isometric look
- Multiple colored lights for the Raycast volumetric look

**Render passes and compositing in Blender:**

- Combined, Diffuse, AO, Shadow passes
- The compositor node editor
- Using the AO pass for overlay darkening
- Glare node for bloom effects
- Color grading in the compositor

---

### 2B — Schematic Technical Illustration Aesthetic (weeks 18-19)

This is the precise aesthetic of Linear's marketing illustrations. Study it systematically.

**Visual language elements:**

- Wireframe outlines (white, ~1px weight) over dark or filled surfaces
- Face fills that are darker than the background by a small amount (not solid black, not textured — subtle)
- Subtle gradient on each face showing light direction (very subtle)
- Ambient occlusion shadows in corners and recesses
- 1-2 accent color elements (blue glows, highlighted selected rows)
- Annotation typography in monospace font (Berkeley Mono or similar)
- Leader lines from annotation to element (thin, with small terminal dots)
- Registration marks and grid backgrounds (dotted grid, very low opacity)
- "FIG_01" or "FIG 0.2" label conventions (top-left, small, mono font)
- All caps labels for annotations

**How to produce this in Blender:**

1. Model your object
2. Apply materials: dark gray face fills with subtle gradient using Shader + Geometry nodes
3. Enable Freestyle: Silhouette + Crease edge sets, white line color, 1-1.5px
4. Add accent elements with Emission shader (blue/teal)
5. Render to PNG (Eevee)
6. Import to Figma or Photoshop
7. Add annotation typography (Berkeley Mono or JetBrains Mono)
8. Add leader lines (thin lines with terminal circles)
9. Add FIG label
10. Add registration marks (dotted grid background, very low opacity)
11. Final composite

**Practice:** Produce 2 pieces in this exact style, following the steps above.

---

### 2C — Grain, Noise, Texture (weeks 20-22)

**The physical basis of grain:** Photographic film grain is silver halide crystal randomness. Digital grain simulates this with noise functions. The warmth it adds is from introducing analog imperfection into digital perfection.

**Procedural noise types:**

- **Perlin noise** — smooth gradient noise, organic-looking, most common
- **Simplex noise** — faster, better distribution than Perlin
- **Worley noise** — cellular pattern, looks like cells or stones
- **Voronoi** — distance-field based cells with sharp edges

**Grain in Photoshop / Affinity Photo:**

- Add Noise filter (monochromatic, gaussian distribution)
- Overlay or Screen blend mode at low opacity (2-8%)
- Multiple layers with different scales for richness
- Fine grain: small radius (0.5-2px), more uniform
- Coarse grain: larger radius (2-5px), more texture

**Grain in CSS / SVG:**

- `<feTurbulence>` filter — generates noise in SVG
    - `type="fractalNoise"` vs `type="turbulence"`
    - `baseFrequency` — how fine the grain is (0.65 is typical)
    - `numOctaves` — complexity (3-4 is typical)
- `<feColorMatrix>` to adjust contrast
- `<feBlend>` to composite with source
- Apply as an SVG filter on a pseudo-element overlay
- Set `pointer-events: none` on the grain overlay

**Grain in WebGL (intro):**

- `fract(sin(dot(co, vec2(12.9898, 78.233))) * 43758.5453)` — classic GLSL hash function
- Adding noise to fragment shader output
- Animating grain with `uTime` for film-like flicker

**The Raycast gradient hero:**

- Near-black background
- 2-3 large, blurred, heavily diffused light sources (Area lights in Blender, or CSS radial gradients)
- Colors: typically one warm (red/pink) and one cool (blue/teal)
- Directional — light comes from one side or corner
- Heavy grain overlay (5-10% opacity, fine grain)
- Reproduced in Blender: add large plane objects with Emission material off-camera, high bloom in Eevee, render, add grain in post
- Reproduced in CSS: radial gradients with blur + SVG grain overlay

**Gradient mesh techniques:**

- In Figma: multiple overlapping ellipses with radial fills, varied opacity
- In Photoshop: the Gradient Mesh tool
- In CSS: layered `radial-gradient()` with `mix-blend-mode: screen`

**Practice (weeks 20-22):**

- 3 Raycast-style gradient backgrounds: one in Blender, one in Photoshop, one in CSS
- Apply grain to each using different methods
- Document which method you prefer and why

---

### 2D — Shaders Introduction (weeks 23-26)

**Resource:** The Book of Shaders (thebookofshaders.com) — free, the canonical introduction **Additional:** Shadertoy (shadertoy.com) — study others' shaders before writing your own

**What a shader is:** A shader is a program that runs on the GPU, executed once per pixel (fragment shader) or once per vertex (vertex shader). It takes inputs (position, UV coordinates, uniforms) and outputs a color. They are massively parallel — all pixels computed simultaneously.

**GLSL basics:**

```glsl
// Types
float, int, bool
vec2, vec3, vec4  // vectors
mat2, mat3, mat4  // matrices

// Uniforms (passed in from CPU/JS)
uniform float uTime;
uniform vec2 uResolution;

// Varyings (passed from vertex to fragment shader)
varying vec2 vUv;

// Built-in functions
sin(), cos(), tan()
abs(), floor(), ceil(), fract()
min(), max(), clamp()
mix(a, b, t)  // linear interpolation — use constantly
smoothstep(edge0, edge1, x)
length(v)     // vector magnitude
normalize(v)  // unit vector
dot(a, b)     // dot product
```

**Concepts from The Book of Shaders (work through these chapters):**

- Chapter 5: Shaping functions — how to make smooth, controllable curves in GLSL
- Chapter 6: Colors — working with color in GLSL, HSB vs RGB
- Chapter 7: Shapes — drawing circles, rectangles with signed distance functions
- Chapter 8: Matrices — transforms in shader space
- Chapter 9: Patterns — tiling, repetition using `fract()`
- Chapter 10: Random — generating pseudo-random numbers in GLSL
- Chapter 11: Noise — implementing Perlin-like noise in GLSL
- Chapter 13: Fractal Brownian Motion — layering noise octaves

**Shadertoy practice:**

- Find 5 shaders with fewer than 50 lines. Read each one fully.
- Pick one you almost understand and modify it until you do understand it.
- Build 3 shaders yourself:
    1. A gradient background (practice `mix` and UV coordinates)
    2. A noise field that animates with time
    3. A circle with soft edges (practice smoothstep and SDF)

---

### Phase 2 Illustration Milestones (end of month 6)

- [ ] 3 polished Blender pieces in the Linear schematic style
- [ ] 3 Raycast-style grainy gradient pieces (one Blender, one Photoshop, one CSS)
- [ ] 3 shaders running on Shadertoy
- [ ] Freestyle line rendering fully understood
- [ ] Can reproduce grain effect in at least 2 different tools

---

## PHASE 3 — Months 7-9: Advanced Blender + Advanced Shaders + Signature Style

**You're producing portfolio-quality work in this phase.**

---

### Advanced Blender (weeks 27-31)

**Complex modeling:**

- Hard surface modeling (mechanical, precise, industrial)
- Curved surfaces with subdivision (organic forms)
- Modeling from reference (import reference images, model to match)
- Clean mesh for subdivision (pole management, loop flow)

**Advanced materials:**

- Full PBR workflow (Albedo, Metallic, Roughness, AO, Normal maps)
- Procedural material networks (10+ nodes, fully parametric)
- Layered materials using Mix Shader and masks
- Subsurface scattering for organic materials
- Shader to RGB for toon/stylized rendering

**Advanced lighting:**

- Multiple HDRI setups for different moods
- Mixing HDRI with manual lights
- Light linking (Blender 4.0+) — control which lights affect which objects
- Volumetric lighting (the Raycast light column aesthetic, in 3D)
- Area lights with custom shapes

**Geometry Nodes depth:**

- Building procedural objects that are controlled by parameters
- Instance on points for scattering
- Fields and attributes
- Creating a procedural grid or pattern for schematic backgrounds

**Compositing in Blender:**

- Full multi-pass composite: Diffuse + Specular + AO + Emission + Shadow
- Glare / bloom node
- Color Correction node
- Lens Distortion for subtle imperfection
- Mixing 3D render with flat color passes

---

### Advanced Shaders (weeks 27-35)

**Noise-based effects:**

- fBm (Fractal Brownian Motion) — layered noise for organic textures
- Domain warping — distort noise coordinates for swirling effects
- Turbulence — `abs(noise)` for sharper features
- Animated noise with `uTime`

**Signed Distance Functions (SDFs):**

- SDF for a circle: `length(p) - r`
- SDF for a rectangle: `max(abs(p) - b)`
- Boolean operations: union (`min`), intersection (`max`), subtraction
- Smooth union with `smin` function
- Building complex shapes from primitive SDFs
- Using SDFs to create sharp or soft edges

**Ray marching:**

- The ray marching algorithm: cast ray from camera, step along it, check SDF
- `march()` loop in GLSL
- Surface normals from SDF gradient
- Basic lighting in ray-marched scenes
- This is how the Vercel globe effects are typically built

**React Three Fiber shaders:**

- `shaderMaterial` from drei
- Passing uniforms from React (including animated values)
- `useFrame` for `uTime` uniform updates
- Vertex shader for mesh deformation (MeshDistortMaterial, custom)
- Fragment shader for custom surface appearance

**One shader portfolio piece:** Build a single shader that would be appropriate for a marketing site hero. It should:

- Animate fluidly on its own
- Accept at least one interactive input (mouse position or scroll)
- Look intentional, not random

---

### Compositing — Combining Everything (weeks 32-39)

This is the signature technique: combine 3D render + grain + vector overlays + typography.

**The workflow:**

1. Model and render the 3D element (Blender)
2. Export with transparency or on dark background
3. Import into Figma or Photoshop
4. Add annotation typography layer (mono font, leader lines)
5. Add grain overlay layer (use your SVG filter or texture)
6. Add color correction layer (subtle curves, slight warm/cool shift)
7. Add glitch or texture accent if appropriate
8. Export at 2x for retina

**Personal style development:** This is the phase where you stop copying references and start making original work. Ask:

- What visual decisions do I keep making instinctively?
- What color palette am I drawn to?
- What level of grain feels right to me?
- How much annotation vs how much raw 3D?
- Linear style, Raycast style, or your own mix?

Write a 500-word "visual manifesto" in your vault describing your illustration POV. This becomes part of your About page later.

**Monthly pieces:**

- **Month 7:** One polished "Linear FIG" original illustration — your concept, not a copy (~10 hrs). Document the full process.
- **Month 8:** One polished Raycast-style piece — a concept that justifies the aesthetic (~10 hrs). Document the full process.
- **Month 9:** One signature piece combining 3D + grain + shader + type (~15-20 hrs). This is the piece you put on the homepage of your portfolio.

---

### Phase 3 Illustration Milestones (end of month 9)

- [ ] One polished original Linear-style illustration
- [ ] One polished original Raycast-style piece
- [ ] One signature combined-technique piece
- [ ] Personal visual manifesto written
- [ ] Ray marching basics understood (at least one ray-marched shader)
- [ ] SDF shapes mastered
- [ ] Compositing workflow fully understood

---

## PHASE 4 — Months 10-12: Portfolio Illustrations

**Produce 2-3 hero illustrations specifically for your portfolio site. These are the best things you've made.**

---

### Portfolio Illustration Objectives

**Homepage hero illustration:** Your signature piece from month 9, refined. Or a new piece designed specifically for the portfolio's concept. This is what people see first when they open your portfolio. It should immediately communicate: taste, craft, POV.

**Case study illustrations:** Each major case study gets a hero image that's illustrative, not a screenshot. For the application project, design an isometric exploded-view illustration of the app's architecture (in the Linear FIG style). For the marketing site recreations, create thumbnail illustrations.

**About page illustration:** A small, personal illustration that represents you. Could be abstract, could be conceptual. Should feel like a signature.

---

### Refinement Process

For each portfolio piece:

1. Produce a rough version (you have the skills now)
2. Leave it for 48 hours
3. Come back with fresh eyes and write down everything that bothers you
4. Fix all of those things
5. Repeat once more
6. Final export at 2x, WebP format for web, PNG for case study downloads

---

### Phase 4 Illustration Milestones (end of month 12)

- [ ] Homepage hero illustration final
- [ ] Case study illustrations complete for each major piece
- [ ] About page illustration complete
- [ ] All illustrations exported at correct resolutions for web
- [ ] Visual manifesto reflected in the portfolio's About page

---

## Reference Library (build throughout the year)

Save everything to `05_illustration/references/`. Target: 5+ new references per week.

**Primary sources:**

- Linear marketing page (linear.app)
- Vercel marketing page (vercel.com)
- Raycast marketing page (raycast.com)
- Resend (resend.com)
- Clerk (clerk.com)
- Stripe (stripe.com)
- Liveblocks (liveblocks.io)
- Framer (framer.com)
- Basehub (basehub.com)
- Planetscale (planetscale.com)

**Secondary sources:**

- Dribbble (filtered: dark, minimal, 3D)
- Behance (filtered: illustration, 3D)
- Awwwards (for motion + illustration combined)
- The FWA (high-craft WebGL)
- Godly.website (curated)

**For shaders specifically:**

- Shadertoy.com
- GLSL Sandbox
- Codrops (tympanus.net) — high-quality creative development tutorials