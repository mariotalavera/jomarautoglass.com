# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll 4.2.0 static website for **Jomar Auto Glass**, a car glass replacement service operating in Puerto Rico and Vieques. The site is built with the Minima theme and uses Spanish as the primary language (es-PR locale). It includes service information, an image gallery, job request forms, and contact information.

**Key details:**
- Ruby version: 2.6.2
- Primary language: Spanish (Puerto Rico)
- Hosting: Netlify (form submissions handled via Netlify)
- Analytics: Google Analytics and Google Ads conversion tracking

## Building and Running the Site

### Prerequisites
```bash
# Install Ruby dependencies
bundle install
```

### Development Server
```bash
# Start local development server (default: http://localhost:4000)
bundle exec jekyll serve

# Serve with live reload
bundle exec jekyll serve --livereload
```

### Build
```bash
# Build the static site (output to _site/)
bundle exec jekyll build

# Build for production
JEKYLL_ENV=production bundle exec jekyll build
```

## Project Structure

### Core Directories

- **`_pages/`**: Page content in Markdown. Files are prefixed with numbers to control sort order (e.g., `010_services.md`). Each page has YAML front matter defining:
  - `layout`: typically "page"
  - `title`: page title (displayed and in meta tags)
  - `permalink`: URL path for the page
  - `metadescription`: SEO description tag

- **`_layouts/`**: HTML templates
  - `default.html`: Base layout with header, footer, and includes
  - `home.html`: Homepage layout
  - `page.html`: Page template (extends default)
  - `post.html`: Blog post template

- **`_includes/`**: Reusable HTML components
  - `head.html`: `<head>` section with Tailwind Play CDN config (custom colors), Google Fonts (Oswald + Inter preconnect), Google Analytics, structured data (Schema.org), and meta tags
  - `header.html`: Sticky dark navy navigation bar + full-width hero section with background image and dark overlay. Responsive hamburger menu with Liquid loop for nav items.
  - `footer.html`: 3-column responsive grid footer with dark navy background, brand info, contact details, and social icons
  - `stylesheet.html`: Simplified stylesheet links (Font Awesome CDN + print.css). Removed deferred CSS loader.
  - `quote_or_call.html`: Modern CTA button pair (red solid primary + white outline secondary) using Oswald font
  - `service_areas.html`: Two-column CSS grid list of service areas
  - `instagram.html`: Instagram/Curator.io feed embed (8KB+ - can be optimized)

- **`_sass/`**: SCSS files for styling
  - `_base.scss`: Base styles
  - `_layout.scss`: Layout styles (7KB+ - contains responsive styling)

- **`assets/`**: Images and static files
  - `ico/`: Service/feature icons (30+ files)
  - `pictures/`: Gallery images (30+ files)
  - `banner/`: Banner images
  - `logo/`: Logo assets
  - `share/`: Social sharing/metadata images

### Configuration

- **`_config.yml`**: Site configuration
  - Title, email, phone numbers, address
  - Base URL and site URL
  - Theme: Minima
  - Plugins: jekyll-feed
  - SASS configuration
  - Includes `_pages` in build
  - Uses GFM (GitHub Flavored Markdown) parser

- **`.ruby-version`**: Specifies Ruby 2.6.2
- **`Gemfile`**: Gem dependencies (jekyll, minima, jekyll-feed, kramdown-parser-gfm)

## Content Guidelines

### Pages
- Page files use numbered prefixes to control navigation order (e.g., `010_services.md`, `04_job_request.md`)
- **Spanish content**: All user-facing text should be in Spanish (Puerto Rico dialect)
- **Redesigned pages** (as of 2026): Services, About, Gallery, Blog, Installation, and Heavy Equipment pages all use modern card-based layouts with Tailwind utility classes. When editing these pages, maintain the design patterns:
  - Intro sections with light slate background (`bg-slate50 rounded-lg p-8 my-8`)
  - Card grids using Tailwind: `grid grid-cols-1 md:grid-cols-2 gap-8`
  - CTA sections with red gradients: `bg-gradient-to-r from-accent to-red-600 text-white`
  - Service/benefit lists with checkmarks: `<span class="text-xl">✓</span>`

### Forms
Two main form patterns exist:
1. **Job Request** (`04_job_request.md`): Detailed form collecting customer info, vehicle details, glass type, and service preferences
2. **Mail Survey** (`05_mail_survey.md`): Simpler feedback/survey form

