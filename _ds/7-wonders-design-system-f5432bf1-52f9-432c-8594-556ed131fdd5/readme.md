# 7 Wonders Design System

7 Wonders is an Emmy(R) Award-winning video marketing agency. It makes brand films, commercials, documentaries, podcasts, animation, social content and YouTube campaigns for organizations including Nasdaq, Blue Shield of California, Mercedes-Benz and Comcast. The brand reads premium, cinematic, editorial and intelligent, while staying clear and human.

## Sources given

- Figma file: "7WC - Design Assets (Copy).fig" (mounted read-only; 1 page, 6772 nodes). Component inventory per its METADATA: one **Icons** set (8 variants) plus five standalone symbols — Calendar, Color, Date/active, Date/inactive, month.
- Uploaded brand assets: Montserrat OTF family, 7WC white logo lockups, banner/Times Square photography, gradient plates, favicon exports, cover PDF, reference screenshots (all in `uploads/`).

## Components

Materialized from the Figma kit into `components/core/`:

- **Icons** — the 8-variant icon set (arrow-left, arrow-right, and siblings), single-color, paints with `currentColor`.
- **Calendar** — the calendar frame composed of Month + Date cells.
- **Color** — the color-swatch symbol used across the kit.
- **DateActive** — selected date cell.
- **DateInactive** — default date cell.
- **Month** — month header row.

From the updated Figma file (`7W Designs.fig`):

- **Glowing** — pill CTA button, 4 variants (primary/secondary × hover). Violet radial gradient #d446f1 → #9a35eb, 999px radius, Lato 700 uppercase 12px at 0.05em tracking.
- **Informative** — content tile with tag, copy and trailing action; hover variant included.
- **Social Icons** (`SocialIcons`) — 26 platforms × 2 colourways (negative / original).
- **Arrow1** — the 9×9 arrow glyph nested inside Glowing and Informative.
- **FluentArrowUp16Filled**, **StreamlineFilmSlateSolid** — the two Iconify glyphs the file places directly.

No other primitives are authored: the Figma files define only these families, so nothing was invented on top of them. Note the button gradient is a violet distinct from the brand magenta — that is the file's value and is kept verbatim.

**Lato** is referenced by the button and tile components; it loads from Google Fonts alongside Poppins.

## Foundations

