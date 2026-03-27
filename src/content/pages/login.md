---
title: Login | Sendit
pageSections:
  - _component: page-sections/info-blocks/login-form
    heading: Log In
    form_action: null
    submit_text: Log In
    footer_text: Create an Account
    footer_link: /signup
    colorScheme: inherit
    backgroundColor: base
    fields:
      - label: Full Name
        name: name
        type: text
        placeholder: Your Name
        required: false
      - label: Email Address
        name: email
        type: email
        placeholder: Your Email
        required: false
    social_buttons:
      - _component: building-blocks/core-elements/button
        text: Sign In with Google
        link: ""
        iconName: social/google
        iconPosition: before
        hideText: false
        variant: tertiary
        size: md
      - _component: building-blocks/core-elements/button
        text: Sign In with Facebook
        link: ""
        iconName: social/facebook
        iconPosition: before
        hideText: false
        variant: tertiary
        size: md
---
