# UI/UX Plan & Screen Specification

## Screen Hierarchy & Routes
- `/` — Homepage / Featured listings showcase
- `/properties` — Search & Filter view
- `/properties/[id]` — Detail view with booking form
- `/dashboard/owner` — Owner property listings & earnings
- `/dashboard/renter` — My bookings & rental history
- `/admin` — System management & subscription metrics

## UI Design Tokens
- **Font Family**: Inter, sans-serif
- **Color Tokens**:
  - Primary: `hsl(222, 47%, 11%)`
  - Secondary: `hsl(217, 91%, 60%)`
  - Background: `hsl(210, 40%, 98%)`
  - Surface: `hsl(0, 0%, 100%)`
  - Accent: `hsl(142, 76%, 36%)`

## Five UI States Specification
Each page component MUST handle:
1. `DEFAULT`: Content grid populated.
2. `LOADING`: Skeleton loader grid.
3. `EMPTY`: Centered empty state illustration + "Add Property" button.
4. `ERROR`: Red banner error card + "Retry" button.
5. `DISABLED`: Submit buttons disabled during network mutation.
