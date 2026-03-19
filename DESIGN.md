# DESIGN.md — Christopher Iach Portfolio

## Visual Theme & Atmosphere

Midnight observatory. Ultra-dark navy backgrounds with electric cyan as the primary accent create the feeling of a deep-space monitoring station. Scattered particle effects drift across the hero, and the entire color system descends through four navy depths from near-black (#050a15) to card surface (#111d30). A secondary amber accent appears for selective emphasis on stats and badges, preventing the cold blue palette from feeling monotone. The layout favors tall, scroll-heavy sections with generous padding, letting each content block breathe against the dark canvas.

## Color Palette & Roles

| Name | Value | Role |
|------|-------|------|
| Deep Space | `#050a15` | Page background, deepest layer (`--bg-deep`) |
| Primary Dark | `#080d1a` | Section backgrounds, primary surface (`--bg-primary`) |
| Surface Navy | `#0e1628` | Elevated section backgrounds (`--bg-surface`) |
| Card Navy | `#111d30` | Card backgrounds, project tiles (`--bg-card`) |
| Card Hover | `#162240` | Card hover state, active surfaces (`--bg-card-hover`) |
| Pale Slate | `#e2e8f0` | Headlines, primary body text (`--text-primary`) |
| Cool Gray | `#8899b5` | Secondary text, descriptions, nav links (`--text-secondary`) |
| Muted Navy | `#506080` | Labels, captions, tertiary text (`--text-muted`) |
| Electric Cyan | `#00d4ff` | Primary accent — H3 titles, CTA fills, social icons, stat highlights (`--accent-cyan`) |
| Signal Blue | `#4f8fff` | Secondary accent — buttons, links, tag highlights (`--accent-blue`) |
| Warm Amber | `#ffb020` | Tertiary accent — stat emphasis, badge glow, selective warmth (`--accent-amber`) |
| Glass White 06 | `rgba(255,255,255, 0.06)` | Subtle dividers, section borders (`--border-subtle`) |
| Glass White 08 | `rgba(255,255,255, 0.08)` | Card borders, panel edges (`--border-card`) |
| Glass White 15 | `rgba(255,255,255, 0.15)` | Hover borders, active states |
| Frosted Black | `rgba(0,0,0, 0.92)` | Mobile nav overlay, modal backdrops |

**White opacity ladder:** `0.04` faint tints → `0.05` tag backgrounds → `0.06` dividers → `0.08` card borders → `0.15` hover borders → `0.92` overlay backdrops.

## Typography Rules

**Display:** Syne (sans-serif, geometric) — all headings and brand name. Weight 700–800. The wide, futuristic letterforms signal tech-forward identity without resorting to a monospace cliche. H3 titles render in Electric Cyan, breaking the white-on-dark heading pattern with color hierarchy.

**Body:** Outfit (sans-serif) — paragraphs, nav links, descriptions, tags, button text. Weight 300–400. Line-height 1.6 for comfortable reading against dark backgrounds.

**Hierarchy:**
- H1: 72px / 800 — hero name, Syne, line-height 1.1
- H2: 40px / 700 — section headers, Syne, line-height 1.2
- H3: 25.6px / 700 — card/project titles, Syne, Electric Cyan color
- Body: 16px / 400 — paragraph text, Outfit, Pale Slate
- Secondary: 14px / 400 — nav links, tag text, letter-spacing 0.28px
- Label: 14px uppercase — section eyebrows ("About", "Expertise", "Projects"), Electric Cyan, letter-spacing wide

## Component Stylings

**Project cards** — `background: #111d30`, `border: 1px solid rgba(255,255,255, 0.08)`, `border-radius: 20px`, `padding: 56px 28px`. Tech tags sit inside cards as inline text. Each card contains an H3 title (cyan), subtitle, tag list, bullet features, and a source link with arrow icon. No images in project cards — content density carries the visual weight.

**Tech tags** — inline pill elements with `background: rgba(255,255,255, 0.05)`, `border: 1px solid rgba(255,255,255, 0.08)`, `border-radius: 100px`, cyan or slate text. Small padding (4px 12px). Tags cluster below project titles.

**CTA buttons** — Signal Blue (`#4f8fff`) solid fill, white text, `border-radius: 8px`. Secondary CTAs use transparent background with cyan text and no border. Both include inline arrow SVG icons.

**Stat counters** — large numbers in Syne display font with cyan color, labels below in muted text. 4-column grid within the About section. Numbers animate from 0 on scroll intersection.

**Experience timeline** — vertical stack of role cards with `background: #111d30`, 20px radius. Each card has a header row (title + tags for company type and date range), followed by a bulleted feature list. Tags use the same pill styling as tech tags.

**Video reel grid** — horizontal scroll or wrapped grid of thumbnail cards. Each card has a video thumbnail with overlay, title below. Cards use 12px radius with subtle border.

**Nav** — fixed top, transparent background. Brand monogram "CI" left-aligned, link row right-aligned. Links in Outfit 14px, no uppercase. Active state uses cyan underline or color change. Padding 18px 40px.

**Contact cards** — grid of icon + label links with `background: rgba(255,255,255, 0.04)`, `border-radius: 14px`. Icon in cyan, label text in Cool Gray. Hover brightens the background.

## Layout Principles

Max content width 1140px (`--max-w`), centered. Sections use 80–120px vertical padding with alternating background depths (deep → surface → deep) to create visual rhythm without explicit dividers.

**Section grid patterns:**
- About: 2-column split (text left, stat grid right)
- Skills: 2-column grid (Marketing card, AI/Dev card)
- Experience: single-column stack of timeline cards
- Video Reel: horizontal scrolling grid or flex wrap
- Showcase: 2-column (embedded iframe left, description + stats right)
- Projects: 2-column grid of project cards
- Contact: 6-column icon grid with download links below

**Border radius system:** `6px` inline code → `8px` buttons → `10–12px` small cards/thumbnails → `14px` contact cards → `16–20px` project cards → `28px` large panels → `100px` pills/tags → `50%` circular avatars.

**Scroll animations:** Elements fade up from `opacity: 0; translateY(30px)` on IntersectionObserver trigger with staggered timing. Stat counters animate from 0 to target value. Hero name letters animate individually.

**Responsive:** Single-column at 768px. Nav collapses to hamburger. Project grid, skill cards, and stat counters stack vertically. Video reel becomes a single-column scroll.
