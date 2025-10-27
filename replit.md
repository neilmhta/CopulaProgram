# The Copula Program Website

## Overview
This is the official website for The Copula Program, a six-week remote academic mentorship program for high school students. The site is built as a static website using HTML, CSS, and Tailwind CSS.

**Purpose**: Provide information about the program, showcase past mentors, and facilitate applications.

**Current State**: Fully functional static website, deployed and ready for production.

## Recent Changes (October 27, 2025)
- Imported project from GitHub
- Set up build process for Tailwind CSS
- Configured http-server to serve the static site on port 5000
- Added deployment configuration for Replit autoscale deployment
- Updated .gitignore to exclude dist folder
- Added founders carousel in dedicated section with peek view layout
- Carousel features: previous/next buttons, indicator dots, auto-advance, square image placeholders
- Separated founders section from About section to prevent morphing with mentee experiences section
- Extended smooth scroll animations across entire website:
  - Added fade-in animations to all sections (founders, mentor grid, footer)
  - Implemented staggered animations for mentor cards (50ms delay between each)
  - Implemented staggered animations for mentee cards (100ms delay between each)
  - Enhanced Intersection Observer with better threshold and margin settings
  - Animations trigger when elements are 10% visible with 100px bottom margin
- Enhanced About section with dynamic animations:
  - Rotating background carousel that cycles through 9 gallery images every 3 seconds
  - Smooth fade transitions between background images (1.5s duration)
  - Subtle hovering text animation with floating effect (4s cycle, moves up 5px)
  - Synchronized float animations on title and paragraphs for cohesive movement
- Enhanced Hero section with dynamic animations:
  - Animated gradient background that shifts between dark gray, navy, and blue shades
  - Gradient animation completes full cycle in 15 seconds with smooth transitions
  - Copula logo floating animation (5s cycle, moves up 8px) for gentle visual appeal
  - Title text "The Copula Program" floats in sync with the logo (5s cycle)
  - Light text shadow on title (subtle 8px blur with 30% opacity) for depth and readability

## Project Architecture

### Tech Stack
- **Frontend**: Static HTML with Tailwind CSS
- **Build Tool**: Node.js with npm scripts
- **Web Server**: http-server (for both development and production)
- **Deployment**: Replit autoscale (static hosting)

### Directory Structure
```
src/
  ├── index.html          # Main HTML file
  ├── input.css           # Tailwind CSS input
  ├── output.css          # Generated CSS (copied to dist)
  ├── CNAME              # Custom domain configuration
  └── static/            # Images, logos, and assets
dist/                    # Build output (served by http-server)
```

### Build Process
- `npm run build` - Builds CSS and copies all files to dist/
- `npm run build:css` - Compiles Tailwind CSS
- `npm run copy:html` - Copies HTML to dist
- `npm run copy:static` - Copies static assets to dist
- `npm run copy:cname` - Copies CNAME file to dist

### Development Workflow
The site runs on port 5000 with cache disabled (-c-1 flag) to ensure changes are immediately visible.

### Deployment
Configured for Replit autoscale deployment:
- Build step runs `npm run build`
- Serves static files from dist/ folder on port 5000
- No persistent state required (stateless static site)
