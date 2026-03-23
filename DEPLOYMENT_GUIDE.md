# WELB Solutions — Deployment Guide
## Get your system live in ~10 minutes

---

## STEP 1 — Set up Firebase (free database)

1. Go to **https://console.firebase.google.com**
2. Click **"Add project"** → Name it `welb-solutions` → Click through the steps
3. On the left menu click **Firestore Database** → **Create database** → choose **"Start in test mode"** → pick region **"europe-west1"** (closest to Kenya) → **Enable**
4. On the left menu click the **gear icon ⚙ → Project settings**
5. Scroll down to **"Your apps"** → click the **Web icon (</>)**
6. Register app name: `welb-web` → click **Register app**
7. You will see a config block like this:

```js
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "welb-solutions.firebaseapp.com",
  projectId: "welb-solutions",
  storageBucket: "welb-solutions.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

8. **Copy all those values** — you will need them in Step 3.

---

## STEP 2 — Upload to GitHub

1. Go to **https://github.com** and log into your account
2. Click the **"+"** button (top right) → **"New repository"**
3. Name it: `welb-solutions`
4. Make it **Public** (required for free Netlify hosting)
5. Click **"Create repository"**
6. On the next screen, click **"uploading an existing file"**
7. Drag and drop the `index.html` file from this folder
8. Click **"Commit changes"**

---

## STEP 3 — Add your Firebase config to index.html

Before or after uploading, open `index.html` in a text editor (Notepad is fine).

Find this section near the bottom of the file:

```js
const FIREBASE_CONFIG = {
  apiKey: "REPLACE_WITH_YOUR_API_KEY",
  authDomain: "REPLACE_WITH_YOUR_AUTH_DOMAIN",
  projectId: "REPLACE_WITH_YOUR_PROJECT_ID",
  storageBucket: "REPLACE_WITH_YOUR_STORAGE_BUCKET",
  messagingSenderId: "REPLACE_WITH_YOUR_MESSAGING_SENDER_ID",
  appId: "REPLACE_WITH_YOUR_APP_ID"
};
```

Replace each `REPLACE_WITH_...` value with the actual values from your Firebase project settings.

Save the file and re-upload it to GitHub if you already uploaded.

---

## STEP 4 — Deploy on Netlify (free hosting)

1. Go to **https://netlify.com** → click **"Sign up"** → sign up **with your GitHub account**
2. Click **"Add new site"** → **"Import an existing project"**
3. Click **"Deploy with GitHub"** → authorize Netlify
4. Select your `welb-solutions` repository
5. Leave all settings as default → click **"Deploy site"**
6. Wait ~30 seconds — Netlify will give you a URL like:
   `https://welb-solutions-abc123.netlify.app`

**That is your live link!** Share it with your co-founders for testing.

---

## STEP 5 — Change your password (important!)

1. Open your live site
2. Log in with: **Username:** `admin` / **Password:** `welb2024`
3. Go to **Settings** in the sidebar
4. Enter a new strong password
5. Click **Save Settings**

---

## Sharing with co-founders (2–3 testers)

- Share the Netlify URL with them
- Give them the login credentials
- All data they enter will be saved to the same Firebase database in real time
- Everyone sees the same data

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| "Offline mode" shown at bottom | Firebase config not set correctly — re-check Step 3 |
| Can't log in | Use `admin` / `welb2024` (default credentials) |
| Data not saving | Check Firebase Firestore rules are in "test mode" |
| Site not loading | Check GitHub file uploaded correctly |

---

## Later upgrades (when ready)

- Custom domain (e.g. `system.welbsolutions.co.ke`) — KES ~1,500/year
- SMS notifications for loan reminders
- M-Pesa payment integration
- PDF loan statements
- Multiple user accounts with different roles

---

*System built for WELB Solutions Microfinance Ltd — March 2026*
