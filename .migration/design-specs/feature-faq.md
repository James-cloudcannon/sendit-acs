# feature-faq

## Category
features

## Description
FAQ section with centered heading and description, followed by an accordion of expandable question/answer items. Each item has a red numbered circle, question title, and chevron toggle. Light pink background.

## Source Components
- `component-1774565959805-740` (pricing) - "Have Questions?" - 5 FAQ items

## Structure Tree
```
CustomSection (backgroundColor="accent", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  ├─ Heading (level="h2", size="2xl", alignX="center")
  ├─ SimpleText (size="md", alignX="center")
  └─ Accordion (openFirst=true, singleOpen=true)
       └─ AccordionItem (repeated x5)
            └─ Text (text={answer})
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Have Questions?" | Section heading |
| description | string | "" | Subtitle text |
| faq_items | array | [{title, answer}, ...] | Array of FAQ question/answer pairs |
| faq_items[].title | string | "" | Question text (accordion title) |
| faq_items[].answer | string | "" | Answer text (accordion content, markdown) |
| open_first | boolean | true | Whether first FAQ item starts expanded |

## Variations
- Only one instance with 5 FAQ items
- First item is expanded by default

## Extracted Styles
- Heading: "Have" in black, "Questions?" in red, centered, large bold
- Subtitle: gray centered text
- Accordion items: white card-like background, with red numbered circle on the left, question text, and chevron on right
- Expanded item shows answer text below the question
- Light pink section background

## CSS Notes
- The heading has "Questions?" in red. Use inline markdown: `Have *Questions?*` with CSS `em { color: var(--color-brand); font-style: normal; }`.
- The red numbered circles (1, 2, 3...) next to each FAQ title are a custom decoration not supported by the AccordionItem component natively. Options:
  - Use custom CSS with `counter()` and `::before` pseudo-element on each `.accordion-item-title`
  - Or accept that the numbered circles will be omitted and rely on the chevron toggle for expand/collapse indication
- Each accordion item appears to have a white card-like background. The AccordionItem uses a border-bottom by default; to achieve card-like appearance, custom CSS: `.accordion-item { background: var(--color-bg); border-radius: var(--radius-sm); margin-bottom: var(--spacing-sm); border-bottom: none; }`
- singleOpen=true ensures only one FAQ is open at a time (uses HTML name attribute).
- backgroundColor="accent" for the pink section background.
