# Workbench Figma Design Summary

This file is the local implementation reference for the design-led rebuild of Adam Ojrzynski's personal portfolio/project site, "The Workbench".

## Source Of Truth

- Local instruction source: `AGENTS.md`
- Figma file: `Workbench`
- Figma file key: `gCRk9abwvW0XXRpOku7TcN`
- Figma page: `Original` (`0:1`)
- Implementation approach: keep Astro, use semantic templates and plain CSS, do not use Tailwind or generated absolute-positioned Figma code.

Inspected final frames:

- Home: https://www.figma.com/design/gCRk9abwvW0XXRpOku7TcN/Workbench?node-id=7-1450&m=dev
  - Node: `7:1450`
  - Type: frame
  - Name: `FINAL Homepage - implement this`
  - Size: `1536 x 3145`
- ReadyRoll: https://www.figma.com/design/gCRk9abwvW0XXRpOku7TcN/Workbench?node-id=22-5252&m=dev
  - Node: `22:5252`
  - Type: frame
  - Name: `FINAL ReadyRoll page - implement this`
  - Size: `1536 x 5199`
- Agents Suite: https://www.figma.com/design/gCRk9abwvW0XXRpOku7TcN/Workbench?node-id=15-3510&m=dev
  - Node: `15:3510`
  - Type: frame
  - Name: `FINAL Agents Suite Page - implement this`
  - Size: `1536 x 6079`
- About: https://www.figma.com/design/gCRk9abwvW0XXRpOku7TcN/Workbench?node-id=26-5756&m=dev
  - Node: `26:5756`
  - Type: frame
  - Name: `FINAL About Page - implement this`
  - Size: `1536 x 2092`

## AGENTS.md Constraints

- Treat the existing Astro implementation, CSS, file structure, and previous generated work as provisional.
- Use the final Figma frames as the design source of truth.
- Preserve useful content, but prioritize visual fidelity to Figma.
- Keep the tone plain, calm, practical, and understated.
- Avoid generic SaaS, startup, glass, heavy-gradient, decorative Japanese-themed, or stock-tech styling.
- Prefer simple, maintainable static code with accessible HTML and responsive behavior.

## Shared Design System

### Typography

- Primary font: Inter.
- Implementation should load Inter weights `400` and `500` via a simple Google Fonts stylesheet.
- Fallback: `ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`.
- Home H1: about `72px / 79.2px`, medium, tight tracking.
- Interior H1: about `60px / 66px`, medium, tight tracking.
- Home lead: `24px / 39px`.
- Interior lead: `20px / 32.5px`.
- Section H2: mostly `24px / 32px`, with selected large editorial H2 at `30px / 36px`.
- Card H2/H3: `36px / 45px` for feature titles; `18px / 28px` for small cards.
- Body copy: `16px / 26px`.
- Small copy and metadata: `14px / 20px` or `14px / 22.75px`.
- Labels: `12px / 16px`, uppercase, `0.6px` letter spacing.

### Colours

- Paper background: `#faf9f7`
- Surface: `#f5f4f1`
- Soft panel wash: `rgba(232, 230, 225, 0.3)` and `rgba(232, 230, 225, 0.5)`
- Ink: `#1a1818`
- Muted: `#6b6866`
- Accent/vermilion: `#c74634`
- Main border: `rgba(26, 24, 24, 0.12)`
- Soft border: `rgba(26, 24, 24, 0.07)`
- Fine divider: `rgba(26, 24, 24, 0.05)` or `rgba(26, 24, 24, 0.06)`
- Accent soft: `rgba(199, 70, 52, 0.3)`, `0.4`, `0.5`, `0.6`

No Figma variables were published for these frames, so the code should define local CSS variables from these values.

### Spacing And Layout Widths

- Desktop frame width: `1536px`.
- Main centered shell: `1152px`, positioned at x `192px` in Figma.
- Shell side padding: `24px`, so primary content often begins at x `216px`.
- Full content width inside shell: `1104px`.
- Prose widths: `672px`, `768px`, and `896px`.
- Feature card inner padding: `48px`.
- Panel/callout padding: usually `41px` or `49px`.
- Small cards: `496px` wide in two columns with `32px` gap.
- Header height: `69px`; footer height: `101px`.
- Hero top on interior pages: red rule at y `165px`, H1 at y `209px`.
- Home hero is intentionally lower and more spacious.
- Section rhythm uses large gaps, usually `64px`, `80px`, or `96px`.

