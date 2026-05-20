# Tag Registry

## Status Tags - every concept note gets one

- #status/learning
- #status/mastered
- #status/maintenance
- #status/stuck

## Discipline Tags - applied to anything cross-cutting

- #disc/engineering
- #disc/design
- #disc/illustration
- #disc/motion

## Topic Tags - finer-grained, applied to concepts

- #topic/javascript
- #topic/typescript
- #topic/rust
- #topic/swift
- #topic/react
- #topic/dom
- #topic/css
- #topic/figma
- #topic/blender
- #topic/shader
- #topic/easing
- #topic/spring
- #topic/choreography
- #topic/typography
- #topic/color
- #topic/composition

## Source Tags - for dissections and references

- #source/linear
- #source/raycast
- #source/vercel
- #source/cursor
- #source/stripe
- #source/article
- #source/talk
- #source/book
- #source/code

## Special Tags

- #review/weekly
- #review/monthly
- #question
- #realization

#### Tag rules

- Always use the slash hierarchy (`#status/learning`, not `#learning`). Obsidian groups these in the tag pane automatically.
- Don't invent tags casually. If you need a new one, add it to a `00_system/tags.md` registry first. This prevents tag sprawl.
- Tag in YAML frontmatter for properties (status, discipline, topic), tag inline for transient things (`#question`, `#realization`).