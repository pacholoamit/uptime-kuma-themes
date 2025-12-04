# Contributing

Contributions are welcome! Here's how to get started.

## Adding a New Theme

1. Create a new directory in `themes/` with your theme name (lowercase, hyphenated)
2. Create an `index.css` file inside with your theme styles
3. Add a `default.png` screenshot of your theme
4. Follow the existing theme structure for consistency
5. Ensure good contrast for readability (light text on dark backgrounds, etc.)
6. Test with multiple monitor states (up, down, pending, maintenance)

## Adding a New Layout

1. Create a new directory in `layouts/` with your layout name
2. Create an `index.css` file focusing only on positioning/sizing
3. Avoid color changes - layouts should work with any theme
4. Test responsiveness on mobile, tablet, and desktop

## Development Workflow

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-new-theme`
3. Start the dev environment: `bun dev`
4. Seed the database with monitors: `bun run db:seed`
5. Make your changes and test in Uptime Kuma
6. Commit your changes: `git commit -m "Add my-new-theme"`
7. Push to your fork: `git push origin feature/my-new-theme`
8. Open a Pull Request

## Code Style

- Use CSS custom properties (variables) for colors
- Include comments for major sections
- Follow the existing file structure
- Test across different browsers

## Theme Structure

Each theme should follow this structure:

```css
/* ========================================
   THEME NAME UPTIME KUMA STATUS PAGE THEME
   Brief description
   Based on: source URL
   ======================================== */

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');

:root {
  /* Color palette */
  --background: #...;
  --foreground: #...;

  /* Theme mappings */
  --primary: ...;
  --success: ...;
  --warning: ...;
  --danger: ...;
  --maintenance: ...;

  /* Background/foreground */
  --bg-base: ...;
  --bg-surface: ...;
  --bg-elevated: ...;
  --fg-primary: ...;
  --fg-secondary: ...;
  --fg-muted: ...;

  /* Borders */
  --border-subtle: ...;
  --border-default: ...;
  --border-accent: ...;

  /* Other */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --shadow-card: ...;
}

/* Base styles, header, overall status, monitor cards, etc. */
```

## Screenshot Guidelines

When adding a `default.png` screenshot:

1. Capture the status page with multiple monitors in different states
2. Use a consistent viewport width (recommended: 1280px)
3. Include the header and at least one monitor group
4. Optimize the image for web (recommended: PNG, <500KB)

## Pull Request Guidelines

- Keep PRs focused on a single theme or feature
- Include a screenshot in your PR description
- Test on both light and dark system preferences if applicable
- Ensure your theme works with all 5 layouts
