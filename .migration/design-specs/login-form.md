# login-form

## Category
info-blocks

## Description
Centered login form card with heading, input fields (name, email), remember me checkbox, forgot password link, primary submit button, "or" divider, social sign-in buttons (Google, Facebook), and a "Create an Account" link at the bottom.

## Source Components
- `component-1774565950175-896` (login) - "Log In"

## Structure Tree
```
CustomSection (paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="sm")
  └─ Card (rounded=true, backgroundColor="base", paddingHorizontal="xl", paddingVertical="xl", border=true)
       ├─ Heading (level="h1", size="2xl", alignX="center")
       ├─ Form (action="")
       │    ├─ Input (label="Full Name", name="name", placeholder="Your Name")
       │    ├─ Input (label="Email Address", name="email", type="email", placeholder="Your Email")
       │    └─ Submit (text="Log In", variant="primary", size="lg")
       ├─ Divider (paddingVertical="md")
       ├─ ButtonGroup (direction="column", alignX="center")
       │    ├─ Button (text="Sign In with Google", variant="tertiary", iconName="social/google")
       │    └─ Button (text="Sign In with Facebook", variant="tertiary", iconName="social/facebook")
       ├─ Divider (paddingVertical="sm")
       └─ SimpleText (text="[Create an Account](/signup/)", alignX="center")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Log In" | Form heading |
| form_action | string | "" | Form action URL |
| fields | array | [{label: "Full Name", name: "name", ...}, ...] | Form field definitions |
| submit_text | string | "Log In" | Submit button text |
| social_buttons | array | [{text: "Sign In with Google", icon: "social/google"}, ...] | Social login buttons |
| footer_text | string | "Create an Account" | Bottom link text |
| footer_link | string | "/signup/" | Bottom link URL |

## Variations
- Only one instance exists

## Extracted Styles
- Card: white background, subtle border/shadow, rounded corners, centered on page
- h1: large bold centered heading
- Submit button: full-width red button with white text, large padding, rounded-2xl (border-radius: 16px)
- Social buttons: outlined/bordered style, full-width, with provider icons
- "or" divider between submit and social buttons
- "Forgot Password" link aligned right (small text)
- "Remember Me" checkbox on the left (same row as Forgot Password)

## CSS Notes
- The submit button is full-width. Override: `.submit .button-inner { width: 100%; border-radius: var(--radius-lg); }`
- The "or" divider has text inside it (not just a line). This can be approximated with a Divider plus a centered SimpleText, or with custom CSS pseudo-elements on the divider.
- The "Remember Me" checkbox and "Forgot Password" link are on the same row. This is a custom layout not directly supported by form building blocks. May need custom CSS or a Split wrapper around those two elements.
- Social buttons should be full-width and stacked. Use ButtonGroup with direction="column".
- Card maxContentWidth should be constrained. Use CustomSection maxContentWidth="sm" (480px) to center the card.
- The card has a left border accent (subtle gray/light border visible on left side).
