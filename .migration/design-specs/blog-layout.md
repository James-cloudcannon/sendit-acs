# blog-layout

## Category
info-blocks

## Description
Blog post card grid with 3 columns. Each card has a large image with dark overlay, a colored category tag, bold title text, and a date. Cards are clickable/linked.

## Source Components
- `component-1774565976793-874` (blog) - "Blog Showcase" - 3 blog post cards

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  └─ Grid (minItemWidth=280, maxItemWidth=400, gap="lg", layout="center")
       └─ GridItem (repeated x3)
            └─ Card (link={postUrl}, rounded=true, backgroundImage={postImage})
                 ├─ SimpleText (text={category}, size="xs")
                 ├─ Heading (level="h3", size="sm")
                 └─ SimpleText (text={date}, size="xs")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| posts | array | [{title, category, date, image, url}, ...] | Array of blog post objects |
| posts[].title | string | "" | Post title |
| posts[].category | string | "" | Category tag (e.g., "Marketing", "Blog") |
| posts[].date | string | "" | Publication date |
| posts[].image | object | {} | Post featured image (used as card background) |
| posts[].url | string | "" | Post URL (makes card clickable) |

## Variations
- Only one instance with 3 posts
- Category tags appear in red on the image

## Extracted Styles
- Cards: rounded corners, image fills the card as background
- Dark overlay on images to make text readable
- Category tag: red/primary color, small uppercase text, positioned on the image
- Title: white bold text overlaid on the dark image
- Date: small white text below title
- Cards scale up on hover (Card link behavior)

## CSS Notes
- Card with backgroundImage renders the post image behind the content. The text needs to be visible on the dark image.
- Dark overlay: Card component has no overlay prop. Custom CSS needed: `.card-inner::after { content: ''; position: absolute; inset: 0; background: rgba(0,0,0,0.4); z-index: 5; }`
- Text must be white to contrast with dark overlay. Use Card colorScheme="dark" so text variables become white.
- Category tag styling: Custom CSS for the category text to have a red/primary background badge appearance: `.simple-text:first-child .simple-text-content { background: var(--color-brand); color: white; display: inline-block; padding: 0.25em 0.75em; border-radius: var(--radius-xs); font-size: var(--font-size-xs); text-transform: uppercase; }`
- Card link makes entire card clickable with hover scale effect (built into Card component).
- The grid of 3 cards at minItemWidth=280 creates 3 columns on desktop.
