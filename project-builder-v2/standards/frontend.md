# Frontend & UI/UX Standards

## 1. Visual Design System
- **Color Palette**: Use curated HSL color systems with distinct semantic tokens (primary, secondary, background, surface, text-primary, text-muted, accent, danger).
- **Typography**: Modern font pairings (Inter, Outfit, Roboto) with clear scale hierarchy.
- **Glassmorphism & Gradients**: Subtle background blur, glass cards, soft drop shadows, and modern micro-animations.

## 2. Five UI States Pattern
Every interactive screen or data list MUST implement 5 UI states:
1. **Default State**: Data rendered cleanly.
2. **Loading State**: Skeleton cards or spinners while fetching.
3. **Empty State**: Friendly graphic/icon with a clear CTA button when zero items exist.
4. **Error State**: Non-blocking alert message with a "Retry" button.
5. **Disabled / Submitting State**: Form fields and submit buttons disabled during network requests to prevent duplicate submissions.

## 3. Responsive Breakpoints
- **Mobile**: `< 768px` (single column layout, collapsible navigation drawer, touch target size $\ge 44\text{px}$).
- **Tablet**: `768px - 1024px` (2-column layout, responsive grids).
- **Desktop**: `> 1024px` (multi-column dashboard grids, side navigation).

## 4. Accessibility (a11y)
- Use semantic HTML tags (`<header>`, `<nav>`, `<main>`, `<article>`, `<footer>`).
- Ensure custom interactive elements have proper `aria-` attributes and keyboard focus state outline.
