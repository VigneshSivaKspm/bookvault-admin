# BookVault — Super Admin Panel

A professional, enterprise-grade Super Admin Dashboard for a multi-vendor book marketplace, built with **React 18** + **Tailwind CSS** + **Recharts**.

---

## Tech Stack

- **React 18** — component-based UI
- **Tailwind CSS** — utility-first styling
- **Recharts** — interactive charts
- **Lucide React** — icon library

---

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Start development server

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 3. Build for production

```bash
npm run build
```

---

## Project Structure

```
src/
├── components/
│   ├── Sidebar.jsx        # Collapsible left navigation
│   ├── Header.jsx         # Top bar with search, notifications, avatar
│   ├── MetricCard.jsx     # KPI summary card
│   ├── Badge.jsx          # Status badge (Active, Pending, etc.)
│   └── Avatar.jsx         # Initials avatar with color mapping
├── pages/
│   ├── DashboardPage.jsx  # Overview metrics + 4 charts + recent orders
│   ├── SellersPage.jsx    # Seller list, approve/reject/suspend
│   ├── UsersPage.jsx      # User list, suspend/restore/reset
│   ├── BooksPage.jsx      # Book listings, approve/feature/remove
│   ├── OrdersPage.jsx     # Order tracking + status management
│   ├── CommissionPage.jsx # Global & per-seller commission settings
│   ├── AnalyticsPage.jsx  # Revenue, user growth, genre & seller charts
│   ├── CategoriesPage.jsx # Add/edit/delete book categories
│   ├── ReviewsPage.jsx    # Approve/flag/delete reviews
│   ├── ReportsPage.jsx    # Export reports (PDF, Excel, CSV)
│   ├── NotificationsPage.jsx # Send notifications to users/sellers
│   ├── SettingsPage.jsx   # General, Payment, Marketplace, Security tabs
│   ├── AdminsPage.jsx     # Admin accounts + roles permissions matrix
│   └── LogsPage.jsx       # System audit logs with filters
├── data/
│   └── mockData.js        # All mock data (replace with Firebase calls)
├── hooks/
│   └── useToast.js        # Toast notification context + hook
├── App.jsx                # Root app + page routing
└── index.css              # Tailwind base + custom component classes
```

---

## Firebase Integration

This project uses mock data. To connect Firebase:

1. Install Firebase SDK:
   ```bash
   npm install firebase
   ```

2. Create `src/firebase.js`:
   ```js
   import { initializeApp } from "firebase/app";
   import { getFirestore } from "firebase/firestore";
   import { getAuth } from "firebase/auth";

   const firebaseConfig = {
     apiKey: "YOUR_API_KEY",
     authDomain: "YOUR_AUTH_DOMAIN",
     projectId: "YOUR_PROJECT_ID",
     storageBucket: "YOUR_STORAGE_BUCKET",
     messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
     appId: "YOUR_APP_ID"
   };

   const app = initializeApp(firebaseConfig);
   export const db = getFirestore(app);
   export const auth = getAuth(app);
   ```

3. Replace mock data imports in each page with Firestore `collection()` + `onSnapshot()` calls.

### Firestore Collections

| Collection   | Used In                    |
|-------------|----------------------------|
| `users`     | User Management            |
| `sellers`   | Seller Management          |
| `books`     | Book Management            |
| `orders`    | Order Management           |
| `reviews`   | Reviews & Ratings          |
| `categories`| Categories                 |
| `payments`  | Commission Management      |
| `notifications` | Notifications          |
| `adminLogs` | System Logs                |

---

## Features

- ✅ 14-page admin panel with full navigation
- ✅ Collapsible sidebar with role badges
- ✅ 8 KPI metric cards on dashboard
- ✅ 6 interactive Recharts charts
- ✅ Seller approve/reject/suspend workflow
- ✅ User suspend/restore/password reset
- ✅ Book feature/approve/remove actions
- ✅ Commission — global + per-seller settings
- ✅ Payout history table
- ✅ Report exports (PDF/Excel/CSV buttons)
- ✅ Notification composer with audience targeting
- ✅ Settings — General, Payment, Marketplace, Security tabs
- ✅ Admin management + role permissions matrix
- ✅ System logs with type filters
- ✅ Toast notification system
- ✅ Dark theme throughout
- ✅ Responsive-ready layout

---

## Design System

Colors defined in `tailwind.config.js`:

| Token       | Value     | Usage                    |
|-------------|-----------|--------------------------|
| `navy-900`  | `#0f1117` | Page background          |
| `navy-800`  | `#161b27` | Sidebar, cards           |
| `navy-700`  | `#1e2535` | Input fields, hover      |
| `navy-500`  | `#2a3348` | Borders                  |
| `brand`     | `#4f7cff` | Accent, active states    |

Custom component classes in `src/index.css`: `.metric-card`, `.table-card`, `.badge`, `.btn-primary`, `.btn-action`, `.btn-danger`, `.form-input`, `.nav-item`.
# bookvault-admin
