# SlotSafe 🛡️

**Your Appointments. Protected. Automatically.**

SlotSafe is a WhatsApp-first no-show prevention SaaS for Indian salons, clinics, and studios. It automatically sends confirmation reminders, handles reschedules, and fills cancelled slots from a waitlist — all via WhatsApp, with SMS fallback.

---

## 📁 File Structure

```
├── index.html       — Public marketing landing page
├── login.html       — Auth page (Login + Sign Up)
├── dashboard.html   — User dashboard (post-login)
├── pricing.html     — Pricing & upgrade page (Razorpay checkout)
└── admin.html       — Internal admin panel (owner/ops use)
```

---

## 🖥️ Pages Overview

### `index.html` — Landing Page
The public-facing marketing site. Includes:
- Hero section with animated WhatsApp phone mockup
- Stats strip (social proof numbers)
- Pain points section (cost of no-shows)
- How it Works (4-step explainer)
- Feature cards
- ROI Calculator (interactive sliders, INR-formatted output)
- Testimonials
- Pricing preview
- FAQ accordion
- Full footer with links

### `login.html` — Authentication
- Toggle tabs: **Log In** / **Sign Up**
- Email + password fields
- Google Sign-In button
- Error/success message banners
- Links to `dashboard.html` on success

### `dashboard.html` — User Dashboard
Post-login interface for business owners. Includes:
- Fixed sidebar navigation
- Stats cards: appointments today, no-shows prevented, revenue saved, next appointment
- Appointments table with status badges and action buttons (Confirm, Reschedule, Cancel)
- WhatsApp message log panel
- Waitlist management tab
- Settings panel (WhatsApp number, business name, reminder timing)

### `pricing.html` — Plans & Billing
Upgrade flow for existing users. Includes:
- Monthly/Yearly billing toggle (with discount labels)
- Three plan cards: **Starter**, **Pro** (featured), **Studio**
- Full feature comparison table
- Razorpay payment modal with GST breakdown (18%)
- Success overlay on payment completion

### `admin.html` — Admin Panel
Internal-only panel for the SlotSafe team. Includes:
- User management table (all accounts, plan, status)
- Platform-wide stats (MRR, active users, churn)
- Broadcast message tool
- Feature flags / kill switches

---

## 💳 Pricing

| Plan | Monthly | Yearly | Appointments/week | Staff |
|------|---------|--------|-------------------|-------|
| Starter | ₹999 | ₹832/mo | 20 | 1 |
| **Pro** ⭐ | **₹1,999** | **₹1,666/mo** | **60** | **3** |
| Studio | ₹3,999 | ₹3,332/mo | 150 | Unlimited |

All plans include: WhatsApp confirmation bot, SMS fallback, waitlist recovery, and monthly ROI report.

---

## 🔧 Tech Stack & Integrations

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML/CSS/JS (single-file pages) |
| Fonts | Google Fonts — Syne (headings) + DM Sans (body) |
| Auth & DB | Firebase (Auth + Firestore) |
| Payments | Razorpay (UPI, Cards, Net Banking, Wallets) |
| Messaging | WhatsApp Business API + SMS fallback |
| Hosting | Any static host (Vercel, Netlify, Firebase Hosting) |

---

## ⚙️ Setup Instructions

### 1. Firebase
Replace the placeholder config in `login.html`, `dashboard.html`, `pricing.html`, and `admin.html`:

```js
const FIREBASE_CONFIG = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

Enable **Email/Password** and **Google** sign-in methods in your Firebase Console under Authentication.

### 2. Razorpay
Replace the test key in `pricing.html`:

```js
const RAZORPAY_KEY = "rzp_test_YOUR_KEY_HERE";
// Switch to rzp_live_... for production
```

Create a Razorpay account at [razorpay.com](https://razorpay.com) and generate your API keys.

### 3. WhatsApp Business Number
Update the support/CTA WhatsApp number across all pages (currently `919999999999`):

```
Search: wa.me/919999999999
Replace with: wa.me/91XXXXXXXXXX
```

### 4. Admin Access
`admin.html` has no built-in auth gate in the frontend — **protect this route at the server/hosting level** (e.g., Netlify password protection, Firebase Hosting rewrites, or an IP allowlist) before going live.

---

## 🚀 Deployment

These are static HTML files — no build step required.

**Vercel (recommended):**
```bash
# Just drag-and-drop the folder at vercel.com/new
# or use CLI:
npx vercel
```

**Firebase Hosting:**
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

**Netlify:**
Drag the project folder into [app.netlify.com/drop](https://app.netlify.com/drop).

---

## 📋 Pre-Launch Checklist

- [ ] Replace all Firebase config placeholders
- [ ] Replace Razorpay test key with live key
- [ ] Update WhatsApp number (`919999999999` → your number)
- [ ] Add real testimonial names/photos
- [ ] Update stat numbers on landing page to reflect real data
- [ ] Protect `admin.html` behind server-level auth
- [ ] Add real Privacy Policy, Terms of Service, and Refund Policy pages
- [ ] Enable GST invoice generation for Indian compliance
- [ ] Test Razorpay payment flow end-to-end in test mode before going live

---

## 🎨 Design System

| Token | Value |
|-------|-------|
| Primary green | `#00e87a` |
| Background | `#0a0a0a` |
| Card | `#141414` |
| Border | `#1e1e1e` |
| Muted text | `#666` / `#999` |
| Danger | `#ff4d4d` |
| WhatsApp green | `#25D366` |

---

## 📞 Support

For setup help, WhatsApp: [wa.me/919999999999](https://wa.me/919999999999)

---

*© 2025 SlotSafe. Made with 💚 in India.*

