# OutreachOS — Cold Outreach Operating System

> Turn cold messages into real conversations. A signal-powered outreach workspace that helps you find high-value prospects, craft personalized messages, and automate follow-up sequences — all in one dark-mode SPA.

---

## What is OutreachOS?

OutreachOS is a single-page web app built for founders, sales professionals, and creators who do their own outreach. It replaces the chaos of spreadsheets, copy-pasted DMs, and forgotten follow-ups with a structured operating system that surfaces the right people, at the right moment, with the right message.

The core idea: **outreach quality beats outreach volume**. OutreachOS helps you identify leads who are already showing buying signals, compose messages that reference those signals directly, and stay on top of follow-ups before momentum dies.

Everything runs in the browser. No backend, no database, no subscription — your data lives in `localStorage` and persists across sessions.

---

## Features

### ⚡ Command Deck
Your daily home base. Opens every session with a clear picture of where you stand and exactly what to do next.

- **Live KPIs** — Messages sent, reply rate, warm leads count, and follow-ups due, all updating in real time
- **Today's Flow** — A prioritised action list of follow-ups, intros, and re-engages due today; tick items off as you go
- **Quick-Launch Chips** — One-click to load any sequence directly from the home screen (Cold Intro, Proof Bump, Soft Nudge, Creator Collab)
- **Activity Feed** — A live stream of prospect signals: profile views, email opens, link clicks, post engagements
- **Performance Overview** — 7-day snapshot of average response time, email open rate, and top-performing sequence

---

### 📡 Lead Radar
A ranked, filterable list of prospects sorted by live signal strength — not just job title or company size.

Each lead card shows:
- **Heat Score** (0–99) — a composite signal score that updates in real time as new events come in
- **Signal Tags** — Post activity, hiring signals, mutual connections, and recent engagement
- **Signal Breakdown Bars** — Four individual scores (Activity, Hiring, Mutual, Engagement) rendered as visual bars
- **Wave Assignment** — Leads are grouped into waves so you can batch your outreach strategically

Filter by:
- **Signal Strength** — High (70+), Mid (40–70), Low (<40)
- **Sequence Stage** — Not Started, Active
- **Lead Wave** — Wave 1, Wave 2, Wave 3

From any lead card you can open them in **DM Studio**, add them to a **Sequence**, or jump directly to their **LinkedIn profile**.

---

### 🧪 Sequence Lab
Build and manage multi-step outreach cadences across LinkedIn and email, with smart day-based delays between steps.

Comes pre-loaded with four proven sequences:

| Sequence | Steps | Best For |
|---|---|---|
| 🚀 Cold Intro | 3 steps (Day 0 / 3 / 7) | First touch on any new prospect |
| 📊 Proof Bump | 2 steps (Day 0 / 4) | Sending social proof after a cold intro |
| 🤝 Soft Nudge | 2 steps (Day 0 / 5) | Re-engaging prospects who went silent |
| 🎨 Creator Collab | 4 steps (Day 0 / 3 / 6 / 10) | Partnership and collaboration outreach |

Each sequence shows live stats: reply rate, active leads, and total messages sent. You can add, edit, or remove steps inline, and create entirely new sequences from scratch.

---

### ✍️ DM Studio
A message composer that writes around your prospect — not a generic template dropped into a name field.

**How it works:**
1. Select a lead — their signal context (recent post, hiring status, mutual connections, engagement) loads automatically
2. Pick a tone — Professional, Casual, Direct, or Playful
3. Pick a channel — LinkedIn DM or Email (character limits and format adjust accordingly)
4. Select proof points — click the achievements, ratings, or case studies you want woven into the message
5. Hit **Generate** — the message pulls in the lead's actual signals and proof points into a personalised draft
6. Edit freely, then hit **Open on LinkedIn**

**Open on LinkedIn** copies the message to your clipboard and opens the lead's LinkedIn profile (or search page) in a new tab simultaneously. You paste and send — the whole flow takes under 10 seconds.

Every sent message is logged in **Recent Sends**, and a follow-up task is automatically added to Today's Flow.

---

### 🔥 Warm Queue
A heat-sorted list of leads who are actively showing signals right now — the people most worth messaging today.

- **Heat bars** animate in real time as new events come in (profile views, email opens, link clicks, replies)
- Leads scoring 85+ get a pulsing **⬆ Promote** badge
- Each card shows a timestamped event log: what they did and how much it bumped their heat score
- Filter by Hot (80+), Warm (55–80), or Promoted

The heat simulation runs on a 6-second interval in the background, so your queue is always moving.

---

## LinkedIn Integration

OutreachOS uses LinkedIn's **native data export** — the same file LinkedIn gives you when you request a copy of your data. This means no API keys, no browser extensions, no third-party services, and no risk of getting your account flagged.

### How to import your connections

1. Go to [linkedin.com/psettings/member-data](https://www.linkedin.com/psettings/member-data)
2. Click **Data Privacy → Get a copy of your data**
3. Select **Connections** and click **Request Archive**
4. LinkedIn emails you a download link (usually within 10 minutes)
5. Unzip the download — find `Connections.csv`
6. In OutreachOS, click **Import Connections CSV** in the sidebar and upload the file

OutreachOS reads: First Name, Last Name, Email, Company, Position, and Connected On date. Each connection becomes a lead in your Radar with an initial heat score, and a LinkedIn search link attached so you can jump to their profile in one click.

### Sending messages

LinkedIn's API does not allow programmatic DM sending for individual accounts. OutreachOS handles this with a one-click flow that takes under 10 seconds:

1. Compose your message in DM Studio
2. Click **Open on LinkedIn** — message is copied to clipboard, their LinkedIn profile opens in a new tab
3. Paste (`Ctrl+V`) and send

---

## Tech Stack

| Layer | Choice |
|---|---|
| Framework | Vanilla HTML/CSS/JS — zero dependencies, zero build step |
| Styling | CSS custom properties, glassmorphism, `backdrop-filter` |
| Persistence | Browser `localStorage` |
| Deployment | GitHub Pages (static hosting) |
| LinkedIn data | CSV import (native LinkedIn data export) |

The entire app is a single `index.html` file. No `npm install`, no bundler, no server.

---

## Deployment

The app is deployed as a static site via GitHub Pages. To fork and deploy your own instance:

1. Fork this repository
2. Go to **Settings → Pages**
3. Set Source to **Deploy from a branch** → Branch: `main` → Folder: `/ (root)`
4. Your instance will be live at `https://YOUR-USERNAME.github.io/outreachos`

---

## Data & Privacy

All data — leads, sequences, flow tasks, send history — is stored exclusively in your browser's `localStorage`. Nothing is sent to any server. Clearing your browser data will reset the app; exporting your state before doing so is recommended.

---

## Roadmap (not yet built)

- [ ] CSV export of leads and send history
- [ ] Email integration via mailto / Gmail compose links
- [ ] Kanban view for sequence stages
- [ ] Custom proof point editor
- [ ] Mobile-responsive layout
- [ ] Full API integration via [Unipile](https://unipile.com) for programmatic LinkedIn DMs

---

## Y2K Mode

Press **✦ Y2K Mode** in the top bar. You'll know why.
