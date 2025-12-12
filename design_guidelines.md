# QR Code Generator - Design Guidelines

## Design Approach

**Hybrid System**: Drawing inspiration from design tool interfaces (Canva, Figma) combined with Material Design principles for a clean, functional utility application. The interface prioritizes clarity, real-time feedback, and effortless customization.

**Core Principle**: The QR code preview is the hero - all controls should feel supportive, not overwhelming.

## Layout Architecture

**Desktop Layout** (lg:):
- Two-column split layout: 40% controls panel (left), 60% preview area (right)
- Controls panel: Fixed width sidebar with scrollable content
- Preview area: Centered QR code with generous whitespace, download controls below

**Mobile Layout**:
- Stack vertically: Preview on top, controls below
- Sticky download button at bottom
- Collapsible control sections for better space management

**Spacing System**: Use Tailwind units of 3, 4, 6, and 8 consistently throughout (p-3, gap-4, my-6, px-8)

## Typography

**Font Stack**:
- Primary: 'Inter' (Google Fonts) - clean, modern sans-serif for UI
- Weights: 400 (regular), 500 (medium), 600 (semibold)

**Hierarchy**:
- Page title: text-2xl font-semibold
- Section headers: text-base font-medium uppercase tracking-wide
- Input labels: text-sm font-medium
- Helper text: text-xs
- Button text: text-sm font-medium

## Component Library

### Input Controls

**Text Input**:
- Large textarea for URL/text input with placeholder
- Border treatment with focus states
- Character counter below input
- Rounded corners (rounded-lg)

**Color Pickers**:
- Two prominent color inputs: Foreground and Background
- Display current color value as hex
- Large clickable color preview squares (w-12 h-12)
- Label + color preview + hex value horizontal layout

**Size Slider**:
- Range input (128px to 512px)
- Visual current value display (large, prominent)
- Tick marks at common sizes (256, 384, 512)
- Immediate preview update

**Style Selection**:
- Grid of style options (2 columns on mobile, 3 on desktop)
- Visual preview cards showing each style pattern
- Active state with border highlight
- Options: Square (classic), Rounded, Dots, Circles

### Preview Area

**QR Code Display**:
- Large centered canvas/image element
- Generous padding around QR code (p-12)
- Subtle shadow for depth
- Checkerboard pattern background for transparency indication

**Download Section**:
- Primary CTA button: "Download QR Code" - large, prominent
- Secondary button: "Copy as Image"
- Format selector dropdown (PNG default, future: SVG, PDF)
- File naming preview showing generated filename

### Control Panel Structure

**Section Organization** (vertical stack, gap-6):
1. Input Section - "Enter Content"
2. Style Section - "QR Code Style"
3. Colors Section - "Customize Colors"
4. Size Section - "Adjust Size"

Each section:
- Clear header with icon (Heroicons)
- Grouped controls with consistent spacing
- Visual separation with subtle borders or background panels

## Navigation

**Header**:
- App title with QR icon
- Tagline: "Generate custom QR codes instantly"
- GitHub/info icon link (top-right)
- Minimal, fixed position

**No traditional navigation needed** - single-page application

## Interaction Patterns

**Real-time Updates**:
- QR code regenerates instantly on any control change
- Smooth transitions (transition-all duration-200)
- Loading state for generation (subtle spinner overlay)

**Visual Feedback**:
- Focus rings on all interactive elements
- Hover states on buttons and style cards
- Active/selected states clearly differentiated
- Success message on download/copy

## Animations

**Minimal Approach**:
- Fade-in on initial QR code generation (opacity transition)
- Smooth scale on style card hover (scale-105)
- Success checkmark animation on download
- No complex scroll-driven or attention-seeking animations

## Accessibility

- All inputs have visible labels
- Color contrast meets WCAG AA standards
- Keyboard navigation for all controls
- ARIA labels for icon-only buttons
- Focus indicators on all interactive elements

## Icons

**Library**: Heroicons (via CDN)

**Usage**:
- QR code icon for app logo
- Download icon for download button
- Copy icon for copy button
- Color swatch icons for color pickers
- Adjustment icons for size controls

## Images

**No hero image needed** - This is a utility tool where the generated QR code IS the visual focus.

**Background Pattern** (optional):
- Subtle grid or dot pattern in preview area background
- Very low opacity to avoid distraction

## Responsive Breakpoints

- Mobile: < 768px (single column, stacked)
- Tablet: 768px - 1024px (two columns, adjusted ratio)
- Desktop: > 1024px (optimal two-column layout)

## Design Excellence Notes

- Keep the interface clean and distraction-free
- Ensure instant visual feedback for all interactions
- Make the QR code preview prominent and shareable-ready
- Provide clear visual hierarchy in control panels
- Use ample whitespace to prevent claustrophobia
- Design for both quick generation and detailed customization workflows