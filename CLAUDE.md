# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Swedish travel website for Cecilia "Cissi" Jakobsson, a travel guide specializing in personal tours to Italy. The website is built as a static HTML/CSS/JavaScript site featuring tour information, photo galleries, and booking capabilities through Facebook integration.

## Architecture

### Core Structure
- **Static HTML Pages**: Multiple interconnected pages using consistent navigation
  - `index.html`: Homepage with tour overview and about section
  - `resor.html`: Tours listing page
  - `capri.html`, `rom.html`: Individual tour detail pages
  - `presentation.html`: About Cecilia page
  - `foredrag.html`: Speaking engagements page
  - `bildgalleri.html`: Photo gallery
  - `kontakt.html`: Contact information

### Data Management
- **Dynamic Content**: Tours are loaded from `tours.json` using JavaScript fetch API
- **Image Assets**: Organized in `assets/images/` with subdirectories for different tour locations
- **Content Language**: All content is in Swedish

### JavaScript Architecture
- **No Build System**: Pure vanilla JavaScript, no bundlers or transpilation
- **Inline Scripts**: All JavaScript is embedded directly in HTML files using `<script>` tags
- **Common Functionality**: Each page includes identical cookie consent and Google Analytics code
- **Tour Loading**: Dynamic tour card generation from `tours.json` on homepage and tours page
- **Gallery Systems**: Lightbox functionality for image galleries on tour detail pages
- **Event Handling**: DOM manipulation using `addEventListener` and standard Web APIs

### Key Features
- **Cookie Consent System**: Comprehensive GDPR-compliant cookie management with Google Analytics integration
- **Facebook Integration**: Primary booking method through Facebook page links
- **Responsive Design**: Mobile-friendly layout using CSS Grid and Flexbox
- **Image Galleries**: Static gallery grids with background images
- **Tour Cards**: Dynamic generation from JSON data

## Development Commands

Since this is a static website with no build system:
- **Local Development**: Open HTML files directly in browser or use a simple HTTP server like `python -m http.server 8000` or `npx serve .`
- **Testing**: Manual testing by opening pages in different browsers and devices
- **No Build Process**: Files can be edited directly and changes are immediately visible
- **Deployment**: Static files can be uploaded directly to web server
- **No Package Manager**: No npm, yarn, or other dependency management - pure static files

## Development Workflow

### File Editing
- Always maintain Swedish language content when editing text
- Preserve existing navigation structure across all HTML pages
- Keep Facebook booking links intact (`https://www.facebook.com/ceciliajakobsson.se`)

### Tour Management
- Add new tours by editing `tours.json` (currently contains 2 tours: Capri and Rome)
- Tour card images should be placed in `assets/images/tours/` (e.g., tour-capri.jpg)
- Tour gallery images should be placed in `assets/images/tours/[location]/`
- Each tour requires: id, title, short_description, long_description, days, price, image, link
- Create corresponding HTML detail pages for new tours (follow `capri.html` or `rom.html` structure)
- Tour data is fetched dynamically on `index.html` and `resor.html` using vanilla JavaScript

### CSS Styling
- Single stylesheet at `css/style.css` contains all styling
- Uses CSS Grid for tour layouts and gallery grids
- Color scheme: Primary blue (#1a76d2), white backgrounds, dark text (#333)
- Responsive breakpoints implemented for mobile compatibility

### Code Duplication Patterns
- **Cookie Consent JavaScript**: Identical implementation across all 8 HTML pages
- **Google Analytics Setup**: Same tracking code (G-S7XXTKR460) and consent management on every page
- **Navigation Structure**: Consistent header/nav markup duplicated in each file
- **Hero Section Structure**: Similar patterns across pages with different content
- **Footer Structure**: Repeated across all pages
- **When making changes**: Update all pages that contain the duplicated code - no shared components or templates

### Analytics & Tracking
- Google Analytics (G-S7XXTKR460) integrated with consent management
- Cookie preferences stored in localStorage
- Analytics consent updates dynamically based on user preferences

### Image Organization
- `assets/images/tours/`: Tour-specific images for cards (tour-capri.jpg, tour-rom.jpg, etc.)
- `assets/images/tours/capri/`: Detailed gallery images for Capri tour
- `assets/images/tours/rom/`: Detailed gallery images for Rome tour  
- `assets/images/prior-tours/`: General gallery images from past tours
- `assets/images/`: Profile images (cissi.jpg), hero backgrounds (hero.jpg), and historical tour photos

## Contact Information
- Email: ceciliajakobsson_250@hotmail.com
- Phone: +46 70 396 73 54
- Facebook: https://www.facebook.com/ceciliajakobsson.se
- Booking: All tours are booked through Facebook page

## Important Notes
- This is a personal travel business website, not a large-scale commercial operation
- Content focuses on authentic, small-group travel experiences to Italy
- Maintain the personal, intimate tone when editing content
- All external links should open in new tabs (`target="_blank"`)