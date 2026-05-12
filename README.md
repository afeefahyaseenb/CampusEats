[README.md](https://github.com/user-attachments/files/27623575/README.md)
# CampusEats# CampusEats — eCanteen v4

> A smart campus canteen ordering web app for Parul University Goa. Order ahead, skip the queue, track your food live, and earn green points — all from a single-page interface.

---

## Overview

CampusEats is a fully self-contained, single-file HTML web application that simulates a modern digital canteen system. It is designed for a university campus environment and supports three user roles: **Students**, **Staff**, and **Admins** — each with tailored access and features.

---

## Features

### For Students & Staff
- **Browse & Order** — Explore a filterable menu of canteen items with prices, ratings, and stall info
- **Live Queue Tracker** — View real-time queue lengths across all stalls before ordering
- **Cart & Checkout** — Add items, adjust quantities, apply promo codes, and place orders
- **Payment Options** — Choose to pay via UPI, Cash, or Card; pay before or after receiving
- **Order Token System** — Receive an animated token card with order ID, estimated wait time, countdown timer, and a QR code for counter verification
- **Live Order Tracking** — Track order progress through stages: Received → Preparing → Cooking → Ready → Completed
- **Order Cancellation** — Cancel within a 2-minute window with automatic refund initiation
- **AI Calorie Scanner** — Upload a food photo or use the live camera to get AI-predicted nutritional info (calories, protein, carbs, fat)
- **Green Points** — Earn loyalty points with each order; view balance via a premium animated token card
- **Featured Carousel** — Horizontally swipeable hero banner showcasing today's top dishes
- **Trending Marquee** — Auto-scrolling strip of popular menu items

### For Admins
- **Admin Dashboard** — Real-time overview of all orders with live stats (total, pending, ready, completed)
- **Order Management** — Search and filter orders; update order status through the kitchen workflow
- **Staff Panel** — Dedicated view for canteen staff to manage their stall orders

### General
- **Auth System** — Sign up / Sign in modal with role selection (Student / Staff / Admin), password strength meter, and field validation
- **Search & Filter** — Search menu items by name; filter by category tags
- **Toast Notifications** — Lightweight feedback toasts for all user actions
- **Responsive Design** — Adapts gracefully to mobile and tablet viewports
- **Custom Cursor** — Branded red dot + ring cursor for desktop

---

## Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 (single file) |
| Styling | CSS3 — custom properties, glassmorphism, keyframe animations |
| Logic | Vanilla JavaScript (ES6+) |
| Fonts | Google Fonts — Syne, DM Sans |
| Images | Unsplash (CDN, no download needed) |
| Camera API | MediaDevices `getUserMedia` (for AI calorie scanner) |
| Storage | Browser `localStorage` (orders, auth state, cart) |

No build tools, no frameworks, no dependencies to install.

---

## User Roles

| Role | Access |
|---|---|
| **Student** | Browse menu, place orders, track tokens, earn green points |
| **Staff** | Same as Student + dedicated staff order panel |
| **Admin** | All of the above + Admin Dashboard with order management |

Demo credentials are handled client-side. Sign up with any email to get started; select **Admin** during signup for full dashboard access.

---

## Getting Started

1. Download `ecanteen_v4.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. No server, no install, no dependencies required

```
open ecanteen_v4.html
```

For the AI Camera Calorie Scanner, the browser will request camera permissions. This feature requires HTTPS or `localhost` in most browsers due to MediaDevices API restrictions.

---

## Project Structure

All code lives inside a single HTML file, organized into clearly commented sections:

```
ecanteen_v4.html
│
├── <head>               — Meta, fonts, CSS custom properties
├── <style>              — All styles (CSS variables, components, animations)
│   ├── Modal / Auth
│   ├── Navigation
│   ├── Hero & Sections
│   ├── Queue Cards
│   ├── Menu & Cart
│   ├── Token Tracking System
│   ├── AI Calorie Calculator
│   ├── Admin Dashboard
│   └── Responsive breakpoints
│
├── <body> (HTML)
│   ├── Auth Modal
│   ├── Cancel Confirmation Popup
│   ├── Navigation Bar
│   ├── Hero Section
│   ├── Featured Carousel
│   ├── Trending Marquee
│   ├── Search Bar
│   ├── Live Queue Section
│   ├── Menu Page (tab-switched)
│   ├── Features Section
│   ├── AI Tools Section (Calorie Scanner)
│   ├── Green Points Section
│   ├── Testimonials
│   ├── Footer
│   ├── Cart Drawer
│   ├── Payment Modal
│   ├── Token Card Overlay
│   ├── Order Tracking Modal
│   ├── Ready for Pickup Popup
│   ├── Admin Dashboard
│   └── AI Camera Modal
│
└── <script>             — All JavaScript logic
    ├── Auth & Session Management
    ├── Menu Rendering & Filtering
    ├── Cart Logic
    ├── Order Placement & Token Generation
    ├── Order Status Simulation (countdown, progress)
    ├── Admin Order Management
    ├── AI Calorie Scanner (keyword match + camera)
    ├── Tab Navigation
    └── UI Helpers (toasts, scroll reveals, cursor)
```

---

## Key Modules

### Token System
When an order is placed, a unique token is generated (format: `EC####`). A full-screen animated token card is shown with a live countdown timer, step-by-step progress tracker, and a QR code. Orders can be cancelled within the first 2 minutes.

### AI Calorie Scanner
Users can upload a food photo or use the live camera. The scanner matches the filename against a keyword database to identify the food item and display estimated nutritional data (calories, protein, carbs, fat) along with a health tip. Unknown foods fall back to a random prediction displayed as "Demo Mode."

### Admin Dashboard
Visible only to admin-role users after login. Displays all placed orders in a filterable grid with controls to advance order status. Live stat counters update on each status change.

### Green Points
Each order earns the user points proportional to order value. Balances are stored in `localStorage` and displayed in the nav and a dedicated section.

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 15+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Mobile browsers | ✅ Responsive |

Camera features require HTTPS or localhost.

---

## Notes

- All data (orders, users, cart) is stored in **browser localStorage** and resets on clearing site data.
- Menu items, stall data, and order history are seeded with mock data for demonstration.
- The AI food recognition is keyword-based and uses randomized fallback — it is a UI/UX prototype, not a real ML model.
- Payment flow is simulated; no real transactions occur.

---

## License

This project is a student/academic prototype. All food images are sourced from [Unsplash](https://unsplash.com) under their free-to-use license.
