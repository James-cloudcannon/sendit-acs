# team-grid

## Category
people

## Description
Team member grid section with a centered heading and a 4-column grid of team member photos with names and titles below each. Photos are square with rounded corners.

## Source Components
- `component-1774565931380-386` (about) - "Our leadership team" - 8 members in 4x2 grid

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  └─ Grid (minItemWidth=200, maxItemWidth=280, gap="lg", layout="center")
       └─ GridItem (repeated x8)
            ├─ Image (aspectRatio="square", rounded=true)
            ├─ Heading (level="h3", size="xs", alignX="center")
            └─ SimpleText (size="sm", alignX="center")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Our leadership team" | Section heading |
| members | array | [{image, image_alt, name, title}, ...] | Array of team members |
| members[].image | string | "" | Photo URL |
| members[].image_alt | string | "" | Photo alt text |
| members[].name | string | "" | Person's name |
| members[].title | string | "" | Job title/role |

## Variations
- Only one instance with 8 team members

## Extracted Styles
- Photos: square aspect ratio, rounded corners (rounded-lg or rounded-xl), no border
- Names: bold, centered, dark text
- Titles: lighter weight, gray, centered, smaller text
- Grid: 4 columns on desktop, responsive stacking
- White background
- Generous spacing between items

## CSS Notes
- Image aspectRatio="square" with rounded=true gives square photos with border-radius: 16px (--radius-lg).
- Grid with minItemWidth=200 and 8 items naturally creates 4 columns on wider screens and fewer on mobile.
- Name heading uses level="h3" for semantics but size="xs" (1.125rem) for visual size.
- SimpleText for title at size="sm" (0.875rem) keeps it small and subordinate.
