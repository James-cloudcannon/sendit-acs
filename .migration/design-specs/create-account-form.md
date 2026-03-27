# create-account-form

## Category
info-blocks

## Description
Centered signup form card with heading, input fields (name, email, password, confirm password), terms checkbox, primary submit button, "or" divider, social sign-in buttons, and "Log In" link at bottom.

## Source Components
- `component-1774565966398-585` (signup) - "Create Account"

## Structure Tree
```
CustomSection (paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="sm")
  └─ Card (rounded=true, backgroundColor="base", paddingHorizontal="xl", paddingVertical="xl", border=true)
       ├─ Heading (level="h1", size="2xl", alignX="center")
       ├─ Form (action="")
       │    ├─ Input (label="Full Name", name="name", placeholder="Your Name")
       │    ├─ Input (label="Email Address", name="email", type="email", placeholder="Your Email")
       │    ├─ Input (label="Password", name="password", type="password")
       │    ├─ Input (label="Retype Password", name="password_confirm", type="password")
       │    └─ Submit (text="Create an Account", variant="primary", size="lg")
       ├─ Divider (paddingVertical="md")
       ├─ ButtonGroup (direction="column", alignX="center")
       │    ├─ Button (text="Sign In with Google", variant="tertiary", iconName="social/google")
       │    └─ Button (text="Sign In with Facebook", variant="tertiary", iconName="social/facebook")
       ├─ Divider (paddingVertical="sm")
       └─ SimpleText (text="[Log In](/login/)", alignX="center")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Create Account" | Form heading |
| form_action | string | "" | Form action URL |
| fields | array | [{label, name, type, placeholder}, ...] | Form field definitions |
| submit_text | string | "Create an Account" | Submit button text |
| social_buttons | array | [{text, icon}, ...] | Social signup buttons |
| footer_text | string | "Log In" | Bottom link text |
| footer_link | string | "/login/" | Bottom link URL |
| terms_text | string | "By registering, you accept our Conditions..." | Terms checkbox text |

## Variations
- Only one instance. Very similar to login-form but with more fields and terms checkbox.

## Extracted Styles
- Identical card styling to login-form: white card, rounded corners, border, centered
- Password fields have eye/toggle icons for show/hide (not directly supported by Input component)
- Terms checkbox is inline with text (not a standard form field layout)
- Submit button: full-width, red, rounded-2xl

## CSS Notes
- Same card styling patterns as login-form (see that spec for details).
- Password field eye toggle is not supported by the Input building block. The type="password" field renders natively. Custom JS would be needed for show/hide toggle.
- Terms checkbox: Use a ChoiceGroup with multiple=true and a single option, or custom HTML. The checkbox text includes links ("Conditions", "Use Policy", "Privacy Notice").
- Submit button full-width override same as login-form.
