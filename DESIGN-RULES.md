# Full Stride Newsletter — Design Rules & SOP

This document is the source of truth for designing Full Stride email templates. Follow these rules exactly when building new issues.

---

## Fonts

| Use | Font | Size | Weight | Color |
|-----|------|------|--------|-------|
| Masthead ("Full Stride") | Instrument Serif | 46px | 400 | #111111 |
| H1 (lead headline) | Instrument Serif | 38px | 500 | #0d6e6e |
| H2 (section headlines) | Instrument Serif | 30px | 500 | Matches card accent color |
| H3 (sub-headlines) | Instrument Serif | 22px | 500 | Matches card accent color |
| Pull quote / One Thing | Instrument Serif | 36px | 500 | Matches card accent color |
| The Number stat | Instrument Serif | 90px | 500 | Matches card accent color |
| Body text | Arial, Helvetica, sans-serif | 15px | 400 | #333333 |
| Subtle/secondary text | Arial, Helvetica, sans-serif | 13–14px | 300 | #333333 |
| Eyebrow labels | Arial, sans-serif | 11px | bold | Matches card accent color |
| Metadata mini-tags | Courier New, Courier, monospace | 10px | bold | #a0907a on #f0ebe4 bg |

**Google Fonts link (required in every `<head>`):**
```html
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif&display=swap" rel="stylesheet">
```
Fallback stack: `'Instrument Serif', Georgia, 'Times New Roman', serif`

---

## Colors

| Name | Hex | Use |
|------|-----|-----|
| Teal (brand primary) | #0d6e6e | H1 color, pills, links, eyebrows on white |
| Dark green (on green cards) | #2d6b5a | Eyebrows, headlines on green cards |
| Blue (on blue cards) | #4a6d8a | Eyebrows, headlines on blue cards |
| Warm brown (on beige cards) | #a0907a | Eyebrows, headlines on beige cards |
| Black | #111111 | Nav, footer, masthead, body bold |
| Body text | #333333 | All paragraph text |
| Light gray | #f5f5f5 | Disclaimer card background |
| Beige card | #f0ebe463 | Section cards (with alpha) |
| Beige meta tag | #f0ebe4 | Header metadata mini-tags only (no alpha) |
| Blue card | #e8eff5 | The Number, data-heavy sections |
| Green card | #e6f0eb | Editor intro, The One Thing, Shelf Check |

---

## Layout & Structure

### Page wrapper
- White body background: `background-color:#ffffff`
- Outer padding: `padding:16px 4px` (small gap at edges on mobile — intentional)
- Max container width: 600px

### Nav bar
- Background: #111111
- Previous/Next issue links: color #c8bfb3
- "All Issues" center link: color #777777

