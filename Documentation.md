# Portfolio Documentation (frontend/portfolio)

This document explains the structure, components, and how the portfolio works.

## Overview

The portfolio is a simple **static frontend** page built with:

- **HTML**: layout and content (`portfolio.html`)
- **CSS**: styling and responsiveness (`portfolio.css`)
- **JavaScript**: small UI interactions (`portfolio.js`)

## Files

### 1) `portfolio.html`

Contains the complete page structure:

- **Header / Navigation**
  - Logo (with Font Awesome icon)
  - Desktop navigation links
  - Mobile hamburger menu (toggle handled by `portfolio.js`)
- **Hero Section** (`#home`)
  - Introduction text
  - Buttons to scroll to projects and to download resume
- **About Section** (`#about`)
  - Short description and a skills “pill” list
- **Projects Section** (`#projects`)
  - Project cards in a grid
- **Contact Section** (`#contact`)
  - Contact form UI (no backend submission implemented in this project)
- **Footer**
- Loads CSS (`portfolio.css`) and JavaScript (`portfolio.js`)

### 2) `portfolio.css`

Responsible for visual styling and responsiveness.
Key parts:

- **CSS variables** in `:root` for theme colors
- **Base styles** for typography and layout
- **Fixed header** with blur effect (`backdrop-filter`)
- **Grid layout** for the projects section (`.project-grid`)
- **Responsive rules** for screens below `768px`
  - Hamburger menu appears
  - `.nav-links` becomes a slide-in panel

### 3) `portfolio.js`

Contains three UI behaviors:

1. **Mobile menu toggle**
   - Toggles the `active` class on hamburger and nav links
2. **Close mobile menu on link click**
   - Removes `active` classes after selecting a section link
3. **Header shadow on scroll**
   - Adds/removes `boxShadow` depending on `window.scrollY`

## Assets

The HTML references a resume PDF:

- `frontend/portfolio/assets/Ajay_Kumar_Resume.pdf`

## Customization Guide

### Update name / title

Edit the text in `portfolio.html`:

- Header logo
- Hero heading (`Hi, I'm Ajay...`)

### Update skills

Modify the `.skills` content inside the `#about` section.

### Add or edit projects

Inside the `#projects` section, duplicate an existing `.project-card` block and update:

- Project title (`h3`)
- Tech stack text (`.tech-stack`)
- Description
- Links (Live Demo / GitHub)

### Change colors / theme

In `portfolio.css`:

- `--bg-color`
- `--text-color`
- `--accent-color`
- `--secondary-bg`

### Contact form behavior

Right now, the contact form is UI-only (no backend submission).
If you want it to send data, you’ll need to:

- Add a backend endpoint (or services like Formspree)
- Or add a `submit` handler in `portfolio.js`

## How to run

Because the project is static, you can:

- Open `portfolio.html` directly in a browser, or
- Serve the folder using any static server (VSCode Live Server, etc.)

## Notes / Improvements (Optional)

Potential improvements you can consider:

- Implement contact form submission
- Add accessibility enhancements (ARIA labels)
- Add better focus styles for inputs and buttons
- Make project links data-driven (render from JS/JSON)
