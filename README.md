
# ♛ FlavorShare — The Grand Culinary Portal

> A prestigious, community-driven recipe sharing web portal with Firebase backend, admin approval workflow, and LMS Academy — built with pure HTML5, CSS3, and Vanilla JavaScript.

---

## 📌 Project Info

| Field | Details |
|---|---|
| **Project Name** | FlavorShare — The Grand Culinary Portal |
| **Course** | AI23431 – Web Technology and Mobile Application |
| **Student** | SRI DURGA R |
| **Roll Number** | 241801273 |
| **Register Number** | 2116241801273 |
| **Department** | Artificial Intelligence and Data Science |
| **College** | Rajalakshmi Engineering College (Autonomous), Chennai – 602 105 |
| **Year** | 2026 |

---

## 📁 Project Structure
FlavorShare/
│
├── gateway.html          →  Landing page — choose User or Admin path
├── user-auth.html        →  User Sign Up / Sign In with Firebase Phone OTP
├── index.html            →  Public recipe discovery portal
├── submit-recipe.html    →  User recipe submission form
├── academy.html          →  LMS Academy — browse & enroll in courses
├── admin-dashboard.html  →  Admin control panel (approval queue + LMS)
│
├── styles.css            →  All shared styles (Dark & Gold luxury theme)
├── app.js                →  Shared logic — Auth, Recipes, Store, helpers
│
└── README.md             →  This file



---

## 🚀 How to Run

No installation. No server. No npm. Just open in a browser.
Download / clone the project folder
Open gateway.html in Google Chrome (or any modern browser)
That's it — the app runs fully client-side


> **Tip:** All pages must be in the **same folder** so they can share `styles.css` and `app.js`.

---

## 🔑 Login Credentials

### 👨‍🍳 User (Chef) Access
- Click **"Enter as Chef"** on the gateway page
- Click **Sign Up** → fill your name, email, password, phone
- OTP is sent via Firebase (see Firebase setup below)
- In **demo mode** (default), OTP is skipped automatically

### 👑 Admin Access
- Click **"Admin Access"** on the gateway page
- Select an admin identity from the dropdown:

| Admin Name | ID |
|---|---|
| Chef Marco Rossini | admin_marco |
| Chef Sofia Laurent | admin_sofia |
| Chef Arjun Menon | admin_arjun |

- **Secret Password:** `chef2026`

---

## 🔥 Firebase Setup (for real OTP)

By default the project runs in **demo mode** — no Firebase needed, OTP is auto-skipped.

To enable **real Firebase Phone OTP**:

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project → name it `FlavorShare`
3. Go to **Authentication** → Enable **Phone** sign-in method
4. Go to **Project Settings → Your apps → Web app** → Copy config
5. Open `user-auth.html` and replace the `firebaseConfig` block:

```javascript
const firebaseConfig = {
  apiKey:            "YOUR_API_KEY",
  authDomain:        "YOUR_PROJECT_ID.firebaseapp.com",
  projectId:         "YOUR_PROJECT_ID",
  storageBucket:     "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId:             "YOUR_APP_ID"
};
```

6. Add your domain to **Authorized Domains** in Firebase Console → Authentication → Settings

> **Free tier:** Firebase allows ~10,000 OTP SMS per month — more than enough for a university project.

---

## ✨ Features

### 👨‍🍳 User (Chef) Features
- ✅ Sign Up with name, email, password + Firebase Phone OTP verification
- ✅ Earn **5 Chef Stars** as a welcome bonus on joining
- ✅ Browse curated recipes with real-time search and cuisine filters
- ✅ View full recipe details — ingredients, step-by-step instructions
- ✅ Rate recipes with a 1–5 star rating (one rating per user per recipe)
- ✅ Submit your own recipe (name, ingredients, steps, image URL)
- ✅ Earn **+10 Chef Stars** when your recipe is approved by an admin
- ✅ Enroll in professional cooking courses in the LMS Academy
- ✅ Sticky navbar with live star count display
- ✅ Logout anytime — returns to gateway

### 👑 Admin Features
- ✅ Secure login with dropdown identity + secret password
- ✅ Overview dashboard with live stats (recipes, pending, users, courses, stars)
- ✅ **Pending Queue** — review submitted recipes with expandable ingredients and steps
- ✅ One-click **Approve** → recipe goes live + chef earns +10 stars
- ✅ One-click **Reject** → recipe permanently removed
- ✅ View all approved recipes in a gallery
- ✅ **User Management** table — see all chefs, their star counts, and join dates
- ✅ **LMS Management** — publish, edit, and delete professional cooking courses
- ✅ Sidebar navigation with hash-based routing