Form styling:
- Form fields have a red left border accent via custom SCSS in `_layout.scss`
- Fieldsets and legends have custom padding/margin for proper spacing
- All form styling preserved from previous version; only layout of surrounding content changed

Form responses are handled by Netlify; no backend processing is in the repo.

### Meta Tags and SEO
- Each page should include `metadescription` in front matter
- `head.html` includes:
  - Google Analytics tracking (UA-122312600-1)
  - Google Ads conversion tracking (AW-796440335)
  - Schema.org structured data for Organization
  - Social media links in structured data

## Design System (2026 Redesign)

### Color Palette
- **Primary (Dark Navy)**: `#0F172A` — used for navigation, hero section, footer, primary text
- **Accent (Bold Red)**: `#DC2626` — used for CTAs, highlights, hover states
- **Light Slate BG**: `#F1F5F9` — alternate section backgrounds for visual contrast
- **Body Text**: `#1E293B` — dark slate for readable body copy
- **Muted Text**: `#64748B` — secondary/tertiary text
- **White**: `#FFFFFF` — card backgrounds, text on dark backgrounds

Implementation: Tailwind custom colors defined in `head.html` CDN config + SCSS variables in `_base.scss` for non-Tailwind contexts.

### Typography
- **Headlines**: **Oswald** (Google Fonts) — bold, condensed, classic automotive feel
- **Body**: **Inter** (Google Fonts) — clean, modern, highly readable
- **Preconnect** to Google Fonts in `head.html` for performance

### Layout Patterns
1. **Hero Section** (`_includes/header.html`): Full-width background image with dark navy overlay, sticky navigation, white Oswald headline
2. **Card Grids**: Responsive 1-col mobile → 2-col desktop using Tailwind (`grid grid-cols-1 md:grid-cols-2 gap-8`)
3. **Page Title Bars** (`_layouts/page.html`): Dark navy to primary gradient with red accent underline
4. **Footer Grid** (`_includes/footer.html`): 3-column responsive footer with dark navy background
5. **CTA Sections**: Red gradient backgrounds with white text, two-button layouts (red primary + white outline secondary)
6. **Image Galleries**: Responsive grids with rounded cards, shadow hover states, captions

### Key Technologies & Patterns

#### Jekyll Specifics
- **Theme**: Minima (2.0+) - standard Jekyll theme
- **Markdown processor**: GFM (GitHub Flavored Markdown)
- **CSS approach**: Tailwind Play CDN (no build step) + SASS for theme defaults
- **Liquid templates**: Used in layouts and includes for dynamic content

#### Frontend
- **Styling**: Tailwind CSS Play CDN (included in `head.html`) — enables utility-first responsive design without Node.js build
- **Responsive Design**: Mobile-first Tailwind classes (e.g., `md:grid-cols-2`, `lg:text-xl`)
- **Vanilla JavaScript**: 
  - Responsive nav toggle in `default.html` via `toggleMobileMenu()` function
  - No frontend framework or transpiler
- **Custom SCSS**: Minimal rules in `_sass/` — only form styling and color variables. Most styling via Tailwind.
- **Icons**: Font Awesome via CDN in `stylesheet.html` + inline SVG icons in cards

### Form Handling
- Netlify-powered forms (declarative via HTML attributes)
- No backend API
- Redirect pages for form success (`045_job_request_response.md`, `055_mail_survey_response.md`)

## Pages Status (2026 Redesign) — COMPLETE ✅

### All Pages Redesigned (Modern Card-Based Layouts)

**Main Service Pages:**
- ✅ `010_services.md` — Service offerings with 2×2 card grid + product images
- ✅ `015_services_glass_installs.md` — Installation services with 4-card service grid + stats section
- ✅ `016_services_glass_heavy_equipment.md` — Heavy equipment with 4-card service grid + 6-image gallery
- ✅ `020_gallery.md` — Portfolio gallery with Curator.io embed + CTA section
- ✅ `030_about.md` — Company info with 4-card "Why Choose Us" grid + service areas

**Core Pages:**
- ✅ `_layouts/home.html` — Homepage with 3-service card grid + stats + service areas
- ✅ `blog/index.html` — Blog listing with card-based post layout + subscribe CTA

