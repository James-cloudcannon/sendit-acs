# pricing-list

## Category
info-blocks

## Description
Three pricing cards displayed side by side, each with plan name, description, price (with optional strikethrough original price), feature list with checkmarks, and a CTA button. The featured/middle card has a red top border accent.

## Source Components
- `component-1774565957530-206` (pricing) - 3 pricing cards (Free, Pro, Business)

## Structure Tree
```
CustomSection (backgroundColor="accent", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  └─ Grid (minItemWidth=280, maxItemWidth=400, gap="lg", layout="center")
       └─ GridItem (repeated x3)
            └─ Card (rounded=true, backgroundColor="base", paddingHorizontal="lg", paddingVertical="lg", border=true)
                 ├─ Heading (level="h3", size="md", alignX="center")
                 ├─ SimpleText (size="sm", alignX="center")
                 ├─ Heading (level="h2", size="2xl", alignX="center")
                 ├─ Divider (paddingVertical="sm")
                 ├─ List (items=[...features], listType="icon", size="sm", direction="vertical")
                 └─ ButtonGroup (alignX="center")
                      └─ Button (text="Try This Free", variant="primary", size="md")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| plans | array | [{name, description, price, original_price, features, button_text, button_link, featured}, ...] | Array of pricing plan objects |
| plans[].name | string | "" | Plan name (e.g., "Free", "Pro", "Business") |
| plans[].description | string | "" | Short plan description |
| plans[].price | string | "$0" | Display price |
| plans[].original_price | string | "" | Strikethrough price if discounted |
| plans[].features | array | [] | List of feature strings |
| plans[].button_text | string | "Try This Free" | CTA button text |
| plans[].button_link | string | "" | CTA button URL |
| plans[].featured | boolean | false | Whether this is the highlighted plan (red top border) |

## Variations
- 3 cards: Free ($0, no strikethrough), Pro ($125 with $199 strikethrough), Business ($350 with $499 strikethrough)
- Pro card has a red top border accent (featured=true)
- Feature lists vary in length but all use the same icon style

## Extracted Styles
- Cards: white background, rounded corners, subtle border, vertical layout
- Plan name: bold, centered, medium size
- Price: very large bold number, centered, with smaller strikethrough price next to it
- Feature list: small text with icon/checkmark items
- CTA button: red filled button, centered
- Featured card: red/primary color top border (~3-4px)

## CSS Notes
- Featured card red top border: Apply custom CSS when `featured` is true: `.card-inner { border-top: 3px solid var(--color-brand); }`
- Strikethrough price: The original price next to the current price can use inline markdown: `$ 125 ~~$199~~` or custom HTML. The `<del>` or `<s>` tag is rendered by markdown `~~text~~`.
- The price display combines a large number with a period suffix (e.g., "$125 /month"). The Counter component could be used but it animates; a simple Heading with the price text is more appropriate here.
- Background is light pink (backgroundColor="accent") for the section containing the cards.
- List items use checkmark or similar icons for features. Use List with listType="icon" and ListItem with iconName="check" or similar.
