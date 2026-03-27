# contact-form

## Category
info-blocks

## Description
Contact section with split layout: contact details (address, phone, email with icons) on the left, and a form card on the right with input fields and a submit button.

## Source Components
- `component-1774565920888-252` (contact) - "Contact Details"

## Structure Tree
```
CustomSection (paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="3xl", backgroundColor="accent")
  └─ Split (distributionMode="third-two-thirds", verticalAlignment="top", gap="2xl")
       ├─ [first column: contact details]
       │    ├─ Heading (level="h2", size="lg")
       │    ├─ SimpleText (size="md")
       │    ├─ Spacer (size="lg")
       │    ├─ Heading (level="h3", size="sm")
       │    ├─ SimpleText (size="md")
       │    ├─ Spacer (size="lg")
       │    ├─ Heading (level="h3", size="sm")
       │    └─ SimpleText (size="md")
       └─ [second column: form card]
            └─ Card (rounded=true, backgroundColor="base", paddingHorizontal="lg", paddingVertical="lg")
                 ├─ Heading (level="h3", size="lg")
                 └─ Form (action="")
                      ├─ Input (label="Full Name", name="name", placeholder="Enter First Name")
                      ├─ Input (label="Phone number", name="phone", type="tel", placeholder="Enter Phone Number")
                      ├─ Input (label="Email Address", name="email", type="email", placeholder="Enter Email Address")
                      ├─ Textarea (label="Your Messages", name="message", placeholder="Enter your message")
                      └─ Submit (text="Send message", variant="primary", size="lg")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Contact Details" | Left column heading |
| contact_items | array | [{title: "Contact Details", icon: "", value: "123 Train St..."}, ...] | Contact detail entries |
| form_heading | string | "Say Hello" | Form card heading |
| form_fields | array | [{label, name, type, placeholder}, ...] | Form field definitions |
| submit_text | string | "Send message" | Submit button text |
| form_action | string | "" | Form submission URL |

## Variations
- Only one instance exists

## Extracted Styles
- Left column: Contact details with icon + bold label heading + value text pattern repeated 3 times (Address, Phone, Email)
- Each contact detail has a small icon (likely from an icon font or SVG) next to the value text
- Right column: White card with rounded corners, subtle shadow, generous padding
- Form fields: bordered inputs with labels above, gray placeholder text
- Submit button: large red button with white text, full-width or large width

## CSS Notes
- The form card has a visible shadow/elevation effect. Card component has no shadow prop, so add custom CSS: `.card-inner { box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1); }`
- The submit button appears quite large/wide. Use Button size="lg" and potentially custom CSS for full-width: `.submit .button-inner { width: 100%; }` or just let it be natural width.
- Background is light pink/accent for the overall section.
- Distribution is approximately 40/60 split, which maps to "third-two-thirds" (1fr 2fr).
- Contact detail icons are small inline icons next to text (e.g., location pin, phone, email icons).
