# Stock Agent Pages Design System

## 0. Research Log

- Embedded refs: shortlisted Vercel, Linear, and Wise; selected `minimalist-skill.md` + `vercel.md` because this public research-project page needs developer credibility, restrained financial context, and fast comprehension.
- Lazyweb: attempted two desktop searches for fintech analytics and developer-project landing pages; zero screens viewed because the endpoint required a paid Pro account.
- Imagen drafts: generated two desktop concepts; selected the split hero plus chart-preview direction in `../design-evidence/selected-concept.png` as the local reference contract. The bitmap is reference-only and is not shipped.
- Distinctive direction: a precise research memo paired with a lightweight market-terminal preview. The signature is a shadow-ring chart surface that makes the project concrete without presenting invented live market data.

## 1. Atmosphere & Identity

Quiet, credible, and technically literate. The page should feel like a concise project brief prepared for a licensing reviewer: factual copy, generous whitespace, and a single interface preview that demonstrates intended charting context. It must never imply that Korea University officially sponsors the project or that the illustrative chart is live data.

## 2. Color

| Role | Token | Value | Usage |
|---|---|---|---|
| Canvas | `--surface-canvas` | `#ffffff` | Page background |
| Soft surface | `--surface-soft` | `#fafafa` | Chart chrome and subtle rows |
| Strong text | `--text-strong` | `#171717` | Headings and key labels |
| Body text | `--text-body` | `#4d4d4d` | Paragraphs |
| Muted text | `--text-muted` | `#666666` | Metadata |
| Rule | `--rule` | `#ebebeb` | Dividers and grid lines |
| Focus/link | `--accent` | `#0068d7` | Links and focus states only |
| Focus halo | `--focus-halo` | `rgba(0, 104, 215, 0.22)` | Keyboard focus |
| Ring | `--ring` | `rgba(0, 0, 0, 0.08)` | Shadow-as-border |
| Soft shadow | `--shadow-soft` | `rgba(0, 0, 0, 0.04)` | Quiet depth |

Accent is functional, never decorative. No gradients or large colored sections.

## 3. Typography

| Level | Size | Weight | Line height | Tracking | Usage |
|---|---|---|---|---|---|
| Display | `clamp(3rem, 7vw, 5.5rem)` | 600 | 0.96 | `-0.06em` | Project name |
| H2 | `1.125rem` | 600 | 1.3 | `-0.02em` | Capability titles |
| Lead | `clamp(1.5rem, 3vw, 2.25rem)` | 500 | 1.18 | `-0.035em` | Project summary |
| Body | `1rem` | 400 | 1.65 | normal | Main copy |
| Small | `0.875rem` | 400 | 1.5 | normal | Supporting copy |
| Caption | `0.75rem` | 500 | 1.4 | `0.04em` | Metadata and badges |

- Primary: Arial, Helvetica Neue, system sans-serif.
- Mono: SFMono-Regular, Consolas, Liberation Mono, monospace.
- Maximum two families. No remote font request.

## 4. Spacing & Layout

- Base unit: 4px.
- Tokens: `--space-1` 4px, `--space-2` 8px, `--space-3` 12px, `--space-4` 16px, `--space-6` 24px, `--space-8` 32px, `--space-12` 48px, `--space-16` 64px, `--space-20` 80px.
- Maximum content width: 1280px.
- Desktop: split hero, 44% copy and 56% preview.
- Tablet and mobile: one column, copy before preview.
- Breakpoints: 768px and 1024px. Content remains usable at 200% zoom.

## 5. Components

### Action link
- Structure: semantic `<a>` with text and compact inline SVG arrow.
- Variants: primary dark, secondary ring.
- States: default, hover, active, focus-visible. No disabled or loading state because all actions are static links.
- Accessibility: descriptive visible label, at least 44px target height, external GitHub link identifies new-tab behavior in its accessible label.
- Motion: transform and opacity only; disabled under reduced motion.

### Capability row
- Structure: icon tile, heading, and one-sentence description.
- Variants: analysis, charting, workflows.
- States: static content only. No decorative hover motion.
- Accessibility: inline SVG is hidden from assistive technology; heading carries meaning.

### Chart preview
- Structure: semantic figure, compact toolbar, inline SVG chart, and explanatory caption.
- Variants: one illustrative state only.
- States: static. It must be labeled as an interface preview and not live data.
- Accessibility: figure has a text caption; SVG has a concise accessible label.

### Status badge
- Structure: small text badge with a blue dot.
- States: static. Not clickable.
- Accessibility: readable text communicates status without color alone.

## 6. Motion & Interaction

- Link hover/focus transitions: 150ms ease-out, transform/opacity only.
- No entrance, scroll, ambient, or decorative animation. Motion would not add information on this verification-focused page.
- `prefers-reduced-motion: reduce` removes transitions.

## 7. Depth & Surface

Mixed but restrained: shadow-as-border plus one soft elevation layer.

- Ring: `0 0 0 1px var(--ring)`.
- Card: ring plus `0 2px 2px var(--shadow-soft)` and `0 16px 32px -24px var(--ring)`.
- Radius: 6px for actions, 8px for tiles, 12px for the chart preview.

## 8. Accessibility Constraints & Accepted Debt

### Constraints

- WCAG 2.2 AA target with 4.5:1 body-text contrast.
- Full keyboard reachability and visible focus on every link.
- No autoplay, flashing, or motion-only meaning.
- Semantic landmarks, one H1, descriptive links, and a skip link.
- Responsive at 375px, 768px, and 1280px; remains usable at 200% zoom.

### Accepted Debt

| Item | Location | Why accepted | Owner / Exit |
|---|---|---|---|
| Preview is illustrative, not interactive | `index.html` chart figure | The public page exists to document the intended project before the charting license is granted. The caption discloses this clearly. | Replace with the licensed implementation only after approval and within license terms. |