**Blog Posts (4 posts):**
- ✅ `_posts/2018-09-09-servicio-a-domicilio.markdown` — Home service with benefit card grid + process steps
- ✅ `_posts/2018-08-01-servicio-a-vieques.markdown` — Vieques service with coverage card grid + booking options
- ✅ `_posts/2018-09-23-jomar-auto-glass-en-vieques-octubre-3.markdown` — October 3 announcement with image card
- ✅ `_posts/2019-01-17-jomar-auto-glass-en-vieques-pronto.markdown` — 2019 announcement with image card

**Forms & Support Pages:**
- ✅ `04_job_request.md` — Job request form with modern intro + contact options
- ✅ `05_mail_survey.md` — Survey form with modern intro section
- ✅ `045_job_request_response.md` — Success response page
- ✅ `055_mail_survey_response.md` — Survey response page
- ✅ `09_privacy.md` — Privacy policy with modern intro + contact grid
- ✅ `011_friends.md` — Partners page with card grid for categories
- ✅ `060_service_areas.md` — Service areas page with intro + CTAs

### All Pages Now Redesigned ✅
- ✅ `_layouts/home.html` — Homepage with 3-service card grid, stats section, and service areas
- ✅ `04_job_request.md` — Job request form with modern intro and contact options
- ✅ `05_mail_survey.md` — Survey form with modern intro section
- ✅ `045_job_request_response.md` — Job request response page with success message
- ✅ `055_mail_survey_response.md` — Survey response page with success message and home link
- ✅ `09_privacy.md` — Privacy policy with modern intro and contact grid
- ✅ `011_friends.md` — Friends/partners page with card grid for partner categories
- ✅ `060_service_areas.md` — Service areas page with intro and CTA buttons

## Development Notes

- The site rebuilds on file changes when using `jekyll serve --livereload`
- Output is generated to `_site/` directory (in `.gitignore`)
- `.jekyll-metadata` tracks build state (in `.gitignore`)
- Forms do not require environment variables or secrets
- No build dependencies beyond Bundler and Ruby

## Important Implementation Notes

### Tailwind + SCSS Hybrid Approach
The site uses **Tailwind Play CDN** (no build step) for responsive design, combined with minimal custom SCSS for color variables and form styling:

- **Tailwind classes** are used in Markdown content (HTML in `.md` files) and layouts for utility-first responsive design
- **Color variables** defined in both `head.html` (Tailwind config) AND `_base.scss` (SCSS variables) to ensure consistency
- **SCSS rules** in `_layout.scss` are minimal — only form fieldset/legend/input styling and essential overrides (e.g., `!important` flags to override Minima theme defaults)
- **Typography** loaded via Google Fonts in `head.html` — Oswald for headlines, Inter for body text
- **CSS compilation**: SASS → CSS happens at build time; Tailwind utilities applied at runtime

### Color & Typography Usage
When editing content or creating new sections:
1. Use Tailwind color classes for consistency: `text-primary`, `bg-accent`, `bg-slate50`
2. Use font families via Tailwind: `font-heading` (Oswald), `font-body` (Inter)
3. Responsive prefixes: `md:grid-cols-2`, `lg:text-xl`, etc.
4. Never add inline colors — use the defined palette

### Handling SCSS Override Issues
If dark navy backgrounds show bright blue text (color conflict with Minima theme):
- Add `text-white` **class AND** inline `style="color: white !important;"` (the `!important` is necessary to override SCSS)
- This issue affects `h1` tags in dark sections (hero, page titles)

## Common Tasks

| Task | Command |
|------|---------|
| Add a new page | Create file in `_pages/` with number prefix and YAML front matter. Use existing pages as templates for card layouts. |
| Update navigation | Edit `_includes/header.html` nav items (Liquid loop) or adjust page order |
| Add images | Place in `assets/pictures/` (or relevant subdirectory) and reference via Tailwind responsive grid |
| Change colors | Update `_base.scss` SCSS variables AND `head.html` Tailwind config to stay in sync |
| Change typography | Edit font family imports in `head.html` and update Tailwind config |
| Change styling | Use Tailwind utility classes in HTML; only edit `_sass/` for form rules or critical overrides |
| Preview site locally | `bundle exec jekyll serve --livereload` — changes to Markdown and includes rebuild instantly |
| Add a form | Use Netlify form pattern: `<form method="POST" data-netlify="true">` with form fields and hidden redirect field |
