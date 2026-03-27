# feature-stats

## Category
features

## Description
Centered section with heading, descriptive paragraph, and a row of 4 animated stat counters with labels. White background.

## Source Components
- `component-1774565891997-694` (index) - "Scale your Business" - $0m, 0, 0+, 0+
- `component-1774565929531-504` (about) - "Built for your Business" - identical layout

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  ├─ SimpleText (size="md", alignX="center")
  └─ Grid (minItemWidth=200, maxItemWidth=320, gap="lg", layout="center")
       └─ GridItem (repeated x4)
            ├─ Counter (number={value}, prefix={prefix}, suffix={suffix}, alignX="center", size="2xl")
            └─ SimpleText (text={label}, alignX="center", size="md")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Scale your Business" | Section heading, varies between index/about |
| description | string | "" | Paragraph below heading |
| stats | array | [{number: 0, prefix: "$", suffix: "m", label: "Venture capital raised"}, ...] | Array of 4 stat items |
| stats[].number | number | 0 | Target number for counter animation |
| stats[].prefix | string | "" | Text before number (e.g. "$") |
| stats[].suffix | string | "" | Text after number (e.g. "m", "+") |
| stats[].label | string | "" | Descriptive label below counter |

## Variations
- Both instances are structurally identical
- Different heading text ("Scale your Business" vs "Built for your Business")
- Same stat values (placeholder zeros in both)

## Extracted Styles
- h2: large bold centered heading, with one word in red (inline markdown: "Scale your **Business**" with CSS to color it)
- Counter numbers: very large bold text (~3.75rem), font-weight 700, centered
- Labels: regular weight, gray text, centered below counters
- Section: white background, generous vertical padding

## CSS Notes
- The heading has one word colored red (e.g., "Business" in red). This can be achieved with inline markdown bold/italic rendered with custom CSS, or by using HTML in the heading text prop (e.g., `Scale your <em>Business</em>` with `em { color: var(--color-brand); font-style: normal; }`).
- Counter component default size is "2xl" (3.75rem) which matches the large stat numbers.
- Grid with 4 items at minItemWidth=200 will create a 4-column layout on desktop and stack responsively.