### 🎓 LMS Academy Features
- ✅ Course grid with level badges (Beginner / Intermediate / Advanced)
- ✅ Enroll in courses — progress saved per user
- ✅ Course detail modal with full lesson curriculum
- ✅ 3 sample courses pre-loaded on first launch

---

## 🗄️ Data Storage

All data is stored in the browser's **localStorage** — no database setup needed.

| localStorage Key | What It Stores |
|---|---|
| `fs_users` | Array of registered user objects |
| `fs_current_user` | Currently logged-in user session |
| `fs_recipes` | Array of approved recipes |
| `fs_pending_recipes` | Array of recipes awaiting admin approval |
| `fs_ratings` | Object map of recipeId_userId to star value |
| `fs_courses` | Array of LMS courses |
| `fs_admin_session` | Currently logged-in admin session |

> To reset all data: **DevTools → Application → Local Storage → Clear All**

---

## 🎨 Design System

| Element | Value |
|---|---|
| **Theme** | Luxury Dark & Gold |
| **Background** | #0F0F0F |
| **Gold Accent** | #C5A059 |
| **Heading Font** | Cinzel (Google Fonts) |
| **Body Font** | Montserrat (Google Fonts) |
| **Image Ratio** | 16:9 for heroes, 4:3 for cards with object-fit: cover |
| **Animations** | fadeInUp, orbFloat, crownGlow, shimmer |

---

## 📄 Pages Overview

| Page | File | Access |
|---|---|---|
| Gateway | gateway.html | Public |
| User Auth | user-auth.html | Public |
| Home / Recipes | index.html | Public (rating requires login) |
| Submit Recipe | submit-recipe.html | Logged-in users only |
| Academy | academy.html | Public (enroll requires login) |
| Admin Dashboard | admin-dashboard.html | Admin only |

---

## 🧪 Sample Data (Auto-loaded)

**6 Approved Recipes:**
Hyderabadi Dum Biryani · Masala Dosa · Classic Beef Steak · Butter Chicken · Tiramisu · Pad Thai

**3 LMS Courses:**
Knife Skills Masterclass · The Art of French Sauces · Indian Spice Alchemy

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 — semantic, multi-page |
| Styling | CSS3 — custom properties, grid, flexbox, keyframe animations |
| Logic | Vanilla JavaScript ES6+ — no frameworks, no build tools |
| Fonts | Google Fonts CDN (Cinzel + Montserrat) |
| Auth / OTP | Firebase JS SDK v10.7.1 (optional, demo mode available) |
| Storage | Browser localStorage API |
| Images | Unsplash CDN URLs |

---

## 🌐 Browser Support

| Browser | Supported |
|---|---|
| Google Chrome 90+ | ✅ |
| Mozilla Firefox 88+ | ✅ |
| Microsoft Edge 90+ | ✅ |
| Safari 14+ | ✅ |
| Internet Explorer | ❌ |

---

## 🌍 SDG Alignment

| SDG | Goal | How FlavorShare Contributes |
|---|---|---|
| SDG 4 | Quality Education | LMS Academy provides free professional culinary courses |
| SDG 8 | Decent Work and Economic Growth | Empowers food entrepreneurs to share and grow |
| SDG 9 | Industry, Innovation and Infrastructure | Uses modern web APIs and Firebase cloud infrastructure |
| SDG 17 | Partnerships for the Goals | Integrates Firebase, Google Fonts, and Unsplash partnerships |

---

## 🧑‍💻 How to Test End-to-End
Open gateway.html in Chrome
USER FLOW: → Click "Enter as Chef" → Sign Up with any name, email, password → You receive 5 ⭐ Stars — check the navbar → Browse recipes on index.html → Click a recipe → rate it with stars → Go to submit-recipe.html → submit a recipe → Go to academy.html → enroll in a course
ADMIN FLOW (open a new tab): → Open gateway.html → Click "Admin Access" → Select any admin name → Password: chef2026 → Go to Pending Queue → see your submitted recipe → Click Approve → check that it appears on index.html → User star count goes up to 15 ⭐ → Go to LMS → add a new course → check academy.html
LOGOUT: → Click Logout on navbar → returns to gateway.html


---

## 📞 Contact

**SRI DURGA R**
Department of Artificial Intelligence and Data Science
Rajalakshmi Engineering College (Autonomous), Chennai – 602 105
Roll No: 241801273  |  Reg No: 2116241801273

---

> *"Where world-class recipes are discovered, crafted, and celebrated."*
>
> **♛ FlavorShare — The Grand Culinary Portal**
