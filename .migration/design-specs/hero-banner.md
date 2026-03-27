# hero-banner

## Category
heroes

## Description
Simple centered banner with a large bold heading and subtitle text on a light pink background. Used as a page header/intro section.

## Source Components
- `component-1774565920012-999` (contact) - "Let's talk."
- `component-1774565955831-893` (pricing) - "A plan for everyone"

## Structure Tree
```
CustomSection (backgroundColor="accent", paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="2xl")
  ├─ Heading (level="h1", size="3xl", alignX="center")
  └─ SimpleText (size="lg", alignX="center")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "" | Bold centered heading text |
| description | string | "" | Subtitle/description text |
| background_color | string (select) | "accent" | Light pink background |

## Variations
- **Contact page**: "Let's talk." heading with "Have a question or suggestion?" subtitle
- **Pricing page**: "A plan for everyone" heading with "Sendit is easy to get started..." subtitle
- Both use identical structure and styling

## Extracted Styles
- h1: very large bold text (~48-72px), black, centered
- p: gray text (~16-18px), centered, lighter weight
- Background: light pink (#fde8e8 / bg-primary/5)
- Generous vertical padding (both top and bottom)

## CSS Notes
- backgroundColor="accent" maps to --color-bg-accent which should be configured to the light pink (#fde8e8) in the theme.
- paddingVertical="5xl" (6rem) gives generous vertical spacing for the banner feel.
- maxContentWidth="2xl" (1280px) keeps text centered and prevents overly wide lines.
- No buttons, no images -- purely text content.
