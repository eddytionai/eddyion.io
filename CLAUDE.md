# EDDY.TION Portfolio Website

## Project Overview
A minimalist portfolio website for a motion and brand identity designer. The site features a dark aesthetic with clean typography and responsive design inspired by Studio Dumbar.

## Tech Stack
- Pure HTML/CSS (no frameworks)
- Inter font family (Google Fonts)
- Responsive design with viewport-based units
- MP4 video background support

## File Structure
```
eddytion.io/
├── index.html          # Home page with video background
├── work.html           # Work portfolio (3-column grid, 1:1 ratio)
├── play.html           # Experimental work (4-column grid, 3:4 ratio)
├── about.html          # About page with bio text
├── background.mp4      # Hero video background
├── background.png      # Fallback background image
└── .gitignore          # Git ignore rules
```

## Design System

### Typography
- **Font Family**: Inter (weights: 400, 500, 600, 700)
- **Title Font Size**: 60px (desktop) → 48px (tablet) → 36px (mobile)
- **Navigation Font Size**: 24px (desktop) → 18px (mobile)
- **Line Height**: 112% (titles), 100% (navigation)
- **Letter Spacing**: -2px (titles)

### Colors
- **Background**: 
  - Home/Work/About: `#000` (black)
  - Play: `#FFF` (white)
- **Text**: 
  - Home/Work/About: `#FFF` (white)
  - Play: `#000` (black)
- **Placeholder**: `#D9D9D9` (light gray)

### Layout & Spacing
- **Responsive Padding**: 
  - Mobile (<768px): 24px fixed
  - Tablet (769-1439px): 4vw
  - Desktop (1440-1919px): 6vw
  - Wide (≥1920px): 8vw
- **Navigation Height**: 100px (desktop), auto (mobile)
- **Grid Gaps**: 16px
- **Navigation Link Gap**: 200px

### Navigation
- **Logo**: Left-aligned, weight 700
- **Links**: Center-aligned (Work, Play, About), gap 200px
- **Social Icons**: Right-aligned (Instagram, Behance)
- **Gradient Background**: `linear-gradient(0deg, [color] -58%, rgba([color], 0.00) 81.5%)`

## Responsive Breakpoints
```css
Mobile:    ≤600px  (1 column)
Tablet:    ≤768px  (smaller fonts, adjusted spacing)
Small:     ≤900px  (2 columns on Work/Play)
Medium:    ≤1200px (3 columns on Play)
Desktop:   >1200px (default layout)
```

## Page-Specific Details

### index.html (Home)
- Full-screen video background with `autoplay`, `muted`, `loop`, `playsinline`
- Hero text: "MOTION AND BRAND IDENTITY DESIGN"
- Dark theme with white text
- Video positioned absolutely with `object-fit: cover`

### work.html (Work Portfolio)
- 3-column grid (responsive: 3 → 2 → 1 columns)
- Square project cards (1:1 aspect ratio)
- Hover overlay with project title
- Title: "MOTION AND BRAND IDENTITY DESIGN"

### play.html (Experimental Work)
- 4-column grid (responsive: 4 → 3 → 2 → 1 columns)
- Vertical project cards (3:4 aspect ratio)
- White background with black text
- Title: "A PLACE MAKE, EXPERIMENT AND PLAY"

### about.html (About)
- Minimal single-text layout
- Text: "I have been planing and creating contents based on understanding brand essense."
- Vertically centered content
- Dark theme with white text

## Key Features
- No `max-width` constraints - content scales naturally with viewport
- Viewport-based padding for fluid responsive behavior
- Consistent navigation across all pages with theme-appropriate colors
- Hover effects on all interactive elements (opacity: 0.6)
- Mobile-optimized navigation (stacked layout on small screens)

## Development Notes
- All pages use the same responsive padding system
- Navigation links are absolutely centered for precise alignment
- SVG icons inline for performance (no external requests)
- Video background fallback handled by browser (shows black on load)
- No JavaScript required - pure CSS animations and interactions

## Future Considerations
- Add actual project content and images
- Implement project detail pages
- Add smooth scroll behavior
- Consider lazy loading for images
- Add meta tags for SEO
- Implement Open Graph tags for social sharing
