# 🛡️ Sentinel AI — Cloud IDS & IPS Security Command Center

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)
![Supabase](https://img.shields.io/badge/Database-Supabase%20Postgres-3ECF8E?logo=supabase&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Styling-Tailwind%20CSS-38B2AC?logo=tailwind-css&logoColor=white)
![Hosting](https://img.shields.io/badge/Hosting-Vercel-000000?logo=vercel&logoColor=white)
![Realtime](https://img.shields.io/badge/WebSockets-Supabase%20Realtime-brightgreen)

> An enterprise-grade, real-time Cloud Intrusion Detection & Prevention System (IDS/IPS) built for hackathons. Features automated threat neutralization, live WebSocket telemetry, AI-powered heuristic assessments, and an adaptive dual-theme interface.

---

## 🌟 Key Features

- **⚡ Real-Time Threat Telemetry**: Instant bi-directional WebSocket syncing powered by **Supabase Realtime**. Incursions broadcast live across all connected client devices without page reloads.
- **🤖 Autonomous IPS (Auto-Defense Mode)**: When armed, newly simulated attacks are analyzed and neutralized (`Blocked`) automatically within exactly 2 seconds.
- **🧠 Sentinel AI Threat Analyst ("Ask AI")**: Provides instant contextual threat intelligence, MITRE ATT&CK technique mapping (e.g., T1498 DDoS, T1190 SQLi, Zero-Day RCE), severity scoring, an executable firewall drop rule (`iptables` / `eBPF`), and a 1-click **Copy Rule** button.
- **🎨 Dual-Personality Interface**:
  - **Hacker Dark Mode**: Deep obsidian backdrop (`#05070c`), glowing neon accents (`#00ff9d` green, `#00f0ff` cyan, `#ff0055` crimson), animated radar sweep, and CRT scanlines.
  - **Corporate Light Mode**: Polished, professional SaaS dashboard with clean slate palettes and crisp contrast. Saved to `localStorage`.
- **💥 Attack Simulator**: Generate synthetic network anomalies (DDoS SYN Floods, SQL Injection, Zero-Day Exploits, Credential Stuffing, Ransomware beacons) across global IP vectors with smooth slide-down animations.
- **🔍 Real-Time Search & Filtering**: Live search bar filters the threat telemetry table by IP, attack vector, country code/name, severity, or status.
- **📊 Incident Audit Export**: Download filtered or full security event telemetry in standard **RFC-4180 CSV** format.
- **☁️ Supabase Cloud Ready**: Operates in standalone high-speed simulation mode out of the box, with built-in UI modal and configuration blocks for live Supabase cloud connection.

---

## 🏗️ Architecture & Technology Stack

```
[ Inbound Network Traffic ] ──► [ Sentinel AI Neural Filter ]
                                          │
                 ┌────────────────────────┴────────────────────────┐
                 ▼                                                 ▼
     [ Supabase PostgreSQL ]                           [ Edge Client Dashboard ]
     - `network_threats` table                         - Tailwind CSS (CDN)
     - Row Level Security (RLS)                        - Vanilla JS (Zero Build Tools)
     - Realtime Replication Publication                - Lucide Icon System
                 │                                                 ▲
                 └────────── WebSocket Event Stream ───────────────┘
                              (Hosted on Vercel)
```

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | Vanilla JavaScript + Tailwind CSS CDN | High-performance, single-file dashboard with zero build steps |
| **Icons** | Lucide Icons | Sleek, vector-rendered cybersecurity indicators |
| **Database** | Supabase (PostgreSQL 15+) | Cloud telemetry storage & historical audit logging |
| **Realtime** | Supabase WebSockets | Push notifications for new intrusions & quarantine state changes |
| **Hosting** | Vercel Edge Network | Sub-millisecond global CDN hosting |
| **VCS** | GitHub | Continuous Deployment (CI/CD) trigger |

---

## 🌐 Complete Step-by-Step Vercel Deployment Process

Choose any of the 3 deployment methods below. Since this application is a pure, self-contained single `index.html` file, **no build step, npm install, or bundler is required**.

---

### Option 1: Fast CLI Deployment Using `npx vercel` (Fastest — 1 Command)

No global packages need to be installed. Run directly from your project folder:

1. Open **PowerShell** or terminal inside the project directory:
   ```powershell
   cd c:\Users\snddc\OneDrive\frontend\Documents\hackthon
   ```
2. Run the deployment command:
   ```powershell
   npx vercel
   ```
3. Follow the quick terminal prompts:
   - **Log in to Vercel**: Press `Enter` to authenticate via browser (GitHub or Email).
   - **Set up and deploy?**: Type `y` and press `Enter`.
   - **Which scope?**: Select your personal Vercel team/account.
   - **Link to existing project?**: Type `n`.
   - **What's your project's name?**: Type `sentinel-cloud-ids` (or your chosen name).
   - **In which directory is your code located?**: Press `Enter` (uses `./`).
   - **Want to modify settings?**: Type `n`.
4. Deploy to production with a permanent URL:
   ```powershell
   npx vercel --prod
   ```
5. Your terminal will print your live URL:
   ```text
   ✅ Production: https://sentinel-cloud-ids.vercel.app
   ```

---

### Option 2: Deploy via GitHub & Vercel Dashboard (Recommended for Hackathons)

This connects your code to GitHub so every new commit automatically redeploys to Vercel.

#### Step 1: Initialize Git and Push to GitHub
Run the following commands in your PowerShell:

```powershell
# 1. Initialize local Git repository
git init

# 2. Stage all project files
git add index.html schema.sql README.md

# 3. Create your initial commit
git commit -m "feat: initial release of Sentinel AI IDS/IPS command center"

# 4. Set branch name to main
git branch -M main
```

#### Step 2: Create a Repository on GitHub
1. Go to **[GitHub New Repository](https://github.com/new)**.
2. Enter Repository name: `sentinel-cloud-ids`.
3. Set visibility to **Public**.
4. Leave "Add README", ".gitignore", and "license" **unchecked** (we already have them).
5. Click **Create repository**.

#### Step 3: Link Remote and Push
Copy and run the remote commands shown by GitHub:
```powershell
# Replace YOUR_GITHUB_USERNAME with your GitHub account name
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/sentinel-cloud-ids.git

# Push your code
git push -u origin main
```

#### Step 4: Import Repository in Vercel
1. Go to **[vercel.com](https://vercel.com)** and log in with GitHub.
2. Click **Add New...** &rarr; select **Project**.
3. Under **Import Git Repository**, locate `sentinel-cloud-ids` and click **Import**.
4. Project Configuration:
   - **Project Name**: `sentinel-cloud-ids`
   - **Framework Preset**: **Other** (Static HTML)
   - **Root Directory**: `./`
   - **Build & Development Settings**: Leave default (no build required).
5. Click **Deploy**.
6. Within 15 seconds, your command center is live at:
   `https://sentinel-cloud-ids.vercel.app`

---

### Option 3: Drag & Drop Upload (Zero Git / Zero Terminal)

1. Log into your dashboard at **[vercel.com](https://vercel.com)**.
2. Go to **[vercel.com/new](https://vercel.com/new)**.
3. Scroll down to the **"Deploy a Project"** section.
4. Drag and drop your project folder (`hackthon`) directly from Windows File Explorer into the Vercel upload dropzone.
5. Click **Deploy**. Vercel will immediately host your application.

---

## 🗄️ Database Setup (Supabase)

The Command Center works immediately in fast in-memory simulation mode. To enable live cloud multi-client synchronization:

### 1. Run the Database Schema
1. Create a free account at [Supabase](https://supabase.com) and start a new project.
2. Navigate to the **SQL Editor** in the left navigation.
3. Open [`schema.sql`](./schema.sql), paste the SQL code into the editor, and click **Run**.
4. This creates:
   - `network_threats` table
   - Row Level Security (RLS) policies for anonymous read/insert/update
   - Realtime publication stream for instant updates

### 2. Connect to the Live App
You can connect Supabase in two ways:

#### Option A: Via the In-App UI Modal (No code edit required!)
1. Open your live Vercel website.
2. Click the **Database icon** (`database`) in the top navigation bar.
3. Enter your **Project URL** (`https://<project-ref>.supabase.co`) and **Anon Public Key**.
4. Click **Connect Cloud**. The status will turn to **CONNECTED (SUPABASE REALTIME)**.

#### Option B: In `index.html` Code
Open [`index.html`](./index.html) and update `SUPABASE_CONFIG`:
```javascript
const SUPABASE_CONFIG = {
  ENABLED: true,
  URL: 'https://zdcvfkannwgnsmocpaea.supabase.co',
  ANON_KEY: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...',
};
```

---

## 🏆 Hackathon Presentation & Live Demo Script

When presenting to hackathon judges, follow this sequence:

1. **Multi-Screen Realtime Sync**:
   - Open your live Vercel URL on your laptop and simultaneously on your smartphone.
   - Click **"Simulate Attack"** on the laptop. Show how the intrusion appears live on the phone screen with zero reload.
2. **Autonomous IPS Demonstration**:
   - Verify that **Auto-Defense** is **ARMED**.
   - Watch the active attack row display an `Auto-blocking in 2s...` countdown, then automatically transition to `Blocked` (Green) with a visual flash.
3. **AI Threat Intelligence & Remediation**:
   - Click **"Ask AI"** on any threat row.
   - Show the dynamic MITRE ATT&CK technique breakdown (e.g. T1498, T1190, T1059), severity score, and the generated `iptables` / `eBPF` firewall rule.
   - Click **"Copy"** to demonstrate clipboard integration, and click **"Execute Immediate Block"**.
4. **Interactive Telemetry Filtering & Audit Export**:
   - Type in the search box to filter by vector (e.g., `SQL`, `DDoS`) or country code.
   - Click **"Export CSV"** to demonstrate instant compliance audit report generation in standard RFC-4180 format.
5. **Theme Switch**:
   - Toggle between **Hacker Dark Mode** and **Corporate Light Mode** to demonstrate UI polish and accessibility.

---

## 📜 Database Schema Reference

Table: `public.network_threats`

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `UUID` | `PRIMARY KEY`, Default `gen_random_uuid()` | Unique threat event identifier |
| `created_at` | `TIMESTAMPTZ` | `DEFAULT now()`, `NOT NULL` | Event timestamp |
| `source_ip` | `TEXT` | `NOT NULL` | Source IP address |
| `origin_country` | `TEXT` | `NOT NULL` | ISO 3166-1 alpha-2 country code |
| `attack_type` | `TEXT` | `NOT NULL` | Incursion classification (e.g. DDoS, SQLi, RCE) |
| `severity` | `TEXT` | Check `('Critical', 'High', 'Medium', 'Low')` | Threat severity level |
| `status` | `TEXT` | Check `('Active', 'Blocked')` | Current IPS defense status |

---

## 🛡️ License

MIT License &mdash; Free for academic, personal, and hackathon use.
