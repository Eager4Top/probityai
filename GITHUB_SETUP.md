# PROBITY AI Website — GitHub Pages Deployment Guide

## Your Final URLs (after deployment)

Replace `yourusername` with your actual GitHub username everywhere below.

| Page | URL |
|---|---|
| **Home / Landing** | `https://yourusername.github.io/probityai/` |
| **Privacy Policy** | `https://yourusername.github.io/probityai/privacy.html` |
| **Terms & Conditions** | `https://yourusername.github.io/probityai/terms.html` |
| **Data Deletion** | `https://yourusername.github.io/probityai/data-deletion.html` |
| **Cookie Policy** | `https://yourusername.github.io/probityai/cookies.html` |
| **OAuth Success** | `https://yourusername.github.io/probityai/oauth-success.html` |

---

## STEP 1 — Create a GitHub Account (if you don't have one)

1. Go to **https://github.com**
2. Click **Sign up**
3. Enter your email, create a password, choose a username
4. Verify your email address
5. Choose the **Free** plan

---

## STEP 2 — Create the Repository

1. Log into GitHub
2. Click the **"+"** button at the top right → **"New repository"**
3. Fill in the form:
   - **Repository name:** `probityai`
   - **Description:** `PROBITY AI Official Website`
   - **Visibility:** ✅ **Public** (required for free GitHub Pages)
   - **Initialize this repository:** ✅ tick **"Add a README file"**
4. Click **"Create repository"**

---

## STEP 3 — Upload All Website Files

1. Inside your new repository, click **"Add file"** → **"Upload files"**
2. Drag and drop ALL of these files at once:
   - `index.html`
   - `privacy.html`
   - `terms.html`
   - `data-deletion.html`
   - `cookies.html`
   - `oauth-success.html`
3. In the **"Commit changes"** section at the bottom write:
   - Commit message: `Add PROBITY AI website files`
4. Click **"Commit changes"**

---

## STEP 4 — Enable GitHub Pages

1. In your repository, click **"Settings"** (top tab)
2. In the left sidebar scroll down to **"Pages"**
3. Under **"Source"**, select:
   - Branch: **main**
   - Folder: **/ (root)**
4. Click **"Save"**
5. Wait 1–2 minutes
6. Refresh the Settings → Pages page
7. You will see: **"Your site is live at https://yourusername.github.io/probityai/"**

✅ Your website is now live.

---

## STEP 5 — Update Bot Username in oauth-success.html

Before uploading (or after), open `oauth-success.html` and find this line near the top of the `<script>` section:

```javascript
const BOT_USERNAME = 'ProbityAIBot'; // update to your bot username
```

Replace `ProbityAIBot` with your actual Telegram bot username (without the @).

To update after uploading:
1. Click `oauth-success.html` in your repository
2. Click the **pencil icon** (Edit)
3. Find and update the username
4. Click **"Commit changes"**

---

## STEP 6 — Update Your .env File

Now add these URLs to your bot's `.env` file:

```env
WEBHOOK_URL=https://yourserver.com

# ── PROBITY AI Website URLs ──────────────────────────────────────────
PRIVACY_POLICY_URL=https://yourusername.github.io/probityai/privacy.html
TERMS_URL=https://yourusername.github.io/probityai/terms.html
DATA_DELETION_URL=https://yourusername.github.io/probityai/data-deletion.html
```

---

## STEP 7 — Enter URLs in Each Platform's Developer Portal

### Facebook & Instagram (Meta)

| Field | Value |
|---|---|
| **Privacy Policy URL** | `https://yourusername.github.io/probityai/privacy.html` |
| **Terms of Service URL** | `https://yourusername.github.io/probityai/terms.html` |
| **Data Deletion Callback URL** | `https://yourusername.github.io/probityai/data-deletion.html` |
| **OAuth Redirect URI (Facebook)** | `https://yourserver.com/oauth/callback/facebook` |
| **OAuth Redirect URI (Instagram)** | `https://yourserver.com/oauth/callback/instagram` |

Where to enter:
- Privacy Policy & Terms → **App Settings → Basic**
- Data Deletion URL → **App Settings → Basic → Data Deletion Instructions URL**
- OAuth Redirect URIs → **Facebook Login for Business → Settings → Valid OAuth Redirect URIs**

### TikTok

| Field | Value |
|---|---|
| **Privacy Policy URL** | `https://yourusername.github.io/probityai/privacy.html` |
| **Terms of Service URL** | `https://yourusername.github.io/probityai/terms.html` |
| **OAuth Redirect URI** | `https://yourserver.com/oauth/callback/tiktok` |

Where to enter: TikTok Developer Portal → Your App → **Configure**

### X (Twitter)

| Field | Value |
|---|---|
| **Privacy Policy URL** | `https://yourusername.github.io/probityai/privacy.html` |
| **Terms of Service URL** | `https://yourusername.github.io/probityai/terms.html` |
| **Callback URI / Redirect URL** | `https://yourserver.com/oauth/callback/x` |

Where to enter: X Developer Portal → Your App → **User Authentication Settings → Edit**

---

## STEP 8 — Test Your Live Pages

Open each URL and confirm it loads correctly:

- [ ] `https://yourusername.github.io/probityai/` — Home page loads
- [ ] `https://yourusername.github.io/probityai/privacy.html` — Privacy policy loads
- [ ] `https://yourusername.github.io/probityai/terms.html` — Terms load
- [ ] `https://yourusername.github.io/probityai/data-deletion.html` — Deletion page loads
- [ ] `https://yourusername.github.io/probityai/cookies.html` — Cookie policy loads
- [ ] `https://yourusername.github.io/probityai/oauth-success.html?ok=1&platform=facebook&handle=testpage` — OAuth success page shows ✅

---

## How to Update Any Page Later

1. Go to your GitHub repository
2. Click the file you want to edit
3. Click the **pencil icon** (Edit this file)
4. Make your changes
5. Click **"Commit changes"**
6. Changes go live within 1–2 minutes automatically

---

## Troubleshooting

| Problem | Solution |
|---|---|
| Site shows 404 | Make sure `index.html` is uploaded (not in a subfolder) and Pages is enabled |
| Pages not enabled | Go to Settings → Pages → make sure Branch is set to `main` |
| Old version still showing | GitHub Pages caches for a few minutes — wait 2–3 minutes and hard-refresh (Ctrl+Shift+R) |
| Meta rejects Privacy Policy URL | Make sure the URL is publicly accessible and returns HTTP 200 — test in an incognito window |
| Meta rejects Data Deletion URL | The URL must be publicly accessible. Use the exact URL: `https://yourusername.github.io/probityai/data-deletion.html` |

---

## Summary of All URLs to Copy

Once deployed, copy these and keep them handy for all platform registrations:

```
Home:           https://yourusername.github.io/probityai/
Privacy Policy: https://yourusername.github.io/probityai/privacy.html
Terms:          https://yourusername.github.io/probityai/terms.html
Data Deletion:  https://yourusername.github.io/probityai/data-deletion.html
Cookies:        https://yourusername.github.io/probityai/cookies.html

OAuth Callbacks (on your BOT SERVER, not GitHub):
Facebook:   https://yourserver.com/oauth/callback/facebook
Instagram:  https://yourserver.com/oauth/callback/instagram
TikTok:     https://yourserver.com/oauth/callback/tiktok
X:          https://yourserver.com/oauth/callback/x
```
