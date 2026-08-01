# Enterprise Auth

# Overview

A split-screen authentication interface with a dramatic dark-to-light visual contrast. The left side features an animated typing headline and a reactive neon glow, while the right side hosts clean, minimal Sign In and Sign Up forms. Everything runs from a single HTML file with no build step or external dependencies beyond a font and icon library.

# Features

- **Split-panel layout** — A dark promotional left panel and a bright white right panel create strong visual separation between branding and functionality
- **Dual-form support** — Toggle between Sign In and Sign Up using a sliding pill switch or the footer link; the active form fades in with a subtle slide animation
- **Animated typing headline** — The text "Hi, Hello World" types itself out character by character on the left panel
- **Reactive neon glow** — A soft blue radial spotlight tracks the cursor across the left panel and subtly scales based on distance from the center
- **Password visibility toggles** — Eye icons on every password field let users switch between masked and plain text
- **Social login placeholders** — Decorative icons for Google, GitHub, and Apple sit below the divider as visual cues for OAuth integration
- **Live validation feedback** — Input fields gain a red border instantly when they fail validation rules, giving immediate visual feedback without cluttering the UI with text messages
- **Button ripple effect** — A material-style ripple expands from the click point on every button press

# Validation

- **Email** — Required; validated with a pragmatic pattern that checks for a local part, an @ symbol, and a domain with a TLD
- **First / Last name** — Required on Sign Up; trimmed and checked against a pattern that accepts letters (including common accented ranges), spaces, hyphens, and apostrophes, with a minimum length of 2 characters
- **Sign Up password** — Required; must be at least 8 characters and contain at least one letter and one number
- **Confirm password** — Required; must exactly match the Sign Up password, checked in real time as the user types
- **Sign In password** — Required; cannot be empty
- **Live validation** — Fields are re-validated on every keystroke and on blur, so error borders appear and disappear immediately as the user corrects their input
- **Submit blocking** — If any field is invalid when the user presses the button, submission is blocked silently and the offending fields keep their red borders
- **Internal strength scoring** — Passwords are scored weak / medium / strong on the Sign Up form, but the result is only logged to the console and not shown in the interface

# UI/UX Highlights

- **Dark-to-light contrast** — The left panel uses deep blacks and a blue gradient, while the right panel is pure white, making the form feel crisp and modern
- **Sliding toggle switch** — A white pill slides behind the Sign In / Sign Up buttons to indicate the active mode, with a gentle pulse glow on the active label
- **Input focus lift** — On focus, text fields shift up by 2 pixels and gain a blue ring, giving a tactile sense of selection
- **Consistent button styling** — The primary action button uses a blue gradient that brightens on hover and casts a soft shadow; pressing it triggers a scale-down for physical feedback
- **Silent error design** — Invalid fields are marked only by a red border and red focus ring, keeping the interface clean and free of error-message noise
- **Footer link mirroring** — The text below the social icons updates dynamically to match the active form, offering a quick way to switch modes without reaching for the toggle

# Responsive Design

- **Vertical stack under 900px** — The two-panel layout collapses into a single column that fills the entire viewport; the left panel becomes a compact header (max 26vh) and the right panel takes the remaining space and scrolls if needed
- **Fluid typography and spacing** — `clamp()` functions scale fonts, padding, and margins smoothly between mobile and desktop sizes
- **Tighter mobile layout** — Below 480px the left panel shrinks further to 20vh and the name-row gap tightens for smaller screens
- **Full-bleed mobile experience** — Border radius is removed and the container stretches to 100vw / 100dvh on narrow devices so it feels like a native app screen

# Technologies

- HTML5
- CSS3 (Flexbox, gradients, keyframe animations, media queries, CSS `clamp()`)
- Vanilla JavaScript (ES6+, strict mode implied, no frameworks)
- Google Fonts — Inter
- Font Awesome 6.5.0 (solid and brand icons)

# Folder Structure

```text
EnterpriseAute/
├── index.html
├── README.md
└── cover.png
```

# Getting Started

No build tools or package managers are needed. Simply open `index.html` in a modern browser. The file pulls in Inter from Google Fonts and Font Awesome from a CDN; everything else is self-contained.

# Browser Support

- Chrome, Firefox, Safari, and Edge (latest stable releases)
- Designed for modern browsers that support CSS `clamp()`, `dvh` units, and standard ES6 APIs

# Future Improvements

- Surface the internal password-strength score in the UI with a visual meter or checklist
- Add visible error messages for users who may not notice a red border alone
- Wire the social icons to actual OAuth providers
- Implement a "Forgot password?" flow on the Sign In form
- Add ARIA labels and focus management for screen-reader compatibility
- Replace the console-only submission with a real API call and show a loading or success state
- Cache partially filled form data in `sessionStorage` to survive accidental refreshes

# License

MIT
