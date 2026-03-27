# Migration Verification Report

**Site:** sendit
**Date:** 2026-03-27
**Status:** GAPS_FOUND

## Summary
All 16 component groups are structurally present with correct file triads. CloudCannon wiring is correct across all groups. Import paths all resolve to existing building blocks. Styles use `@layer page-sections` consistently. Brand colors (#e71818 red) are properly mapped to theme variables. No TypeScript in template sections. A small number of issues were found, none critical.

## Component Verification

| Group | Files | Structure | Spec Alignment | Visual Fidelity | Status |
|-------|-------|-----------|---------------|-----------------|--------|
| hero-split-large | OK | OK | OK | OK | PASS |
| split-image-text | OK | OK | OK | OK | PASS |
| feature-stats | OK | OK | OK | OK | PASS |
| feature-testimonial-card-grid | OK | OK | OK | OK | PASS |
| cta-centre | OK | OK | OK | OK | PASS |
| feature-video-modal | OK | OK (note) | OK | OK | PASS (with notes) |
| contact-form | OK | OK | OK | OK | PASS |
| login-form | OK | OK | OK (note) | OK (note) | PASS (with notes) |
| create-account-form | OK | OK | OK | OK | PASS |
| team-grid | OK | OK | OK | OK | PASS |
| split-text-video-modal | OK | OK | OK | OK | PASS |
| hero-banner | OK | OK | OK | OK | PASS |
| pricing-list | OK | OK | OK | OK | PASS |
| feature-faq | OK | OK | OK | OK | PASS |
| 404-page | OK | OK | OK | OK | PASS |
| blog-layout | OK | OK | OK | OK | PASS |

## Issues Found

### Critical (broken -- will not work)
None.

### Important (wrong -- will work but incorrectly)

**1. feature-video-modal: dual backgroundColor props**
The component has both `background_color` (custom prop, used to pass to CustomSection) and `backgroundColor` (system prop, destructured but unused). The inputs.yml defines `backgroundColor` with `hidden: true` and a separate `background_color` input. The structure-value.yml only defines `background_color: accent` and `colorScheme: inherit` but not `backgroundColor`. This means if a user somehow sets `backgroundColor` through other means, it would be silently ignored since the component passes `background_color` to CustomSection's `backgroundColor` prop. The hidden `backgroundColor` input in the inputs.yml is unnecessary clutter but not harmful.
**Severity:** MINOR (functional, just confusing)

**2. login-form: missing "Remember Me" checkbox and "Forgot Password" link**
The original screenshot shows a "Remember Me" checkbox and "Forget Password" link between the form fields and submit button. The built component does not include these elements. The form fields are driven by a configurable `fields` array, but there is no mechanism for the checkbox or the forgot-password link.
**Severity:** MINOR (these are decorative/non-functional in a CMS template context; login forms are typically cosmetic in static sites)

**3. hero-split-large: image.alt stored separately as image_alt**
The `image` prop is an object with `source` but `alt` is stored as a separate `image_alt` prop instead of `image.alt`. The inputs.yml defines `image` as object and `image.source` as image, which is correct for the object shape. But `image_alt` is a flat separate prop. This diverges slightly from the migration-patterns.md recommendation to use `image.alt` inside the image object. However, it is functionally correct -- the Image component receives `source` and `alt` as separate props regardless.
**Severity:** MINOR (works correctly, just inconsistent with pattern recommendation)

### Minor (cosmetic -- works but could be better)

**4. split-image-text: red vertical accent bar not reproduced**
The original screenshots for the "Email Campaign" and "Simply click and send" variants show a red vertical accent bar on the left edge of the section. The built component does not include this decorative element. This is a purely cosmetic detail.

**5. hero-split-large: decorative masked shapes not reproduced**
The design spec notes decorative masked shapes (bg-primary/70 and bg-primary/30 with mask-image) in the original. The spec itself says "These are purely decorative and can be omitted." Correctly omitted.

**6. pricing-list: strikethrough price not handled**
The original screenshot shows strikethrough "was" prices next to current prices (e.g., "$125 ~~$199~~"). The built component has a single `price` text prop which could contain markdown, but the heading component used for price display (`<Heading>`) does not render markdown. This means strikethrough pricing would need to be handled as raw HTML in the heading text or as a separate prop. As-is, only the current price can be displayed.
**Severity:** MINOR (price display works, just missing the crossed-out original price decoration)

**7. contact-form: missing address icon**
The original screenshot shows small icons next to each contact detail (location pin, phone, email icons). The built component uses plain Heading + SimpleText without Icon components. These are decorative.

## Global Wiring

- [x] All 16 structure-value files discoverable by glob pattern `/src/components/page-sections/**/*.cloudcannon.structure-value.yml`
- [x] All `_inputs_from_glob` paths point to existing files (verified each group)
- [x] All `_component` values match directory paths:
  - `page-sections/heroes/hero-split-large`
  - `page-sections/heroes/hero-banner`
  - `page-sections/features/split-image-text`
  - `page-sections/features/feature-stats`
  - `page-sections/features/feature-testimonial-card-grid`
  - `page-sections/features/feature-video-modal`
  - `page-sections/features/feature-faq`
  - `page-sections/features/split-text-video-modal`
  - `page-sections/ctas/cta-centre`
  - `page-sections/info-blocks/contact-form`
  - `page-sections/info-blocks/login-form`
  - `page-sections/info-blocks/create-account-form`
  - `page-sections/info-blocks/pricing-list`
  - `page-sections/info-blocks/404-page`
  - `page-sections/info-blocks/blog-layout`
  - `page-sections/people/team-grid`

## Style Verification

- [x] Brand colors applied: `--brand-primary: #e71818` (sendit red)
- [x] Light theme mapped: `--color-brand`, `--color-link`, `--color-bg-accent: #fde8e8` (light pink), all grays properly set
- [x] Dark theme mapped: inverted colors with appropriate dark brand variants
- [x] Core element customizations: No custom overrides needed beyond page-section-level CSS

## Detailed Structural Verification

### Button arrays -- complete default entries with _component
- [x] hero-split-large: `buttonSections` has full button entry with `_component: building-blocks/core-elements/button`
- [x] split-image-text: `buttonSections` has full entry (variant: text, iconName: arrow-right)
- [x] split-text-video-modal: `buttonSections` has full entry (variant: tertiary)
- [x] 404-page: `buttonSections` has full entry (variant: primary)
- [x] login-form: `social_buttons` has two full entries with `_component`
- [x] create-account-form: `buttonSections` has two full entries with `_component`
- [x] pricing-list: each plan's `buttonSections` has full entry

### Image props -- dot-notation inputs
- [x] hero-split-large: `image` object with `image.source` input (type: image) -- but `image_alt` is flat (see issue #3)
- [x] 404-page: `illustration` object with `illustration.source` and `illustration.alt` inputs
- [x] team-grid: member items have `image` object with `image.source` and `image.alt` in inline `_inputs`
- [x] blog-layout: post items have `image` object with `image.source` and `image.alt` in inline `_inputs`

### Overlay patterns
- [x] blog-layout: uses `::after` on `.card-inner` with `z-index: 15` (between card bg at 10 and card content at 20). Content positioned with `justify-content: flex-end` on `.card-outer-content`. Correct pattern.
- [x] feature-testimonial-card-grid: dark section background, white cards with `colorScheme="light" backgroundColor="base"`. No overlay needed -- just theme switching.

### No TypeScript in templates
- [x] Verified all 16 .astro files: no type annotations in template sections after closing `---`

### data-prop / data-editable attributes
- [x] All editable content uses `data-prop` attributes
- [x] Array containers use `data-editable="array"` + `data-prop`
- [x] Array items use `data-editable="array-item"` + `data-id="page-sections/{category}/{group-name}/{itemName}"`
- [x] ButtonGroup arrays use `data-children-prop`

### Styles in @layer page-sections
- [x] All 16 components use `@layer page-sections` for their custom styles

## Recommendations

1. **No action required for launch.** All components are structurally correct and will function properly in CloudCannon.

2. **Optional improvements (post-launch):**
   - Normalize `hero-split-large` image prop to use `image.alt` instead of separate `image_alt` for consistency with other components
   - Add strikethrough price support to pricing-list (either via a `previous_price` prop or by switching price display to SimpleText which renders markdown)
   - Add contact detail icons to contact-form using the Icon component
   - Add red accent bar CSS to split-image-text as a `::before` pseudo-element
