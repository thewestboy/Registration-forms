# Modern Auth

# Overview

A polished, glassmorphism-style authentication card that supports both Log In and Sign Up flows. It features real-time validation, a four-segment password strength meter, animated status icons, and a full dark mode that responds to the user's system preference. The entire component lives in a single HTML file with no external dependencies.

# Features

- **Dual-form layout** — Switch between Log In and Sign Up using a segmented pill control; the active panel fades in with a staggered reveal animation
- **Glassmorphism card** — Semi-transparent surface with a heavy backdrop blur, soft border, and layered shadows that adapt to light and dark modes
- **Automatic dark mode** — Full color palette swap via `prefers-color-scheme: dark`, covering backgrounds, surfaces, text, borders, and field states
- **Floating label inputs** — Labels shrink and slide upward when the user types or focuses, keeping the interface clean while maintaining context
- **Real-time validation** — Fields are checked on every keystroke and on blur; valid fields glow green, invalid fields glow amber, and a status icon animates in beside the input
- **Password strength meter** — A four-segment bar that fills progressively based on length, mixed case, numbers, and symbols; the helper text updates to show "Weak", "Fair", "Good", or "Strong"
- **Password visibility toggle** — Eye icon buttons on password fields switch between masked and plain text with updated ARIA labels
- **Shake feedback** — Invalid fields shake horizontally when the user attempts to submit, drawing attention without adding noise
- **Loading and success states** — The submit button morphs into a bouncing-dot spinner during "submission", then pops in a checkmark on success
- **Signup success overlay** — After a simulated delay, a full-screen overlay slides in over the form with a green animated ring and a confirmation message
- **Social login placeholders** — Styled buttons for Google and GitHub with inline SVG icons, ready for OAuth wiring
- **Ambient background orbs** — Two large, softly blurred circles drift slowly behind the card for depth (disabled when reduced motion is preferred)
- **Keyboard tab navigation** — Left and Right arrow keys move focus between the Log In and Sign Up tabs

# Validation

- **First name** — Required; trimmed on blur, must be at least 2 characters, and can only contain letters (including common accented ranges), spaces, hyphens, and apostrophes
- **Last name** — Same rules as first name
- **Email** — Required; trimmed on blur, validated with a standard pattern that checks for a local part, an @ symbol, and a domain with a TLD
- **Password** — Required; minimum 8 characters. A four-point scoring system checks for mixed case, at least one number, and at least one symbol. The form requires a score of 3 or higher to pass
- **Confirm password** — Required; must exactly match the password field, validated live as the user types
- **Login email** — Required; must pass the same email pattern used during signup
- **Login password** — Required; cannot be empty
- **Empty-field handling** — On submit, any blank required field is marked invalid with a "This field is required" message and receives a shake animation
- **Focus management** — If validation fails on submit, the first invalid field is automatically focused so the user can correct it immediately

# UI/UX Highlights

- **Subtle depth** — The card uses an inner radius slightly smaller than the outer radius, plus an inset highlight line, to create a layered, physical feel
- **Color-coded feedback without clutter** — Validation states use green and amber glow rings rather than bulky banners; helper text appears only when a field needs attention or confirmation
- **Smooth state transitions** — Field backgrounds, borders, shadows, label positions, and icon opacities all transition with custom easing curves
- **Tactile buttons** — Primary and social buttons scale down slightly on press and lift on hover, giving them a responsive, physical quality
- **Success choreography** — The signup flow stages its feedback: button spinner → button checkmark → overlay fade-in → green ring pop-in, creating a satisfying sense of completion
- **Reduced motion respect** — All animations, including the drifting background orbs, are disabled when the user prefers reduced motion

# Responsive Design

- **Centered fluid card** — The card has a max width of 440px and sits centered with comfortable body padding on all screen sizes
- **Small-screen refinement** — Below 400px, inner padding and heading sizes shrink to keep the form usable without scrolling on compact devices
- **Touch-friendly targets** — Buttons and input fields maintain adequate tap sizes across breakpoints

# Technologies

- HTML5
- CSS3 (Custom Properties, `backdrop-filter`, `color-mix()`, keyframe animations, media queries including `prefers-color-scheme` and `prefers-reduced-motion`)
- Vanilla JavaScript (strict mode, no frameworks)
- System font stack (SF Pro, Segoe UI, Helvetica, Arial)
- Inline SVG icons

# Folder Structure

```text
ModernAuth/
├── index.html
├── README.md
└── cover.png
```

# Getting Started

No build step or package manager is needed. Open `index.html` in any modern browser. The component is fully self-contained and will automatically adapt to the user's light or dark system preference.

# Browser Support

- Chrome, Firefox, Safari, and Edge (latest stable releases)
- Requires support for CSS `backdrop-filter`, `color-mix()`, and standard ES5 APIs
- Keyboard navigation and focus-visible outlines are fully supported
- Respects system-level reduced-motion preferences

# Future Improvements

- Wire the simulated `setTimeout` submission to a real authentication API
- Persist form state in `sessionStorage` so accidental refreshes don't erase user input
- Connect the Google and GitHub social buttons to actual OAuth flows
- Add a "Forgot password?" link on the Log In form
- Include a "Remember me" checkbox for session persistence
- Add password-requirement checkboxes (similar to the strength meter but more explicit) for users who prefer a checklist
- Consider adding a visible password-strength label on the Log In form if password policy enforcement is desired there too

# License

MIT
