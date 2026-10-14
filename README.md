# TrailSync India — Frontend Client (`travel-fe`)

Modern, high-performance React 18 + Vite frontend for **TrailSync India**, an Indian Group Travel Marketplace and Operator B2B SaaS platform.

---

## 🌟 Key Features

### 🔐 Role-Based Authentication & Portal Routing
Dynamic multi-portal interface automatically rendering customized workspaces based on `user.role`:
- **🎒 Traveler Marketplace Portal (`TRAVELER`)**:
  - `Discover & Compare`: Search trips, category filters, interactive itinerary & review drawer, 3-way side-by-side trip comparison, instant batch checkout, and full-batch waitlisting.
  - `Vibe Matcher™ (Model B)`: 5-dimensional traveler personality vector assessment (cosine similarity match against departure batch rosters).
  - `Verified Operators`: Browse verified operator profiles with Trust Scores and apply to become an operator.
  - `My Bookings & Safety`: Instant booking cancellation with automated refund slab calculation, verified 4-dimension reviews, and 24x7 Safety SOS triggering automatic operator escrow freezing.
- **📊 Operator B2B SaaS Console (`OPERATOR`)**:
  - `Live Batches & Manifests`: Real-time seat inventory, offline Instagram/WhatsApp +1 seat sync, passenger manifest drawer with dynamic CSV export, waitlist inspection, and operator batch cancellation (100% traveler refund + trust penalty).
  - `My Trip Catalogue`: Multi-day itinerary creator, departure batch scheduler, and trip status toggle (`ACTIVE` / `PAUSED`).
  - `Bookings & Custom Quotes`: Verify manual UPI reference numbers and send custom B2B quotes.
  - `Trust Audit & Incidents`: Audit logs for weighted Trust Scores, review replies, and official safety incident explanations.
  - `Operator Profile`: Support SLA and KYC profile configuration.
- **🏛️ Admin Governance & Escrow Console (`ADMIN`)**:
  - `Unit Economics`: Real-time GMV, 10% platform commission, 2% gateway fee, and net contribution margin tracking.
  - `Operator KYC Audit`: Approve/reject operator KYC applications and inspect audit histories.
  - `Escrow Payouts (UTR)`: Milestone-based payout settlement by inputting bank UTR references.
  - `Safety Incidents`: Investigate and resolve emergency SOS safety incidents to unfreeze escrow.

---

## 🛠️ Tech Stack

- **Framework**: React 18
- **Build Tool**: Vite
- **Icons**: Lucide Icons (`lucide-react`)
- **Styling**: Modern CSS Design System (Glassmorphic cards, responsive CSS grid, role-themed palettes)
- **API Client**: Native `fetch` with centralized JWT token management and error handling

---

## 🚀 Getting Started

### 1. Installation
```bash
git clone https://github.com/tanishkgupta20012004-sketch/travel-fe.git
cd travel-fe
npm install
```

### 2. Configure Backend Proxy
The Vite development server is configured in `vite.config.js` to proxy `/api` requests to `http://127.0.0.1:5000`:
```javascript
export default defineConfig({
  plugins: [react()],
  server: {
    port: 5173,
    host: true,
    proxy: {
      '/api': {
        target: 'http://127.0.0.1:5000',
        changeOrigin: true
      }
    }
  }
});
```

### 3. Start Development Server
```bash
npm run dev
```
Open **http://localhost:5173** in your browser.

---

## 🔐 Demo Credentials (Seeded)

All demo accounts share the password: `Password@123`

| Role | Name | Email | Phone | Password |
| :--- | :--- | :--- | :--- | :--- |
| **Traveler** | Aarav Verma | `aarav@example.com` | `9000000005` | `Password@123` |
| **Traveler** | Priya Nair | `priya@example.com` | `9000000006` | `Password@123` |
| **Operator (Verified)** | Vikram Singh (*Malwa Trails*) | `vikram@malwatrails.in` | `9000000003` | `Password@123` |
| **Operator (Verified)** | Rohan Mehta (*Himalayan Nomads*) | `rohan@himalayannomads.in` | `9000000002` | `Password@123` |
| **Admin** | Platform Admin | `admin@tourmarketplace.in` | `9000000001` | `Password@123` |
