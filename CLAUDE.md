# EDDY.TION Portfolio Website

## Project Overview
A minimalist portfolio website for a motion and brand identity designer. The site features a dark aesthetic with clean typography and responsive design inspired by Studio Dumbar.

## Tech Stack
- Pure HTML/CSS (no frameworks)
- Vanilla JavaScript for dynamic content loading
- JSON-based data management
- Inter font family (Google Fonts)
- Responsive design with viewport-based units
- MP4 video background support

## File Structure
```
eddytion.io/
├── index.html          # Home page with video background
├── work.html           # Work portfolio (3-column grid, 1:1 ratio)
├── play.html           # Experimental work (4-column grid, variable sizes)
├── about.html          # About page with bio text
├── content.html        # Project detail page
├── data/
│   ├── work.json      # Work projects data (title, subtitle, thumbnail, link)
│   ├── play.json      # Play projects data (title, subtitle, thumbnail, size)
│   └── README.md      # Content management guide
├── assets/
│   ├── work/          # Work project images (organized by project ID)
│   └── play/          # Play project images (organized by project ID)
├── background.mp4      # Hero video background
├── background.png      # Fallback background image
└── .gitignore          # Git ignore rules
```

## Content Management System

### Adding New Projects

**Work Projects** (`data/work.json`):
1. Create folder: `assets/work/project-id/`
2. Add thumbnail image (recommended: 1200x1200px, 1:1 ratio)
3. Add entry to `work.json`:
   ```json
   {
     "id": "project-id",
     "title": "Project Title",
     "subtitle": "Project Description",
     "thumbnail": "assets/work/project-id/thumbnail.jpg",
     "link": "content.html?id=project-id"
   }
   ```

**Play Projects** (`data/play.json`):
1. Create folder: `assets/play/project-id/`
2. Add thumbnail image (size based on `size` property)
3. Add entry to `play.json`:
   ```json
   {
     "id": "project-id",
     "title": "Project Title",
     "subtitle": "Project Description",
     "thumbnail": "assets/play/project-id/thumbnail.jpg",
     "size": "size-large"
   }
   ```

**Play Grid Sizes**:
- `size-square`: 1x1 square
- `size-vertical`: 1x2 vertical rectangle
- `size-horizontal`: 2x1 horizontal rectangle
- `size-large`: 2x2 large square

### Updating Projects
- Edit JSON files to change titles, descriptions, or order
- Replace images in asset folders to update visuals
- No HTML editing required for content updates

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
- JavaScript used only for JSON data loading (async fetch)
- Projects dynamically generated from JSON data
- Images loaded as CSS background-image for proper sizing

## Content Workflow
1. **Add Images**: Place thumbnails in `assets/work/` or `assets/play/`
2. **Update JSON**: Edit `data/work.json` or `data/play.json`
3. **Commit & Push**: Changes appear immediately on GitHub Pages
4. **No Build Step**: Static files only, direct deployment

## Future Considerations
- Add smooth scroll behavior
- Consider lazy loading for images
- Add meta tags for SEO
- Implement Open Graph tags for social sharing
- Add image optimization pipeline
- Consider adding a CMS integration
