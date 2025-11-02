# HandiHelp Design Guidelines

## Design Approach
**System-Based Approach**: Given the utility-focused nature of this accessibility platform and the explicit requirement for functionality over visual complexity, we'll use principles from **Material Design** adapted for maximum accessibility, with inspiration from government accessibility standards (like gov.uk) for clarity and usability.

## Core Design Principles
1. **Accessibility First**: WCAG 2.1 AA compliance minimum, with AAA contrast ratios preferred
2. **Functional Clarity**: Every element serves a clear purpose
3. **Cognitive Simplicity**: Reduce mental load, clear hierarchy, obvious actions
4. **Inclusive Design**: Works for all disability types (motor, visual, auditory)

## Typography
- **Primary Font**: Inter or Roboto via Google Fonts (excellent readability, open license)
- **Headings**: 
  - H1: text-4xl md:text-5xl, font-bold
  - H2: text-3xl md:text-4xl, font-semibold
  - H3: text-2xl, font-semibold
- **Body Text**: text-base md:text-lg (minimum 16px for accessibility)
- **Labels**: text-sm font-medium, uppercase tracking-wide for form labels
- **Line Height**: leading-relaxed (1.625) for better readability

## Layout System
**Spacing Units**: Use Tailwind units of 4, 8, 12, 16, 20, 24 for consistent rhythm
- Section padding: py-16 md:py-24
- Card padding: p-8 md:p-12
- Form spacing: gap-6 between fields
- Button padding: px-8 py-4

**Container Strategy**:
- Max-width: max-w-7xl for main content
- Forms: max-w-2xl centered
- Dashboard content: max-w-6xl with responsive grid

## Component Library

### Navigation
- Sticky header with high contrast
- Large tap targets (minimum 44x44px)
- Clear active states with underline + bold
- Mobile: Full-screen menu with large buttons
- Logout button always visible in header

### Forms
- **Layout**: Single column, full-width fields
- **Field Height**: Minimum 48px (accessibility standard)
- **Labels**: Above fields, bold, with asterisk for required
- **Inputs**: Large, rounded-lg borders, focus ring with 3px outline
- **Error States**: Red border + icon + descriptive text below field
- **Success States**: Green checkmark icon inline
- **Select Dropdowns**: Custom styled with chevron icon, large options
- **Textareas**: Minimum 120px height, auto-grow
- **Submit Buttons**: Full-width on mobile, prominent primary style

### Buttons
- **Primary**: Large (px-8 py-4), bold text, rounded-lg
- **Secondary**: Outlined style with 2px border
- **Icon Buttons**: Square 44x44px minimum with clear icon
- **Disabled State**: Reduced opacity with cursor-not-allowed
- **Focus State**: 3px offset ring for keyboard navigation

### Cards (Need Cards, User Cards)
- Rounded-xl borders with subtle shadow
- Padding: p-6 md:p-8
- Header with title + status badge
- Description with max 3 lines, then "Read more"
- Footer with action buttons and metadata
- Hover: Subtle lift effect (shadow increase)

### Status Badges
- Rounded-full px-4 py-2
- Bold text-sm uppercase
- "Open": Green background
- "In Progress": Blue background  
- "Fulfilled": Gray background
- "Urgent": Red background with pulse animation

### Dashboard Layout
- **Sidebar Navigation** (desktop): Fixed left, width 280px, full-height
  - Profile summary at top with avatar
  - Navigation items with icons (Heroicons)
  - Active state: background highlight + border-left accent
- **Mobile**: Bottom tab bar with 4-5 main actions
- **Content Area**: Responsive grid, cards layout
- **Stats Cards**: 3-column grid showing key metrics (total needs, fulfilled, pending)

### Messaging Interface
- **Conversation List**: Left sidebar (desktop) or separate view (mobile)
- **Message Bubbles**: Rounded-2xl, different alignment for sent/received
- **Input**: Fixed bottom bar with textarea + send button
- **Timestamps**: Subtle text-xs below messages
- **Unread Indicator**: Badge with count

### Needs List/Grid
- **Grid Layout**: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- **Filters**: Sticky top bar with dropdowns for category/urgency
- **Empty State**: Centered illustration placeholder + CTA
- **Pagination**: Simple prev/next buttons at bottom

## Accessibility Features
- **Skip Links**: "Skip to main content" at top
- **Focus Indicators**: Visible 3px rings on all interactive elements
- **ARIA Labels**: Comprehensive labeling for screen readers
- **Keyboard Navigation**: Full tab order, Enter/Space for actions
- **High Contrast Mode**: Tested with Windows high contrast
- **Screen Reader**: Announcements for dynamic content changes
- **Form Validation**: Live regions for errors

## Images
- **Hero Section**: Use compassionate, diverse stock photo showing inclusivity (people helping, community, accessibility)
  - Size: Full-width, height 60vh on desktop, 40vh mobile
  - Overlay: Dark gradient (bottom to top) for text readability
  - CTA buttons on hero: Blurred background (backdrop-blur-md) with semi-transparent background
- **Dashboard**: Small avatar/profile images (rounded-full, 64x64px)
- **Empty States**: Simple illustrative SVGs (not photos)
- **No decorative images**: Every image serves functional purpose

## Responsive Strategy
- **Mobile-First**: Base styles for mobile, scale up
- **Breakpoints**: sm:640px, md:768px, lg:1024px, xl:1280px
- **Touch Targets**: Minimum 44x44px on mobile
- **Typography**: Scales with viewport (text-base to text-lg)
- **Forms**: Stack all fields vertically on mobile

## Animations
**Minimal, Purposeful Only**:
- Page transitions: Simple fade-in (duration-200)
- Button clicks: Subtle scale (scale-95 on active)
- Loading states: Spinner icon rotation
- Status updates: Gentle fade-in for success messages
- **No**: Parallax, complex scroll animations, decorative motion