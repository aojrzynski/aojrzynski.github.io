# AGENTS.md

## Project status

This repository is for Adam Ojrzynski’s personal portfolio / project site, currently called “The Workbench”.

The existing implementation should be treated as provisional. It was created through earlier Codex Cloud iterations and is not a fixed constraint.

This is now a design-led rebuild/pivot.

## Important instruction

Do not assume the existing architecture, framework, styling approach, file structure, or code should be preserved.

Everything is up for review, including:
- framework choice
- package dependencies
- styling approach
- component structure
- page structure
- existing CSS
- existing Astro implementation
- deployment approach, within reason

If starting again is the better option, recommend that clearly.

If keeping Astro is still the best option, explain why.

## Current repo state

The repo currently contains an Astro static site with pages for:
- Home
- ReadyRoll
- Agents Suite
- About

The existing content may be useful as raw material, but the implementation should not be treated as authoritative.

## Design source of truth

The Figma design is the primary source of truth.

When Figma MCP is available, use the currently selected Figma frame/page as the design source. Do not use older Figma pages or older versions unless explicitly asked.

Screenshots are secondary reference material only.

## Visual direction

The intended design direction is a minimal, editorial project site influenced by Japanese ink-brush / sumi-e / ensō aesthetics.

This does not mean the site should look like a themed “Japanese” website. Avoid clichés, decorative motifs, fake calligraphy, lanterns, temples, waves, or anything that feels like pastiche.

The useful inspiration is:
- off-white or warm white backgrounds
- strong use of negative space
- restrained black, charcoal, and vermilion/red contrast
- sparse composition
- quiet asymmetry where appropriate
- small deliberate marks rather than heavy decoration
- thin rules, subtle dividers, and carefully placed accents
- a hand-crafted / workshop feeling without looking messy
- calm, precise, editorial layout

Think of the visual feel as:
- minimal editorial
- quiet workshop
- ink mark / red seal / black brush reference
- practical and restrained
- modern, but not generic SaaS

Avoid:
- generic SaaS landing page style
- heavy gradients
- glassmorphism
- excessive animations
- random icon sets
- overdesigned cards
- noisy visual effects
- stock tech/startup aesthetics
- corporate buzzword aesthetics
- literal Japanese-themed decoration

## Goal

Build a polished, minimal, editorial-style personal project site that reflects:
- practical software projects
- data/product work
- ReadyRoll
- the Agents Suite
- careful, traceable, useful systems
- practical AI without hype

The site should feel calm, precise, minimal, and professional.

It should not feel like:
- a startup landing page
- a corporate portfolio template
- a flashy AI product site
- a generic developer blog
- a theme copied from a design trend

## Content tone

Use plain English.

Prefer direct, grounded copy over marketing language.

The tone should be:
- clear
- calm
- confident
- practical
- understated

Avoid:
- hype
- grand claims
- excessive adjectives
- corporate-speak
- AI buzzwords unless they are genuinely relevant

## Development approach

Before major implementation, inspect:
1. the current codebase
2. the selected Figma frame via Figma MCP
3. the project goal
4. deployment needs

Then recommend an implementation approach.

Do not jump straight into editing code if a stack/framework decision is still unresolved.

## Implementation preference

Prefer simple, maintainable code.

This is a mostly static portfolio/project site, so avoid unnecessary complexity.

Use clean HTML, accessible structure, good responsive behaviour, and clear styling.

The visual design should be implemented through deliberate layout, spacing, typography, colour, borders, and small accent details rather than heavy decorative effects.

## Design implementation priorities

When translating the Figma design into code, prioritise:

1. Overall layout fidelity
2. Spacing and whitespace
3. Typography scale and line height
4. Colour accuracy
5. Header and footer proportions
6. Card sizing and rhythm
7. Accent mark placement
8. Responsive behaviour
9. Simplicity and maintainability

Do not “improve” the design by adding extra visual features unless explicitly asked.

## Safety

Before large rewrites:
- explain the proposed approach
- list the files likely to change
- avoid deleting useful content without preserving or migrating it
- keep routes and links sensible unless a better structure is proposed
- run build checks where possible