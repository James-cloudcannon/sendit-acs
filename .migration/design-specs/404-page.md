# 404-page

## Category
info-blocks

## Description
404 error page with a centered illustration (hand with magnifying glass over "404"), a bold heading, and a red CTA button to try again. White background.

## Source Components
- `component-1774565941238-255` (404) - "Oops! Page not found."

## Structure Tree
```
CustomSection (paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="md")
  ├─ Image (source={illustration}, alt="404 illustration", rounded=false)
  ├─ Heading (level="h1", size="xl", alignX="center")
  └─ ButtonGroup (alignX="center")
       └─ Button (text="Try again", variant="primary", size="md", link="/")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| illustration | string | "/images/404.png" | 404 illustration image |
| heading | string | "Oops! Page not found." | Error heading text |
| button_text | string | "Try again" | CTA button text |
| button_link | string | "/" | CTA button URL (home page) |

## Variations
- Only one instance

## Extracted Styles
- Illustration: centered, medium size (~300-400px wide), hand holding magnifying glass over purple "404" text
- Heading: large bold centered text below illustration
- Button: red filled button, centered, medium size, rounded corners
- White background with generous top padding

## CSS Notes
- The illustration is a pre-made image file. The Image component renders it centered within the maxContentWidth container.
- Button variant="primary" with default styling matches the red filled button.
- Large top padding (pt-30 in original = 7.5rem). Use paddingVertical="5xl" (6rem) or "6xl" (7rem) for similar effect.
- maxContentWidth="md" (640px) keeps the 404 content compact and centered.
