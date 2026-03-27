# split-text-video-modal

## Category
features

## Description
Split layout section with text content (heading, paragraph, outline button) on the left and a video thumbnail with play button overlay on the right. White background.

## Source Components
- `component-1774565930450-943` (about) - "We love what we do"

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl")
  └─ Split (distributionMode="half", verticalAlignment="center", gap="2xl")
       ├─ [first column: content]
       │    ├─ Heading (level="h2", size="xl")
       │    ├─ SimpleText (size="md")
       │    └─ ButtonGroup (alignX="start")
       │         └─ Button (text="Follow on LinkedIn", variant="tertiary", size="md")
       └─ [second column: video]
            └─ Video (type="youtube", id={videoId}, title={videoTitle})
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "We love what we do" | Section heading |
| description | string | "" | Paragraph text |
| button_text | string | "Follow on LinkedIn" | Button label |
| button_link | string | "" | Button URL |
| video_type | string (select) | "youtube" | Video provider |
| video_id | string | "" | Video ID |
| video_title | string | "" | Accessible video title |

## Variations
- Only one instance

## Extracted Styles
- Left side: bold heading, body text, red outline/tertiary button ("Follow on LinkedIn")
- Right side: team photo with orange/red play button circle overlay
- Button is outline style (variant="tertiary"): transparent bg, border, dark text
- White background section

## CSS Notes
- Button variant="tertiary" gives the outlined button appearance matching the "Follow on LinkedIn" button.
- The video thumbnail has a circular play button overlay. The Video component (lite-youtube) provides built-in play button styling.
- If the play button needs to be red/orange to match, custom CSS: `lite-youtube .lty-playbtn { background-color: var(--color-brand); }`
- The red vertical accent bar on the left edge is the same decorative element seen in split-image-text sections.
