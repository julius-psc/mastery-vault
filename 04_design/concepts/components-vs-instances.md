---
concept: components-vs-instances
discipline: design
status: mastered
topic: figma-mastery
date_started: 2026-05-24
date_mastered: 24/05/2026
tags:
  - "#status/learning"
  - "#disc/design"
related:
---

# Components vs Instances

## What it is

A Component in Figma corresponds to a reusable BLUEPRINT which can be re-used throughout a file (multiple diamonds). An Instance is an active, linked COPY of that component which can be recognized by a single hollow diamond. 
![[Screenshot 2026-05-24 at 14.59.52.png|401]]
Components are like classes in OOP (Object Oriented Programming) and Instances are the objects. 
The Component is the STAMP, the only source of truth. It states : structure, padding, constraints, typography and colours. When you edit anything, you reshape the stamp itself.
The Instance is the stamp IMPRESSION, a copy of the master that obeys its foundational rules. You can change properties like the content but you cannot break the layout (padding, margin) or the structure defined by the Component.

The only way to make changes to the Component from an Instance is to "push overrides to main component" which instantly updates the main Component and syncs all other Instances under that Component to match the new structure / layout which eliminates the need to find the main Component and manually adjust the layout.

## Why it matters (the underlying principle)
The underlying principle here is : Single Source of Truth (SSoT). Pushing overrides matters because it maintaints SwE integrity inside a design tool which is Figma. In programming, repeating code is a liability and in design, designing the same button twice is too.


## When to apply
- When tweaking a card instance inside a layout and realize that a specific margin is better than the previous
- An incorrect colour token is used while building a screen. Fix and push
- When the main component is in another file, pushing straight away removes the need to go manually hunt it down.

## When NOT to apply
- Never push unique data like usernames as doing so will override the main template with specific data which isn't scalable.
- For testing one-off exceptions that only need a local modification, not global
- If working on a shared multi-user library with other designers


## Mastery test

- [ ] Can articulate this principle without notes
- [ ] Date mastered: