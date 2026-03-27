# feature-testimonial-card-grid

## Category
features

## Description
Testimonial section with dark (black) background, centered heading and description in white text, and a 3-column grid of white testimonial cards. Each card has a circular avatar, author name, title, and quote text.

## Source Components
- `component-1774565898723-685` (index) - "Build relationships that last"
- `component-1774565912293-314` (features) - identical

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  ├─ SimpleText (size="md", alignX="center")
  └─ Grid (minItemWidth=280, maxItemWidth=400, gap="lg", layout="center")
       └─ GridItem (repeated x3)
            └─ Testimonial (text={quote}, authorName={name}, authorDescription={title}, authorImage={avatar}, alignX="start")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Build relationships that last" | Section heading |
| description | string | "" | Subtitle text |
| color_scheme | string (select) | "dark" | Dark theme for section |
| testimonials | array | [{authorName, authorDescription, text, authorImage}, ...] | Array of 3 testimonial items |
| testimonials[].authorName | string | "" | Person's name |
| testimonials[].authorDescription | string | "" | Person's job title |
| testimonials[].text | string | "" | Quote text |
| testimonials[].authorImage | string | "" | Avatar image URL |

## Variations
- Both instances are identical in structure and styling
- Only difference is potentially different testimonial content

## Extracted Styles
- Section: black background (#000000), white text
- Heading: white, centered, with "last" in red italic (inline markdown)
- Cards: white background, rounded corners, padding, with circular 80x80 avatar photos
- Quote text in cards: regular weight, dark text on white card background
- Author name: bold
- Author description: lighter weight, smaller

## CSS Notes
- The dark color scheme (`colorScheme="dark"`) inverts the color variables so text becomes white and backgrounds become dark. The Testimonial card will use `var(--color-bg)` which in dark mode is black, but the card itself should remain white. Use Testimonial component's default styling which has `background: var(--color-bg)` -- in dark scheme this may need override.
- Actually, the Testimonial component has `background: var(--color-bg)` which in a dark theme would be dark. The cards need to be white. This requires wrapping each Testimonial in a Card with its own colorScheme="light" override, OR using custom CSS on the grid items.
- Alternative approach: Use GridItem wrapping a Card (colorScheme="light", rounded=true, border=false, paddingHorizontal="md", paddingVertical="md") containing the Testimonial.
- The heading "last" word is in red italic. Use inline markdown: `Build relationships that *last*` with CSS `em { color: var(--color-brand); }`.
- Grid of 3 cards at minItemWidth=280 creates 3 columns on desktop.

## Revised Structure Tree (handling color scheme)
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  ├─ SimpleText (size="md", alignX="center")
  └─ Grid (minItemWidth=280, maxItemWidth=400, gap="lg", layout="center")
       └─ GridItem (repeated x3)
            └─ Card (colorScheme="light", backgroundColor="base", rounded=true, paddingHorizontal="md", paddingVertical="md")
                 └─ Testimonial (text={quote}, authorName={name}, authorDescription={title}, authorImage={avatar}, alignX="start")
```