### Header
- Padding: `32px 16px 0`
- Left: "Full Stride" in Instrument Serif 46px weight 400 #111111
- Right: "Sponsored by" (9px, #999999, uppercase) + sponsor name (13px, 900, #0d6e6e)
- Below title: metadata mini-tags in Courier New (Issue #, Format, Read time) — background #f0ebe4, radius 3px, color #a0907a
- NO divider line after the header

---

## Cards

All colored section cards follow this structure:
- `border-radius: 8px`
- Outer cell padding: `padding: 8px 6px 0` (or `36px 6px 0` for first card after body text)
- Inner content padding: `padding: 36px 40px` (or `32px 36px` for intro cards)
- Cards go edge-to-edge within the container (only 6px gap on sides)

### Card rhythm rule
**Never stack more than 3 colored cards in a row.** Always insert a white section between groups of colored cards. This prevents a "wall of color" effect. White sections use `padding: 36px 16px`.

### Card accent colors
Each card color has a matching accent color for its eyebrow labels and headlines:
- Beige (#f0ebe463) → #a0907a
- Blue (#e8eff5) → #4a6d8a
- Green (#e6f0eb) → #2d6b5a
- White sections → #0d6e6e

---

## Section Types

### Editor Intro Card (green, always first)
Every issue opens with a green card (`#e6f0eb`) after the header containing a casual editorial note from the team. 3–4 paragraphs. Ends with `— The Full Stride Team` in italic. No eyebrow label needed.

### Category Pills
- First pill: filled, background #0d6e6e, white text — the format type (e.g. "Deep Dive", "The Fix")
- Additional pills: outlined, border #bbbbbb, text #777777 — topic tags (e.g. "Cardio", "Longevity")
- Font: Arial, 10px, normal weight, uppercase, letter-spacing 1px
- Border-radius: 20px, padding: 5px 14px

### Eyebrow Labels
- ALL CAPS, letter-spacing 2px, bold, Arial, 11px
- **Maximum 3–4 words.** If a label is longer than ~25 characters, shorten it to a category label and move the descriptive content into the headline below it.
- Examples of good eyebrows: "THE NUMBER", "THE ACTION", "ON OUR RADAR", "THE ONE THING", "SHELF CHECK", "THE MECHANISM"
- Bad example: "THE MECHANISM — AND THIS IS WHERE THE FEELINGS PROBLEM STORY FALLS APART" → shorten to "THE MECHANISM"

### Headlines
- H1: Only one per issue. Instrument Serif 38px, weight 500, #0d6e6e
- H2: Instrument Serif 30px, weight 500, card accent color
- H3: Instrument Serif 22px, weight 500, card accent color
- **Never split a headline with an eyebrow.** If the eyebrow says "WHAT EVERYONE GETS WRONG ABOUT" and the headline says "Loneliness," combine them: "What Everyone Gets Wrong About Loneliness" as a single H1.

### Pull Quotes
Use sparingly — maximum 1–2 per issue — to highlight the most memorable editorial moment in a section. Instrument Serif, 26px, weight 500, card accent color or #0d6e6e. Works well after a data-heavy paragraph or as a lead-in to the "so what" takeaway.

### The Number
- Eyebrow: "THE NUMBER", card accent color
- Stat: Instrument Serif 90px, weight 500, card accent color, letter-spacing -2px
- Body: Arial 15px, #333333, explaining the stat in 2–4 sentences
- Use blue card (#e8eff5)

### The One Thing
- Always a green card (#e6f0eb) with a hero image at the top (padding 16px around image, border-radius 6px)
- Eyebrow: "THE ONE THING", color #2d6b5a
- Subtext: "If you do nothing else this week..." — Arial 15px, weight 300, #333333
- Main text: Instrument Serif 36px, weight 500, #2d6b5a
- This is the pull quote treatment at its largest — it should be punchy and actionable

### Border rule — no single-side borders on rounded containers
If an element has `border-radius`, it must NOT have a single-side border (e.g. `border-left`). Choose one:
- **Rounded container with background color** → no border at all
- **Left-border accent** → no `border-radius` on that element (flat/square element only)

This applies to all cards, tease boxes, callout containers, and any block-level element with `border-radius`.

### Verdict / Rating
Never use badge-style elements (colored boxes with borders). Instead use the left-border blockquote treatment:
```html
<table role="presentation" width="100%">
  <tr>
    <td style="border-left:3px solid [ACCENT_COLOR];padding:12px 0 12px 16px;">
      <span style="font-family:'Instrument Serif',Georgia,serif;font-size:22px;color:[ACCENT_COLOR];">[Verdict text here]</span>
    </td>
  </tr>
</table>
```

### Sponsored Sections
**Always in a card** — beige (#f0ebe463) preferred. Never in a plain white section. Structure:
- Eyebrow: "SPONSORED" (color #a0907a)
- Headline: H2 in Instrument Serif (not H3)
- Body copy
- CTA button (outlined, black border, black text, no fill)
- "Thank you for supporting our sponsors" line in light gray below the button

### On Our Radar
List of 2–4 recommended products/tools. White section (no card) or beige card. Items separated by `border-bottom: 1px solid #e0e0e0`. Links use the brand link style: `color:#111111; font-weight:bold; border-bottom:2px solid #0d6e6e; text-decoration:none`.

### Disclaimer ("Please Don't Sue Us")
- Always the last section before the footer
- Light gray card: `background-color:#f5f5f5; border-radius:8px`
- Eyebrow: "PLEASE DON'T SUE US" — color #333333
- Body text: Arial, 14px, weight 300, color #333333
- Keep it casual and human — not legal boilerplate

### Footer
- Always a dark rounded card: `background-color:#111111; border-radius:8px`
- Outer padding: `8px 6px 6px`
- Inner padding: `32px 40px`
- Text: centered, #777777 for secondary, #333333 for address
- Links: color #c8bfb3 (warm cream)

---

## Links

All inline body links:
```css
color: #111111;
font-weight: bold;
text-decoration: none;
border-bottom: 2px solid #0d6e6e;
padding-bottom: 1px;
```

---

## Images

- Hero image below the H1: full-width, `border-radius:3px`, `margin-bottom:24px`
- Card images (The One Thing, etc.): inner padding `16px 16px 0`, image `border-radius:6px`
- All images: `display:block; width:100%; max-width:100%`
- Use Unsplash for placeholder images: `?w=600&h=280&auto=format&fit=crop`

---

## Typography Rules

- **Never use gray text on a colored background.** If a section has a colored card, all text inside must have sufficient contrast — use #333333 or the card's accent color, never #999999 or #777777.
- **Font weight 300** for subtle/secondary text: the "If you do nothing else this week..." line, benchmark notes, italic callouts.
- **Font weight 400** for the masthead.
- **Font weight 500** for all Instrument Serif headlines, stats, and pull quotes.
- **Font weight bold/900** for eyebrow labels, sponsor name.

---

## Issue Format Types

| Format | Day | Pill Color | Typical Length |
|--------|-----|------------|----------------|
| Deep Dive | Monday | #0d6e6e (filled) | ~6 min read |
| The Fix | Wednesday | #0d6e6e (filled) | ~3 min read |
| The Take | Friday | #0d6e6e (filled) | ~4 min read |

---

## Checklist Before Deploying

- [ ] Google Fonts link in `<head>`
- [ ] No eyebrow label longer than 4 words
- [ ] No headline split from an eyebrow (combine into one)
- [ ] No more than 3 colored cards in a row
- [ ] No gray text on colored backgrounds
- [ ] Sponsored section is in a card
- [ ] Verdict uses left-border blockquote, not a badge
- [ ] Disclaimer card present before footer
- [ ] Footer is a dark rounded card
- [ ] All images have border-radius
- [ ] H2s are 30px, H3s use Instrument Serif