- `styles.css` — the single entry point (imports only).
- `tokens/colors.css` — deep ink blacks (`--ink` #0d020d), plum (`--plum-900` #590e58), magenta (`--magenta-700` #8e2e8f, `--magenta-400` #ff1fed), lilac/blush tints, and the two brand gradients.
- `tokens/typography.css` — Montserrat is the core face (Light 300 through Black 900); Poppins and Montez appear in the file as secondary/script faces.
- `tokens/spacing.css` — spacing, radii, shadows (incl. the magenta glow), easing.
- `tokens/fonts.css` — @font-face for the six uploaded Montserrat weights.

## Assets

`assets/logo-circle-mark.png` (circle mark, primary), `assets/logo-white-full.png` (full lockup), `assets/logo-white-mark.png` (Parthenon mark), `assets/gradient-bloom.png`, `assets/fonts/`.

**Primary lockup.** The circle mark — the Parthenon glyph reversed out of a plum-to-magenta circle — set beside the `7 WONDERS` wordmark (Montserrat SemiBold 600, 0.15em tracking, white) is now the default lockup and is being used increasingly in place of the older artwork. Use it first. The full lockup and the standalone Parthenon mark remain valid as secondary options.

## Missing fonts

**Poppins** and **Montez** are used in the Figma file but no font files were uploaded. Their tokens point at the real family names and fall back until the binaries arrive.

## Still to build

Foundation specimen cards, visual/content-fundamentals and iconography write-ups, UI kits, slide templates, SKILL.md.

## CONTENT FUNDAMENTALS

**Voice.** Confident, specific, unadorned. 7 Wonders states what it did and who it did it for, then stops. Claims are always evidenced — an award, a ranking, a named client — never adjectives standing alone.

**Person.** "We" for the agency, "you"/"your brand" for the reader. Never "I". Client names are used plainly and often; they carry the proof.

**Casing.** Sentence case for body and subheads. The wordmark is set in caps with wide tracking (7 WONDERS). Eyebrows and small labels are uppercase with \~0.18em tracking. No title-case headlines.

**Sentence shape.** Short declaratives. A bolded lead phrase followed by plain continuation is the house pattern for list rows:

- "**Emmy®-winning** video partner for healthcare and technology brands"
- "**#1 ranked** video and podcast vendor in the world on Clutch"

**Headline pattern.** A light-weight setup line above a heavy, wide-tracked payoff line: "Who is" over "7 WONDERS". Occasionally two or three words are lifted into the editorial italic serif for emphasis ("Great Brands").

**Emoji.** Never. The check glyph in list rows is a drawn tick, not ✅.

**Numbers.** Written as numerals, always attached to a source (Clutch ranking, Emmy count, client name). Aspect ratios and specs are written with spaced colons in the deck: `1.43 : 1`.

## VISUAL FOUNDATIONS

**Ground.** Almost everything sits on near-black ink (#0d020d) with an off-centre plum bloom — a large soft radial from #5a1157 through #2a0729 out to ink, usually anchored top-left or behind the subject. Light surfaces exist (white, #feefff blush) but are the exception, used for print and documents.

**Color.** Ink and plum are the field; magenta is the event. Magenta appears as the image plate behind a hero subject, as a 1px glow border on the active item in a comparison, and as small emphasis text. Never more than one magenta focal point per composition. The blue (#007dfc) comes from the kit's UI chrome, not the brand voice.

**Gradients.** Two only: `--gradient-brand` (135°, ink → plum → magenta) for large fields, and `--gradient-plum` (180°) for slide grounds. Gradients are soft and photographic, never banded or multi-hue. No blue-purple SaaS gradients.

**Type.** Two faces with a clear division of labour. **Poppins** sets everything readable — Bold 700 for titles ("Video Podcast / Remote Recording", "2026 Healthcare Video Guide"), Light 300 for subheads and body, SemiBold 600 for the bold lead phrase inside a checklist row. **Montserrat** is reserved for the wordmark and for uppercase eyebrow labels, always with wide tracking (0.22em on "7 WONDERS"). A high-contrast serif italic appears sparingly for one- to three-word emphasis ("Great Brands"), always white and usually with a magenta glow behind it.

**Scale contrast.** Deliberate and extreme: a 13px uppercase eyebrow directly above a 64px display line. Mid-sizes are avoided.

**Negative space.** Generous. A slide typically runs a left text column at roughly 40% width against a full-height image plate; the text column is bottom-weighted with a large empty band above it.

**Cards and panels.** Two kinds. (1) Glass list rows: translucent plum fill (rgba magenta at 14–42%), 1px rgba(249,210,252,.22) hairline, 16px radius, 12px backdrop blur. (2) Image plates: solid magenta or the photo itself, 24px radius, no border, no drop shadow. Nothing has a coloured left border.

**Elevation.** Depth reads through glow and blur, not grey shadow. `--shadow-glow` (48px magenta bloom) marks the active/selected object; `--shadow-card` is a deep ink shadow used only where a light surface needs lifting off a light ground.

**Borders.** Hairlines only — 1px, either a light rgba on dark glass or a saturated magenta on a selected object. No 2px+ rules, no dividers between list rows (gap does the work).

**Radii.** 0 for full-bleed, 8 for small UI, 16 for glass rows, 24 for image plates, pill for tags. Never a mix of radii inside one group.

**Transparency and blur.** Used only for glass rows sitting over the plum bloom, and for the protection scrim under text laid on photography. A scrim is a bottom-up ink gradient at 0 → 70%, never a flat box.

**Imagery.** Cinematic, low-key, cool-to-magenta cast. Subjects are people, sets, equipment, awards. Photography is either full-bleed or plated inside a magenta 24px-radius panel. Cutouts on white (the banner artwork) are the light-mode counterpart. Grain is present but subtle — a film texture, not a noise overlay.

**Motion.** Slow and filmic. Fades and 20–40px upward translates on `--ease-cine` (cubic-bezier(.22,.61,.36,1)) at 280–640ms. No bounce, no spring, no scale-in pops. Sequential reveals stagger 80–120ms.

**Hover.** Lighten rather than darken — text goes white, borders go from plum to magenta, glass fill gains \~8% opacity. Image plates lift opacity on an overlaid scrim. **Press:** a 1–2% scale-down and a brief drop to the deeper plum; no colour inversion.

**Layout rules.** Full-bleed background, content on a wide margin (roughly 6–8% of width). Logos sit top-left or centred above a title; the Parthenon mark is used alone when the lockup would be too heavy. Client logo rows are circular pills at a consistent diameter, spaced evenly, always at the bottom of a block.

## ICONOGRAPHY

The kit ships one icon family, materialized as `components/core/Icons.jsx` — eight glyphs: check-bold, dots-vertical, close, arrow-down, arrow-up, arrow-left, arrow-right, download. They are single-path, filled (not stroked), and paint with `currentColor`, so they inherit the surrounding text colour — white on ink, lilac inside glass rows, magenta when active.

There is no icon font and no sprite sheet. Nothing is licensed from Lucide, Heroicons or similar; do **not** add a CDN icon set to fill gaps — if a needed glyph is missing, ask for it rather than mixing stroke styles into a filled set.

Emoji are never used. Unicode is used only where it is typographically correct: ® after Emmy, × for dimensions, · as a separator, and the spaced colon in ratios.

Brand marks in the system are raster PNGs, not SVG: `assets/logo-circle-mark.png` (circle mark — the primary), `assets/logo-white-full.png` (full lockup) and `assets/logo-white-mark.png` (Parthenon mark). Reference these files directly at whatever size is needed; never redraw them.

## Index

- `styles.css` — global entry (imports only)
- `tokens/` — `fonts.css`, `colors.css`, `typography.css`, `spacing.css`
- `components/core/` — Icons, Calendar, Color, DateActive, DateInactive, Month (+ card HTML)
- `guidelines/` — 18 foundation specimen cards (Colors, Type, Spacing, Brand)
- `assets/` — logos, fonts, brand photography, gradient plate, favicon
- `thumbnail.html` — project tile
- `SKILL.md` — portable skill wrapper

## THE BRAND PDF (source of truth)

`uploads/brand-cover.pdf` — the "Answer Engine Multiplier" cover document — is the reference the client named as representing the brand exactly. Everything below is read off it and the deck pages in `uploads/`.

**Page architecture.** A thin lilac hairline runs across the top and terminates in the right-aligned `7 WONDERS` wordmark. Title and subhead sit centred beneath. Content below is a two-column grid of glass panels with generous gutters. The Parthenon mark sits bottom-right at \~12% opacity as a quiet signature.

**Bloom plates.** The PDF ships soft radial glow bitmaps rather than CSS gradients: `assets/glow-plum.png` and `assets/glow-magenta.png`. Screen-blend them over ink for the background field; this is what gives the brand its photographic, non-banded depth. CSS radials are the fallback.

**Checklist rows.** A single glass panel containing rows separated by 1px rgba(249,210,252,.10) hairlines — not separate cards. Each row: a lilac tick at \~80% opacity, then Poppins Light copy with the operative phrase in SemiBold.

**Section headers inside panels.** Uppercase, Bold, centred, white — "HOW IT WORKS:", "OUTCOME:" — with the trailing colon. This is the one place caps headings are used.

**Pull quotes.** Light lilac at 19px, curly quotes, attribution on its own line as `— Client Name` in SemiBold white. No oversized quotation-mark ornament.

**Resource labels.** Bonus/asset blocks end with a bare format label — "Google Doc", "Video", "PDF" — set small and quiet, no icon, no button chrome.

**Link affordance.** Inline actions are written as an arrow plus label: `→ Watch Overview`. No pill buttons on documents.

**Footer credit.** "Built by 7 Wonders" followed by "An Emmy® Award-winning agency trusted by leading SaaS and technology brands." — the standard closing block.

### Additional cards from this source

`guidelines/brand-wordmark.html`, `brand-bloom.html`, `brand-checklist.html`, `brand-quote.html`, `brand-watermark.html`, `type-heading-poppins.html`.

### Assets added

`assets/glow-plum.png`, `assets/glow-magenta.png`, `assets/cover-4x5.png` (the 4:5 cover reference).
