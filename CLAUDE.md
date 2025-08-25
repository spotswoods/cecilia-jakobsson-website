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

### Key Features
- **Cookie Consent System**: Comprehensive GDPR-compliant cookie management with Google Analytics integration
- **Facebook Integration**: Primary booking method through Facebook page links
- **Responsive Design**: Mobile-friendly layout using CSS Grid and Flexbox
- **Image Galleries**: Static gallery grids with background images
- **Tour Cards**: Dynamic generation from JSON data

## Development Workflow

### File Editing
- Always maintain Swedish language content when editing text
- Preserve existing navigation structure across all HTML pages
- Keep Facebook booking links intact (`https://www.facebook.com/ceciliajakobsson.se`)

### Tour Management
- Add new tours by editing `tours.json`
- Tour images should be placed in `assets/images/tours/`
- Each tour requires: id, title, short_description, long_description, days, price, image, link
- Create corresponding HTML detail pages for new tours (follow `capri.html` or `rom.html` structure)

### CSS Styling
- Single stylesheet at `css/style.css` contains all styling
- Uses CSS Grid for tour layouts and gallery grids
- Color scheme: Primary blue (#1a76d2), white backgrounds, dark text (#333)
- Responsive breakpoints implemented for mobile compatibility

### Analytics & Tracking
- Google Analytics (G-S7XXTKR460) integrated with consent management
- Cookie preferences stored in localStorage
- Analytics consent updates dynamically based on user preferences

### Image Organization
- `assets/images/tours/`: Tour-specific images for cards
- `assets/images/tours/[location]/`: Detailed galleries for individual tours
- `assets/images/prior-tours/`: General gallery images
- `assets/images/`: Profile images and hero backgrounds

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