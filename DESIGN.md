# Design Specification - EDDY.TION

## Design Philosophy
Minimalist, typography-focused portfolio inspired by Studio Dumbar's fluid responsive approach. Emphasizes content over decoration with bold typography and generous white space.

## Visual Language

### Typography Scale
```
Hero/Title:     60px / 700 / -2px / 112% line-height
Navigation:     24px / 500 / 0px / 100% line-height
Logo:           24px / 700 / 0px / 100% line-height
Mobile Title:   36px (768px and below)
Mobile Nav:     18px (600px and below)
```

### Color Palette
```
Primary Background:   #000000 (Black)
Inverted Background:  #FFFFFF (White - Play page only)
Primary Text:         #FFFFFF (White on dark)
Inverted Text:        #000000 (Black on light)
Placeholder:          #D9D9D9 (Light gray)
Overlay:             rgba(0, 0, 0, 0.6) (Hover state)
```

### Spacing System
```
Container Padding (Responsive):
  Mobile:        24px (fixed)
  Tablet:        4vw (769px+)
  Desktop:       6vw (1440px+)
  Wide:          8vw (1920px+)

Grid Gaps:       16px
Nav Link Gap:    200px
Section Padding: 73px vertical (desktop)
                 40px vertical (mobile)
```

## Component Specifications

### Navigation Bar
- **Position**: Fixed bottom
- **Height**: 100px (desktop), auto (mobile)
- **Background**: Gradient fade to transparent
- **Layout**: 3-column flex (Logo | Links | Social)
- **Alignment**: 
  - Logo: Left
  - Links: Absolute center
  - Social: Right
- **States**: Hover opacity 0.6

### Project Grid - Work Page
```
Columns:       3 (1200px+) → 2 (900px+) → 1 (600px-)
Aspect Ratio:  1:1 (square)
Gap:           16px
Overlay:       Appears on hover (opacity 0→1)
Card Info:     Centered title on dark overlay
```

### Project Grid - Play Page
```
Columns:       4 (1200px+) → 3 → 2 → 1
Aspect Ratio:  3:4 (portrait)
Gap:           16px
Background:    White (inverted theme)
Overlay:       Same as Work page
```

### Hero Section (Home)
```
Height:        100vh
Video:         Absolute positioned, object-fit: cover
Text:          Positioned over video with z-index
Background:    Black (fallback before video loads)
```

### About Section
```
Layout:        Full viewport height flex container
Text Size:     60px → 48px → 36px (responsive)
Alignment:     Flex start (top-left area)
Padding:       73px vertical (desktop), 40px (mobile)
```

## Interaction Design

### Hover States
- **All Links**: opacity: 1 → 0.6 (0.3s ease)
- **Project Cards**: Overlay opacity: 0 → 1 (0.3s ease)
- **Cursor**: Default (no custom cursor)

### Transitions
```css
All interactive elements: 0.3s ease
Properties: opacity only (for performance)
```

### Responsive Behavior
- **Navigation**: Horizontal → Stacked vertical on mobile
- **Grids**: Column count reduces progressively
- **Typography**: Scales down at breakpoints, never fluid
- **Padding**: Fluid vw units between fixed breakpoints

## Layout Patterns

### Page Structure
```
[Video/Content Area - Full viewport]
[Navigation - Fixed bottom with gradient]
```

### Responsive Grid Formula
```
Desktop → Tablet → Mobile
4 columns → 3 → 2 → 1  (Play)
3 columns → 2 → 1       (Work)
```

### Padding Philosophy
- No max-width containers
- Content scales with viewport using vw-based padding
- Creates natural margins that grow with screen size
- Prevents content from touching viewport edges on any size

## Brand Elements

### Logo Treatment
- All caps: "EDDY.TION"
- Weight: 700 (bold)
- No special styling or effects
- Links to home

### Social Icons
- Instagram and Behance SVG icons
- Inline SVG (no external requests)
- Color matches theme (white or black)
- 30px × 30px Instagram, 37px × 30px Behance

## Accessibility Considerations
- High contrast (black/white)
- Clear focus states (browser default)
- Semantic HTML structure
- aria-labels on icon-only links
- Readable font sizes (minimum 18px on mobile)

## Performance Optimizations
- Inline SVG icons
- Single font family (Inter) from Google Fonts
- CSS-only interactions (no JavaScript)
- Video attributes for autoplay optimization
- No external CSS frameworks

## Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge)
- CSS Grid and Flexbox required
- Video element required for home page
- No IE11 support needed

## Design Inspirations
- Studio Dumbar (fluid responsive padding)
- Swiss design (grid system, typography focus)
- Brutalism (minimal decoration, raw functionality)
