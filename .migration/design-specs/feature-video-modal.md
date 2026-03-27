# feature-video-modal

## Category
features

## Description
Centered video thumbnail with a red play button overlay. The image shows a team photo with a warm pink overlay tint. Clicking the play button triggers video playback. Light pink background.

## Source Components
- `component-1774565893096-938` (index) - "Video Player"

## Structure Tree
```
CustomSection (backgroundColor="accent", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  └─ Video (type="youtube", id={videoId}, title={videoTitle})
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| video_type | string (select) | "youtube" | Video provider type |
| video_id | string | "" | YouTube/Vimeo video ID |
| video_title | string | "Video" | Accessible title for video |
| background_color | string (select) | "accent" | Light pink section background |

## Variations
- Only one instance exists

## Extracted Styles
- Image/video has rounded corners (rounded-md)
- Light pink background (bg-primary/5 = rgba(231,24,24,0.05))
- The play button is a red circle with white play icon, centered on the image
- The image has a warm pink/salmon overlay tint

## CSS Notes
- The Video component (lite-youtube/lite-vimeo) provides its own play button styling. The red circular play button from the original design may differ from the lite-youtube default. Custom CSS can override: `lite-youtube::part(playButton) { background-color: var(--color-brand); border-radius: 9999px; }` (if lite-youtube supports ::part).
- The warm overlay tint on the photo may need a custom CSS overlay. Since Image component has no overlay prop, this effect would require wrapping the video in a container with a pseudo-element.
- If the original is actually a clickable image that opens a modal video, then the Video component with YouTube lite-element is the closest match (lazy loads with poster image).
- Section background: backgroundColor="accent" maps to the pink/salmon tinted background.
