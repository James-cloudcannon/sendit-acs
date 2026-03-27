# hero-split-large

## Category
heroes

## Description
Full-width hero section with split layout: text content (h1 heading, paragraph, CTA button) on the left, large image on the right. Light pink/accent background.

## Source Components
- `component-1774565890234-659` (index) - "Beautiful web campaigns" - dashboard report image
- `component-1774565907682-571` (features) - "Run the best campaigns" - dashboard donut chart image
- `component-1774565928406-94` (about) - "On a mission to change email marketing" - photo collage

## Structure Tree
```
CustomSection (backgroundColor="accent", paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="3xl")
  └─ Split (distributionMode="half", verticalAlignment="center", gap="2xl")
       ├─ [first column: content]
       │    ├─ Heading (level="h1", size="3xl")
       │    ├─ SimpleText (size="lg")
       │    └─ ButtonGroup (alignX="start")
       │         └─ Button (variant="primary", size="lg")
       └─ [second column: image]
            └─ Image (rounded=true)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Beautiful web campaigns" | h1 text from source, varies per page |
| description | string | (paragraph text) | Body text below heading |
| button_text | string | "Try This Free" | CTA button label |
| button_link | string | "/signup/" | CTA button URL |
| image | object | (dashboard image) | Right-side hero image, varies per instance |
| image_alt | string | "Reports dashboard" | Alt text for hero image |
| background_color | string (select) | "accent" | CustomSection backgroundColor; index/features use "accent" (pink), about uses "accent" too |
| color_scheme | string (select) | "inherit" | CustomSection colorScheme |

## Variations
- **Index hero**: Pink background, single dashboard screenshot on right with shadow
- **Features hero**: Pink background, single dashboard screenshot with donut chart
- **About hero**: Cream/beige background (still "accent"), photo collage on right with 3 overlapping photos at angles

The photo collage on the about page is a single composite image, so the Image component handles it the same way.

## Extracted Styles
- h1: font-size 72px (maps to Heading size="3xl" = 4.625rem ~ 74px), font-weight 700, color rgb(0,0,0), line-height 90px, margin-bottom 24px
- p (description): font-size 20px (maps to SimpleText size="lg" = 1.125rem ~ 18px, use "xl" = 1.375rem ~ 22px; best match is "lg"), color oklch(0.446 0.03 256.802) ~ gray-600
- a (CTA button): font-size 18px, font-weight 800, bg rgb(231,24,24), color white, border-radius 16px, padding 16px 32px, letter-spacing 0.9px
- img: max-height 600px, rounded-md, shadow-xl

## CSS Notes
- The CTA button uses border-radius: 16px (--radius-lg) vs the toolkit default of 4px (--radius-xs). Override with custom CSS: `.button-inner { border-radius: var(--radius-lg); }`
- Button has letter-spacing: 0.9px and font-weight: 800 (extrabold). Override: `.button-inner { letter-spacing: 0.05em; font-weight: 800; }`
- Button padding is larger than default (16px 32px vs 0.5em). Override: `.button-inner { padding: 1rem 2rem; }`
- Hero image has shadow-xl effect. Add: `.image-inner { box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1); }`
- The section has decorative masked shapes (bg-primary/70 and bg-primary/30 with mask-image). These are purely decorative and can be omitted or added as custom CSS pseudo-elements.
- The about variant has the image overflowing slightly. This is an effect of the collage layout.
