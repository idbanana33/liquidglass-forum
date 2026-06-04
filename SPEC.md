# LiquidGlass Forum - Specification

## Concept & Vision

A futuristic communication forum for young people that captures Apple's iOS 18 liquid glass aesthetic — translucent surfaces with dynamic light refraction, caustic patterns, and ray-traced shadows. The interface feels like touching glass that bends light, where every surface breathes with color and every interaction ripples with energy. This is digital liquid metal meets social space.

## Design Language

### Aesthetic Direction
iOS liquid glass with bioluminescent undertones — imagine frosted crystal floating in a gradient void, where light bends through layered transparency creating caustic patterns and prismatic refractions. Dark mode dominant with vibrant accent glows.

### Color Palette
- **Background**: Deep space gradient `#0a0a0f` → `#1a1a2e` → `#16213e`
- **Glass Primary**: `rgba(255, 255, 255, 0.08)` with backdrop blur
- **Glass Border**: `rgba(255, 255, 255, 0.18)` 
- **Accent Cyan**: `#00d4ff` (primary glow)
- **Accent Magenta**: `#ff006e` (secondary glow)
- **Accent Purple**: `#8b5cf6` (tertiary)
- **Text Primary**: `rgba(255, 255, 255, 0.95)`
- **Text Secondary**: `rgba(255, 255, 255, 0.6)`

### Typography
- **Display**: "Syne" (bold, futuristic) — headings and hero text
- **Body**: "DM Sans" — clean, readable for content
- **Mono**: "JetBrains Mono" — code snippets, timestamps

### Motion Philosophy
- Page load: Staggered glass panels fade in with 0.6s ease-out, 100ms delays
- Hover: Glass surfaces lift (translateY -4px) with enhanced glow
- Caustic patterns: Slow-moving SVG noise (15s loop)
- Interactive elements: Subtle pulse animation on focus
- Smooth scroll with momentum feel

### Visual Assets
- Custom SVG caustic/ray patterns
- Gradient mesh backgrounds
- Icon library: Phosphor Icons (thin weight)
- Avatar placeholders: Gradient circles with initials

## Layout & Structure

### Page Architecture
1. **Floating Navigation Bar** — Pill-shaped glass navbar with logo, search, user avatar
2. **Hero Section** — Large glass card with trending话题, animated caustic background
3. **Content Grid** — 2-column masonry-style forum posts with varying glass intensities
4. **Sidebar** — Trending topics, online users (glass cards stacked)
5. **Post Cards** — Each with unique caustic pattern overlay based on category

### Responsive Strategy
- Desktop: 2-column content + sidebar
- Tablet: Single column, sidebar collapses to horizontal scroll
- Mobile: Full-width cards, bottom nav bar

## Features & Interactions

### Core Features
1. **Forum Posts Feed** — Infinite scroll with lazy-loaded glass cards
2. **Post Creation** — Floating action button opens glass modal with blur backdrop
3. **Category Filtering** — Pill buttons with active state glow
4. **User Interactions** — Like (heart pulse), Comment (expand), Share (ripple)
5. **Real-time Indicators** — Online users count, new post badge

### Interaction Details
- **Card Hover**: Glass lifts, border brightens, caustic pattern intensifies
- **Like Button**: Heart fills with gradient, particle burst on click
- **Search**: Glass input expands on focus, results dropdown appears
- **FAB**: Opens with scale + rotation animation

### States
- **Loading**: Skeleton cards with shimmer animation
- **Empty**: Illustrated glass card with CTA
- **Error**: Red-tinted glass with retry button

## Component Inventory

### Glass Card
- Background: `rgba(255,255,255,0.05)` + `backdrop-filter: blur(20px)`
- Border: 1px solid `rgba(255,255,255,0.1)`
- Border-radius: 24px
- Shadow: `0 8px 32px rgba(0,0,0,0.3)`
- Hover: Border brightens to `rgba(255,255,255,0.2)`, translateY(-4px)

### Navigation Bar
- Position: Fixed top, centered
- Shape: Pill/capsule with glass effect
- Height: 64px, max-width: 1200px
- Logo with gradient text

### Post Card
- Author avatar, username, timestamp
- Post title (Syne bold)
- Content preview (2 lines, DM Sans)
- Category tag (pill with glow)
- Engagement: likes count, comments count
- Caustic SVG overlay (position: absolute, mix-blend-mode)

### Action Button (FAB)
- Size: 56px circle
- Glass with gradient border
- Icon: Plus sign
- Hover: Scale 1.1, glow intensifies

### Input Fields
- Glass background with inner shadow
- Placeholder: secondary text color
- Focus: Cyan glow border, background lightens

## Technical Approach

- **Framework**: Single HTML file with embedded CSS/JS
- **CSS**: Custom properties for theming, @keyframes for animations
- **JS**: Vanilla JS for interactions, CSS for most animations
- **Fonts**: Google Fonts (Syne, DM Sans, JetBrains Mono)
- **Icons**: Phosphor Icons via CDN
- **Effects**: CSS backdrop-filter, SVG filters for noise/caustics
