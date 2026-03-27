# cta-centre

## Category
ctas

## Description
Simple centered section header with a large bold heading and descriptive paragraph below. White background. Used as an introductory heading above feature sections.

## Source Components
- `component-1774565894223-470` (index) - "Sendit Features"
- `component-1774565908544-543` (features) - "Sendit Features" (identical)

## Structure Tree
```
CustomSection (paddingVertical="3xl", paddingHorizontal="xl", maxContentWidth="2xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  └─ SimpleText (size="md", alignX="center")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Sendit Features" | Centered heading text |
| description | string | "" | Descriptive paragraph text |

## Variations
- Both instances are identical (same heading, same description)

## Extracted Styles
- h2: large bold centered, "Sendit" in black and "Features" in red. Font-size approximately 48-60px (maps to size="2xl" = 3.75rem = 60px)
- p: gray text (gray-600), centered, regular weight, ~16px
- White background, moderate vertical padding (less than full section)

## CSS Notes
- The heading has "Features" colored red. Use inline markdown: `Sendit *Features*` with CSS `em { color: var(--color-brand); font-style: normal; }`.
- Padding is less than a full hero section. Use paddingVertical="3xl" (4rem) for a more compact section header feel.
- maxContentWidth="2xl" (1280px) keeps text nicely centered and readable.
