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
- Founder cards dimensions: 420px wide, 550px minimum height with increased padding and spacing; hover lift effect disabled
- Infinite carousel: Cloned first/last cards enable seamless looping; cards automatically advance every 5s
- Blur effects: Non-focused cards blur (4px) and fade (50% opacity) with subtle scale-down (95%); smooth 0.5s transitions on filter, opacity, and transform
- Mobile responsive design (768px and below):
  - About section: Preserves 3-column photo grid layout with adjusted inset (1.5rem) and minimal gap (0.25rem)
  - About section: Flexible height (min-height instead of fixed h-screen) for better content flow
  - Meet Our Founders section: Maintains desktop layout with adjusted padding and spacing
  - Founder cards resize to 90vw (max 350px) with responsive positioning
  - Navigation compresses with smaller fonts and spacing
  - Most grids switch to single column layout (except About photo grid)
  - Touch-friendly buttons (min 44px height)
  - Blur effects disabled on mobile for better performance
  - Cards use opacity reduction instead of blur on mobile (60% vs 50%)
- Small mobile optimization (480px and below):
  - About section: Tighter photo grid spacing (1rem inset, 0.125rem gap)
  - Founders section: Reduced padding for better card visibility
  - Founder cards at 95vw (max 320px)
  - Navigation stacks vertically
  - Reduced text sizes and padding for compact display
- Extended smooth scroll animations across entire website:
  - Added fade-in animations to all sections (founders, mentor grid, footer)
  - Implemented staggered animations for mentor cards (50ms delay between each)
  - Implemented staggered animations for mentee cards (100ms delay between each)
  - Enhanced Intersection Observer with better threshold and margin settings
  - Animations trigger when elements are 10% visible with 100px bottom margin
- Enhanced About section with dynamic animations:
  - Animated gradient background (same as hero section, perfectly synchronized)
  - Background gradient shifts through dark gray, navy, and blue shades in 15-second cycle
  - Rotating image carousel overlays the gradient (9 gallery images, 3-second intervals)
  - Image grid has spacing on all edges (~40px) so animated gradient is visible as a frame
  - Rounded corners on image grid for polished appearance
  - Smooth fade transitions between background images (1.5s duration)
  - Creates cohesive visual connection between hero and about sections
  - Subtle hovering text animation with floating effect (4s cycle, moves up 5px)
  - Synchronized float animations on title and paragraphs for cohesive movement
- Enhanced Hero section with dynamic animations:
  - Animated gradient background that shifts between dark gray, navy, and blue shades
  - Gradient animation completes full cycle in 15 seconds with smooth transitions
  - Copula logo floating animation (5s cycle, moves up 8px) for gentle visual appeal
  - Title text "The Copula Program" floats in sync with the logo (5s cycle)
- Applied consistent light shadow across entire website:
  - Text shadow (2px vertical offset, 8px blur, 30% opacity) on all text elements (headings, paragraphs, links, buttons, spans)
  - Box shadow on all cards and frames for depth and visual hierarchy
  - Creates cohesive, polished look throughout the site with enhanced readability
- Added interactive hover effects to all buttons and frames:
  - Smooth lift animation (5px upward movement) when mouse hovers over elements
  - Enhanced shadow on hover (increased depth and darkness) for visual feedback
  - 0.3s smooth transition for elegant interaction
  - Automatically returns to original position when mouse leaves
  - Mentee cards excluded from lift effect - they keep their original border color change animation (gray to blue)
  - Founder cards excluded from lift effect for cleaner carousel interaction

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
