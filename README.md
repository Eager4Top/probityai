<div align="center">

<img src="1774358514997.jpg" alt="PROBITY AI Logo" width="180"/>

# PROBITY AI

### Decentralized Ads & Rewards — Blockchain-Powered Social Media Advertising

[![Telegram Bot](https://img.shields.io/badge/Telegram%20Bot-@Probityads__Bot-blue?logo=telegram&logoColor=white)](https://t.me/Probityads_Bot)
[![Website](https://img.shields.io/badge/Website-Live-brightgreen)](https://yourusername.github.io/probityai/)
[![Privacy Policy](https://img.shields.io/badge/Privacy-Policy-informational)](https://yourusername.github.io/probityai/privacy.html)
[![License](https://img.shields.io/badge/License-Private-red)]()
[![Node.js](https://img.shields.io/badge/Node.js-22%2B-339933?logo=nodedotjs)](https://nodejs.org/)
[![TON Network](https://img.shields.io/badge/Blockchain-TON%20Network-0088CC)](https://ton.org/)

**[Open Bot](https://t.me/Probityads_Bot) · [Privacy Policy](https://yourusername.github.io/probityai/privacy.html) · [Terms](https://yourusername.github.io/probityai/terms.html) · [Data Deletion](https://yourusername.github.io/probityai/data-deletion.html)**

</div>

---

## What is PROBITY AI?

PROBITY AI is a blockchain-powered social media advertising platform built on the **TON Network**. It connects **Merchants** who want to advertise their products with **Promoters** who have social media followings and want to earn **USDT rewards** by posting ads.

Everything runs through a **Telegram bot** (`@Probityads_Bot`). No separate app needed.

```
Merchant creates an ad  →  AI generates/distributes it  →  Promoter posts with one tap  →  USDT credited automatically
```

---

## Key Features

| Feature | Description |
|---|---|
| 🤖 **AI Ad Generation** | Generate Text, Image, Video and Audio ads using AI from a simple product description |
| 📱 **Multi-Platform Posting** | Auto-post to Facebook, Instagram, TikTok, X, Telegram, WhatsApp |
| 🔐 **OAuth Verification** | Secure handle verification via each platform's official OAuth 2.0 flow — no passwords collected |
| 💰 **USDT Rewards** | Promoters earn USDT per verified post, paid on the TON Network |
| ⚡ **Auto-Post** | One tap posts the ad to all verified social handles simultaneously |
| 🔗 **Referral System** | Earn USDT bonuses for every Merchant or Promoter you refer |
| 💸 **Instant Withdrawals** | Withdraw earnings to any TON wallet at any time |
| 👑 **MasterBot Dashboard** | Full admin control — approve ads, manage users, process withdrawals |

---

## How It Works

### For Promoters (Earn USDT)

```
1. Register on @Probityads_Bot
2. Connect your social media handles (Facebook, Instagram, TikTok, X, Telegram, WhatsApp)
3. Handles verified automatically via OAuth — no bio editing, no passwords
4. Browse available ads in the bot
5. Tap "Post Ad" — ad is published to your social media automatically
6. Earn USDT per verified post (up to 9 posts/day)
7. Withdraw to your TON wallet anytime
```

### For Merchants (Advertise)

```
1. Register on @Probityads_Bot as Merchant
2. Add your product
3. Purchase an Ads Bundle (Text / Image / Video)
4. Generate an AI-powered ad or upload your own
5. Ad is automatically distributed to eligible Promoters
6. Pay only per verified post — no wasted spend
7. Track performance in real time
```

---

## Supported Social Media Platforms

| Platform | Verification | Auto-Post | Method |
|---|---|---|---|
| 📘 **Facebook** | ✅ OAuth 2.0 | ✅ Graph API `/me/feed` | Facebook Login for Business |
| 📸 **Instagram** | ✅ OAuth 2.0 | ✅ Content Publishing API | Meta Facebook App |
| 🎵 **TikTok** | ✅ OAuth 2.0 | ✅ Content Posting API | TikTok Developer App |
| 🐦 **X (Twitter)** | ✅ OAuth 2.0 | ✅ v2 Tweets API | X Developer App |
| ✈️ **Telegram** | ✅ Bot Admin Check | ✅ Bot API sendMessage | Bot Token only |
| 💬 **WhatsApp** | ✅ Manual Confirm | ❌ Manual only | Confirmation message |

---

## Tech Stack

| Component | Technology |
|---|---|
| **Bot Framework** | Node.js 22 + `node-telegram-bot-api` |
| **Database** | SQLite (via `better-sqlite3`) |
| **Blockchain** | TON Network — USDT Jetton payments |
| **AI Generation** | AI service (text, image, video, audio) |
| **Authentication** | OAuth 2.0 (per platform) + HMAC-SHA256 state signing |
| **Encryption** | AES-256-GCM for all stored tokens and credentials |
| **Transport** | Webhook (production) with polling fallback (dev) |
| **Website** | Static HTML — GitHub Pages hosted |

---

## Project Structure

```
probityai/
├── src/
│   ├── index.js                    # Bot entry point, webhook server, all callback routing
│   ├── handlers/
│   │   ├── promoter.js             # Promoter flows: handles, verification, ad posting, rewards
│   │   ├── merchant.js             # Merchant flows: products, AI ad gen, bundles, distribution
│   │   ├── masterbot.js            # Admin dashboard: user management, ad approval, withdrawals
│   │   ├── registration.js         # User registration flow (Merchant / Promoter)
│   │   └── support.js              # Support ticket system
│   ├── services/
│   │   ├── database.js             # SQLite DB: all queries, schema, migrations
│   │   ├── socialAutomation.js     # OAuth flows + platform API posting (no browser driver)
│   │   ├── wallet.js               # TON Network: USDT balance, deposits, withdrawals
│   │   ├── ai.js                   # AI ad generation: text, image, video, audio
│   │   └── paymentPoller.js        # TON Network payment detection (polls every 30s)
│   ├── middleware/
│   │   └── security.js             # Rate limiting, input sanitisation, token generation
│   └── utils/
│       ├── logger.js               # Structured logging with DB persistence
│       └── config.js               # Environment config loader
├── website/                        # GitHub Pages static site
│   ├── index.html                  # Landing page
│   ├── privacy.html                # Privacy Policy (Meta/TikTok/X compliant)
│   ├── terms.html                  # Terms & Conditions
│   ├── data-deletion.html          # Data Deletion Callback (required by Meta)
│   ├── cookies.html                # Cookie Policy
│   └── oauth-success.html          # Post-OAuth redirect page
├── .env                            # Environment variables (never commit this)
├── .env.example                    # Template for environment variables
└── README.md                       # This file
```

---

## Installation & Setup

### Prerequisites

- Node.js 18 or higher (22 recommended)
- A Telegram Bot Token (from [@BotFather](https://t.me/BotFather))
- A publicly accessible server with HTTPS (for webhooks and OAuth callbacks)
- TON Network wallet for receiving deposits

### 1. Clone and Install

```bash
git clone https://github.com/yourusername/probityai.git
cd probityai
npm install
```

### 2. Configure Environment Variables

Copy the example file and fill in your values:

```bash
cp .env.example .env
nano .env
```

Full `.env` reference:

```env
# ── TELEGRAM ──────────────────────────────────────────────────────────
BOT_TOKEN=your_telegram_bot_token_from_botfather
BOT_USERNAME=Probityads_Bot

# ── SERVER ────────────────────────────────────────────────────────────
WEBHOOK_URL=https://yourserver.com          # Public HTTPS URL of your server
WEBHOOK_PORT=3000                           # Port for the HTTP server
WEBHOOK_SECRET=your_random_webhook_secret   # Any random string

# ── DATABASE ──────────────────────────────────────────────────────────
DB_PATH=./probity.db

# ── TON BLOCKCHAIN ────────────────────────────────────────────────────
TON_NETWORK=mainnet                         # mainnet or testnet
MASTER_WALLET_ADDRESS=EQyourtonwallethere   # Your TON wallet for receiving deposits
WALLET_VERSION=W5
TONCENTER_API_KEY=your_toncenter_api_key    # From toncenter.com

# ── ENCRYPTION (generate random 32-char strings) ───────────────────────
TOKEN_ENCRYPT_KEY=change_this_32char_key_now_please
OAUTH_STATE_SECRET=another_32char_state_secret_key

# ── FACEBOOK & INSTAGRAM (same Meta Developer App) ────────────────────
FACEBOOK_APP_ID=your_facebook_app_id
FACEBOOK_APP_SECRET=your_facebook_app_secret
INSTAGRAM_APP_ID=your_facebook_app_id
INSTAGRAM_APP_SECRET=your_facebook_app_secret

# ── TIKTOK ────────────────────────────────────────────────────────────
TIKTOK_CLIENT_KEY=your_tiktok_client_key
TIKTOK_CLIENT_SECRET=your_tiktok_client_secret

# ── X (TWITTER) ───────────────────────────────────────────────────────
X_CLIENT_ID=your_x_oauth2_client_id
X_CLIENT_SECRET=your_x_oauth2_client_secret

# ── WHATSAPP ──────────────────────────────────────────────────────────
WHATSAPP_VERIFY_NUMBER=+2348012345678       # Your WhatsApp number for manual verification

# ── REWARDS ───────────────────────────────────────────────────────────
REFERRAL_BONUS_PROMOTER=2
REFERRAL_BONUS_MERCHANT=1
POST_VERIFY_DELAY=30                        # Minutes before auto-verifying a post

# ── ADMIN ─────────────────────────────────────────────────────────────
MASTER_TELEGRAM_ID=your_telegram_id         # Your Telegram ID for admin access
SUPPORT_TELEGRAM_IDS=id1,id2               # Comma-separated support staff IDs

# ── LOGGING ───────────────────────────────────────────────────────────
LOG_LEVEL=4
```

### 3. Start the Bot

**Development (polling mode):**
```bash
node src/index.js
```

**Production (webhook mode — set WEBHOOK_URL in .env first):**
```bash
node src/index.js
```

The bot automatically uses webhook mode when `WEBHOOK_URL` is set, and falls back to polling when it is not.

---

## OAuth Callback URLs

These routes are served automatically by the bot's built-in HTTP server. Register them in each platform's developer portal:

```
Facebook:   https://yourserver.com/oauth/callback/facebook
Instagram:  https://yourserver.com/oauth/callback/instagram
TikTok:     https://yourserver.com/oauth/callback/tiktok
X:          https://yourserver.com/oauth/callback/x
```

The server also exposes:
```
GET  /health       — Health check endpoint
GET  /             — Service info
POST /webhook/:secret — Telegram webhook
```

---

## Website (GitHub Pages)

The `website/` folder contains a complete static site for platform developer app registration compliance.

### Deploy to GitHub Pages

1. Create a **public** GitHub repository named `probityai`
2. Upload all files from the `website/` folder to the repository root
3. Go to **Settings → Pages → Source: main branch** → Save
4. Site goes live at `https://yourusername.github.io/probityai/`

### Required URLs for Developer Portals

| Purpose | URL |
|---|---|
| Privacy Policy | `https://yourusername.github.io/probityai/privacy.html` |
| Terms of Service | `https://yourusername.github.io/probityai/terms.html` |
| Data Deletion (Meta required) | `https://yourusername.github.io/probityai/data-deletion.html` |
| Cookie Policy | `https://yourusername.github.io/probityai/cookies.html` |

---

## Platform API Credentials Setup

### Facebook & Instagram — Free

1. Go to [developers.facebook.com](https://developers.facebook.com) → Create App → **Other** → **Business**
2. Add product: **Facebook Login for Business**
3. Add OAuth Redirect URIs: `/oauth/callback/facebook` and `/oauth/callback/instagram`
4. Add Privacy Policy URL and Data Deletion URL (from GitHub Pages)
5. Add permissions: `pages_manage_posts`, `instagram_content_publish`, `pages_show_list`
6. Switch App Mode to **Live**
7. Copy **App ID** and **App Secret** → add to `.env`

### TikTok — Free

1. Go to [developers.tiktok.com](https://developers.tiktok.com) → Create App
2. Add scopes: `user.info.basic`, `video.publish`
3. Add Redirect URI: `https://yourserver.com/oauth/callback/tiktok`
4. Copy **Client Key** and **Client Secret** → add to `.env`

### X (Twitter) — Free tier (1,500 posts/month)

1. Go to [developer.twitter.com](https://developer.twitter.com) → Create Project → Create App
2. Enable **OAuth 2.0** under User Authentication Settings
3. Set App Type: **Web App**
4. Add Callback URL: `https://yourserver.com/oauth/callback/x`
5. Copy **Client ID** and **Client Secret** → add to `.env`

### Telegram — No credentials needed

The existing `BOT_TOKEN` handles all Telegram verification and posting. No additional setup required.

---

## Reward Structure

| Action | Default Reward |
|---|---|
| Text ad post | 0.05 USDT |
| Image ad post | 0.08 USDT |
| Video ad post | 0.10 USDT |
| Audio ad post | 0.10 USDT |
| Refer a Promoter | 2.00 USDT |
| Refer a Merchant | 1.00 USDT |

Reward amounts are configurable by admin via the MasterBot dashboard.

---

## Security

- **OAuth 2.0** — all social media authentication done on platform's official pages. Passwords never touch PROBITY AI servers.
- **AES-256-GCM** encryption for all stored OAuth access tokens
- **HMAC-SHA256** signed OAuth state parameters to prevent CSRF
- **Rate limiting** — per-user request throttling on all bot actions
- **Input sanitisation** — all user inputs sanitised before DB storage
- **Handle deduplication** — each social media handle can only be linked to one account
- **Fake handle detection** — pattern-based rejection of test/placeholder handles
- **Proof verification** — post assignments verified before rewards are credited

---

## Bot Commands

| Command | Description |
|---|---|
| `/start` | Registration and main menu |
| `/menu` | Open dashboard |
| `/wallet` | View balance and transactions |
| `/profile` | View your profile |
| `/referral` | Your referral link and earnings |
| `/news` | Platform announcements |
| `/support` | Open a support ticket |
| `/help` | List all commands |
| `/master` | Admin dashboard (authorised staff only) |

---

## Database Schema Overview

The SQLite database contains these core tables:

| Table | Purpose |
|---|---|
| `users` | All user accounts — Merchants, Promoters, Admin |
| `ads` | Ad campaigns created by Merchants |
| `post_assignments` | Ad posting records per Promoter per platform |
| `transactions` | All USDT credits, debits and withdrawals |
| `withdrawals` | Pending and completed withdrawal requests |
| `ads_bundles` | Merchant ad bundles (Text / Image / Video) |
| `products` | Merchant products |
| `support_tickets` | User support tickets |
| `support_messages` | Ticket conversation threads |
| `announcements` | Platform news and announcements |
| `challenges` | Temporary verification challenges (WhatsApp) |
| `reg_sessions` | Multi-step registration and flow sessions |
| `security_log` | Security events and suspicious activity |
| `daily_logs` | Per-user daily earnings tracking |
| `settings` | Platform-wide configuration (reward rates, limits) |

---

## Admin Features (MasterBot)

Access the admin dashboard with `/master` (your Telegram ID must be in `MASTER_TELEGRAM_ID`):

- 👥 **User Management** — view, suspend, ban, or restore any account
- 📢 **Ad Approval** — review and approve/reject uploaded ads
- 💸 **Withdrawal Processing** — approve or reject withdrawal requests
- 📊 **Platform Stats** — total users, posts, earnings, active ads
- 📣 **Announcements** — broadcast news to all users or specific roles
- 🔧 **Settings** — update reward rates, daily limits, fees live
- 🛡️ **Security Log** — review suspicious activity reports

---

## Deployment

### Recommended: Railway or Render (free tier available)

**Railway:**
```bash
# Install Railway CLI
npm install -g @railway/cli
railway login
railway init
railway up
```
Set all environment variables in Railway dashboard → Variables.

**Render:**
1. Connect GitHub repository to Render
2. Set Start Command: `node src/index.js`
3. Add all environment variables in the Render dashboard
4. Enable a custom domain for HTTPS (required for webhooks)

**VPS (Ubuntu):**
```bash
# Install Node.js 22
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# Install PM2 for process management
npm install -g pm2

# Start the bot
pm2 start src/index.js --name probityai
pm2 startup
pm2 save
```

---

## Contributing

This is a private repository. For bug reports or feature requests, open a support ticket via [@Probityads_Bot](https://t.me/Probityads_Bot).

---

## Legal

- [Privacy Policy](https://yourusername.github.io/probityai/privacy.html)
- [Terms & Conditions](https://yourusername.github.io/probityai/terms.html)
- [Data Deletion](https://yourusername.github.io/probityai/data-deletion.html)
- [Cookie Policy](https://yourusername.github.io/probityai/cookies.html)

PROBITY AI complies with Meta Platform Terms, TikTok Developer Terms, X Developer Agreement, and GDPR principles.

---

<div align="center">

**© 2026 PROBITY AI — All rights reserved**

Built on the [TON Network](https://ton.org/) · Powered by Telegram · USDT Payments

[![Telegram](https://img.shields.io/badge/Join%20Now-@Probityads__Bot-blue?logo=telegram)](https://t.me/Probityads_Bot)

</div>