### Marks, Borders, Panels

- Hero rule: `80px x 4px`, accent.
- Section heading rule: `48px x 4px`; home Working Principles uses `64px x 4px`.
- Brand header mark: `6px x 28px`, accent.
- Footer brand mark: `4px x 20px`, accent.
- Dot marks: `4px` or `6px`, circular accent.
- Cards and panels are square-edged, no rounded card look. Use `border-radius: 0`.
- Feature cards use `#f5f4f1`, `1px` ink border, and a top accent gradient/rule.
- Callouts use a soft wash background, soft border, and a vertical accent bar.
- Links use accent text plus a subtle accent underline and a small arrow/external indicator.

## Reusable Implementation Patterns

- `BaseLayout`: document shell, metadata, Inter stylesheet, global CSS, header/footer.
- `Header`: brand mark, nav links, active state using current path.
- `Footer`: brand mark, GitHub icon link, LinkedIn icon link, ReadyRoll external text link.
- `Hero`: red rule, H1, optional lead, prose block, optional CTA.
- `SectionHeading`: red horizontal rule plus heading.
- `FeatureCard`: label, title, description, narrative quote/bar, metadata grid, optional progression chips, CTA.
- `CalloutPanel`: soft panel with vertical accent bar, label/title/body.
- `SmallCardGrid`: two-column desktop card grid, single-column mobile.
- `DotList`: reusable two-column or stacked lists with small red dots.
- `Timeline`: numbered circles with optional connector lines.
- `MetadataGrid`: uppercase label and value pairs.
- `TextLink`: accent link with arrow/external cue.

## Page Structures

### Home

- Shared header.
- Hero: The Workbench, lead, explanatory paragraph, byline.
- ReadyRoll feature card.
- Agents Suite feature card with progression chips.
- Future work callout.
- Working Principles section with five dot-list items.
- Shared footer.

### ReadyRoll

- Shared header.
- Hero with ReadyRoll title, lead, two paragraphs, external CTA.
- Product Status callout.
- Prose sections: Why this exists, Why accountless.
- What ReadyRoll does: two-column feature cards, seven items.
- How it works: numbered steps inside a panel.
- Built for group chat prose section.
- Where ReadyRoll is heading: roadmap panel with four items.
- Technical notes: soft panel with two-column bullet list.
- Large whitespace before shared footer is intentional.

### Agents Suite

- Shared header.
- Hero with title, lead, two paragraphs.
- What this suite is exploring: four small cards.
- Learning Progression: heading, short paragraph, timeline panel with covered and planned stages.
- Completed Agents: three large feature cards, each with label, title, summary, details, and GitHub CTA.
- Planned Agents: soft panel with grouped dot-list items and italic note.
- Where this is heading: prose section with top divider.
- Shared footer.

### About

- Shared header.
- Hero with title and two intro paragraphs.
- Prose sections: How I got here, Why The Workbench exists.
- How I like to build: two-column dot-list items.
- Contact section with LinkedIn and GitHub links plus note.
- Shared footer.

## Responsive Assumptions

- Only desktop Figma frames were supplied.
- Mobile/tablet should preserve the visual language while adapting responsibly:
  - Reduce large desktop offsets.
  - Stack nav as needed without overlap.
  - Use single-column card grids.
  - Let prose widths become fluid.
  - Keep red rules, dot marks, and panel styles.
  - Avoid text clipping, horizontal scrolling, and overlapping footer/header links.

## Implementation Risks

- Exact desktop spacing may need visual tuning after browser screenshots.
- Inter rendering can differ slightly between local/system and Google Fonts.
- No mobile Figma frames exist, so responsive layout is inferred.
- Do not depend on expiring Figma asset URLs.
- The Figma MCP output is React/Tailwind reference code, not implementation code.
- GitHub Pages is compatible with the current static Astro deployment.

## Things Not To Add

- Tailwind.
- Figma-generated absolute-positioned React code.
- Glassmorphism, heavy gradients, decorative blobs, or extra animation.
- Literal Japanese motifs, fake calligraphy, lanterns, temples, waves, or visual pastiche.
- Generic SaaS landing-page sections or marketing-heavy copy.
- Random icon libraries for a few simple icons.
- Stock technology imagery.
