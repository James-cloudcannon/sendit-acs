# split-image-text

## Category
features

## Description
Two-column split section with text content (h2, paragraph, text link with arrow) on one side and a UI mockup image on the other. Alternates left/right positioning across instances.

## Source Components
- `component-1774565895126-119` (index) - "Email Campaign in one minute" - content left, image right
- `component-1774565896294-340` (index) - "See every Lead in one Place" - image left, content right
- `component-1774565897322-80` (index) - "100% free uploads" - content left, image right
- `component-1774565909520-771` (features) - "Simply click and send" - content left, image right
- `component-1774565910518-78` (features) - "See every lead in one place" - image left, content right
- `component-1774565911359-77` (features) - "Free templates to get you started" - content left, image right

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  └─ Split (distributionMode="half", verticalAlignment="center", reverse={reversed}, gap="xl")
       ├─ [first column: content]
       │    ├─ Heading (level="h2", size="2xl")
       │    ├─ SimpleText (size="md")
       │    └─ Button (variant="text", size="lg", iconName="arrow-right", iconPosition="after")
       └─ [second column: image]
            └─ Image (rounded=true)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "" | h2 heading text, differs per instance |
| description | string | "" | Paragraph text below heading |
| button_text | string | "Try This Free" | Text link label, consistent across all instances |
| button_link | string | "/signup" | Link URL |
| image | object | {} | UI mockup image |
| image_alt | string | "" | Image alt text |
| reversed | boolean | false | When true, image appears on left and content on right. Components 2 and 5 are reversed. |

## Variations
- **Content left / image right** (default): 4 of 6 instances
- **Image left / content right** (reversed=true): 2 of 6 instances
- All instances use "Try This Free" as the link text with an arrow icon
- All have white backgrounds
- The left-content variants have a red vertical accent bar on the left edge (decorative)

## Extracted Styles
- h2: font-size ~48px (text-3xl to text-6xl responsive; maps to Heading size="2xl" = 3.75rem = 60px at desktop), font-weight 700, color black
- p (description): font-size 16px, color gray-600
- a (text link): font-size 18px, font-weight 800, color rgb(231,24,24) (primary red), border: 0, bg transparent, letter-spacing 0.9px
- The arrow icon is an inline SVG (w-5 h-5), translates right on hover
- Section padding: py-16 sm:py-20 (64px / 80px)
- Inner max-width: max-w-7xl (1280px)
- Image has a decorative masked red shape behind it (bg-primary/40 with mask-image)

## CSS Notes
- Button variant="text" gives the right base styling (transparent bg, primary color, no padding). The arrow icon should use iconName="arrow-right" with iconPosition="after".
- The red vertical accent bar on the left edge of content-left variants is a decorative element. Can be added with a pseudo-element: `border-left: 4px solid var(--color-brand)` on the section or omitted.
- The decorative masked shapes behind the images (bg-primary/40 with mask-image) create a colored swoop effect. These are complex to reproduce and can be simplified or omitted.
- Section uses responsive padding: py-16 sm:py-20 = 4rem / 5rem, maps to CustomSection paddingVertical="4xl" (5rem).
- Gap between columns: gap-8 lg:gap-12 = 2rem / 3rem, maps to Split gap="xl" or "2xl".
