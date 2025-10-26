# The Copula Program Website

## Overview
This is the official website for The Copula Program, a six-week remote academic mentorship program for high school students. The site is built as a static website using HTML, CSS, and Tailwind CSS.

**Purpose**: Provide information about the program, showcase past mentors, and facilitate applications.

**Current State**: Fully functional static website, deployed and ready for production.

## Recent Changes (October 26, 2025)
- Imported project from GitHub
- Set up build process for Tailwind CSS
- Configured http-server to serve the static site on port 5000
- Added deployment configuration for Replit autoscale deployment
- Updated .gitignore to exclude dist folder
- Added founders carousel to About section with cards for three program founders

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
