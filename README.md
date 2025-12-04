# Uptime Kuma Themes

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Bun](https://img.shields.io/badge/Bun-%23000000.svg?style=flat&logo=bun&logoColor=white)](https://bun.sh)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![Uptime Kuma](https://img.shields.io/badge/Uptime%20Kuma-5CDD8B?style=flat&logo=uptime-kuma&logoColor=white)](https://github.com/louislam/uptime-kuma)

[![Themes](https://img.shields.io/badge/Themes-21-blue?style=for-the-badge)](./themes)
[![Layouts](https://img.shields.io/badge/Layouts-5-green?style=for-the-badge)](./layouts)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](http://makeapullrequest.com)

A collection of beautiful, customizable themes and layouts for [Uptime Kuma](https://github.com/louislam/uptime-kuma) status pages.

---

## Themes

| | | | |
|---|---|---|---|
| [Gruvbox](#gruvbox) | [Catppuccin](#catppuccin) | [Nord](#nord) | [Dracula](#dracula) |
| [Solarized](#solarized) | [Tokyo Night](#tokyo-night) | [One Dark Pro](#one-dark-pro) | [Monokai](#monokai) |
| [Ayu](#ayu) | [Palenight](#palenight) | [Synthwave '84](#synthwave-84) | [Everforest](#everforest) |
| [Kanagawa](#kanagawa) | [Rosé Pine](#rosé-pine) | [Modus Vivendi](#modus-vivendi) | [GitHub Dark](#github-dark) |
| [Night Owl](#night-owl) | [Horizon](#horizon) | [One Light](#one-light) | [Moonlight](#moonlight) |
| [Lumina](#lumina) | | | |

---

### Gruvbox

Retro groove with warm browns, oranges, and muted greens.

![Gruvbox Theme](./themes/gruvbox/default.png)

[View CSS](./themes/gruvbox/index.css)

---

### Catppuccin

Soothing pastel theme (Mocha flavor).

![Catppuccin Theme](./themes/catppuccin/default.png)

[View CSS](./themes/catppuccin/index.css)

---

### Nord

Arctic, bluish-grey inspired by polar nights.

![Nord Theme](./themes/nord/default.png)

[View CSS](./themes/nord/index.css)

---

### Dracula

Dark purple with vibrant pink, cyan, and green accents.

![Dracula Theme](./themes/dracula/default.png)

[View CSS](./themes/dracula/index.css)

---

### Solarized

Precision-engineered dark color scheme.

![Solarized Theme](./themes/solarized/default.png)

[View CSS](./themes/solarized/index.css)

---

### Tokyo Night

Deep blues inspired by Tokyo city lights.

![Tokyo Night Theme](./themes/tokyo-night/default.png)

[View CSS](./themes/tokyo-night/index.css)

---

### One Dark Pro

Based on Atom's iconic One Dark theme.

![One Dark Pro Theme](./themes/one-dark-pro/default.png)

[View CSS](./themes/one-dark-pro/index.css)

---

### Monokai

The legendary Sublime Text classic.

![Monokai Theme](./themes/monokai/default.png)

[View CSS](./themes/monokai/index.css)

---

### Ayu

Minimalist with soft, refined colors.

![Ayu Theme](./themes/ayu/default.png)

[View CSS](./themes/ayu/index.css)

---

### Palenight

Material Design-inspired purples and teals.

![Palenight Theme](./themes/palenight/default.png)

[View CSS](./themes/palenight/index.css)

---

### Synthwave '84

Retro 80s neon aesthetic with glow effects.

![Synthwave '84 Theme](./themes/synthwave-84/default.png)

[View CSS](./themes/synthwave-84/index.css)

---

### Everforest

Nature-inspired green palette.

![Everforest Theme](./themes/everforest/default.png)

[View CSS](./themes/everforest/index.css)

---

### Kanagawa

Japanese-aesthetic muted tones.

![Kanagawa Theme](./themes/kanagawa/default.png)

[View CSS](./themes/kanagawa/index.css)

---

### Rosé Pine

Soft, romantic, muted tones.

![Rosé Pine Theme](./themes/rose-pine/default.png)

[View CSS](./themes/rose-pine/index.css)

---

### Modus Vivendi

WCAG AAA accessible dark theme.

![Modus Vivendi Theme](./themes/modus-vivendi/default.png)

[View CSS](./themes/modus-vivendi/index.css)

---

### GitHub Dark

Official GitHub dark colors.

![GitHub Dark Theme](./themes/github-dark/default.png)

[View CSS](./themes/github-dark/index.css)

---

### Night Owl

Optimized for night-time with accessible colors.

![Night Owl Theme](./themes/night-owl/default.png)

[View CSS](./themes/night-owl/index.css)

---

### Horizon

Warm oranges, purples, and pinks.

![Horizon Theme](./themes/horizon/default.png)

[View CSS](./themes/horizon/index.css)

---

### One Light

Clean, professional light theme.

![One Light Theme](./themes/one-light/default.png)

[View CSS](./themes/one-light/index.css)

---

### Moonlight

Deep blues with vibrant accents.

![Moonlight Theme](./themes/moonlight/default.png)

[View CSS](./themes/moonlight/index.css)

---

### Lumina

Dark cinematic theme with orange accents.

![Lumina Theme](./themes/lumina/default.png)

[View CSS](./themes/lumina/index.css)

---

## Layouts

| Layout | Description |
|--------|-------------|
| **Compact** | Dense, space-efficient for many monitors |
| **Two-Column** | Side-by-side monitor groups |
| **Three-Column** | Maximum density grid layout |
| **Cards Grid** | Individual monitors as responsive cards |
| **Minimal** | Clean, distraction-free design |

## Usage

### Applying a Theme

1. Open your Uptime Kuma dashboard
2. Go to **Settings** → **Appearance** → **Custom CSS**
3. Copy the contents of your chosen theme from `themes/<theme-name>/index.css`
4. Paste it into the Custom CSS field
5. Save

### Combining Theme + Layout

You can combine any theme with any layout by concatenating both CSS files:

```css
/* First, paste the theme CSS */
/* themes/dracula/index.css content here */

/* Then, paste the layout CSS */
/* layouts/two-column/index.css content here */
```

## Documentation

- [Development Guide](./docs/DEVELOPMENT.md) - Setting up the development environment, available scripts, mock server endpoints, and troubleshooting
- [Contributing Guide](./docs/CONTRIBUTING.md) - How to add new themes/layouts, code style guidelines, and PR requirements

## License

MIT License - feel free to use these themes in your own projects!

## Acknowledgments

- [Uptime Kuma](https://github.com/louislam/uptime-kuma) by Louis Lam
- Theme color palettes from their respective projects:
  - [Gruvbox](https://github.com/morhetz/gruvbox)
  - [Catppuccin](https://github.com/catppuccin/catppuccin)
  - [Nord](https://www.nordtheme.com)
  - [Dracula](https://draculatheme.com)
  - [And more...](#themes)
