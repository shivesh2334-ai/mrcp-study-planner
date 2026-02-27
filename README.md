# 🏥 MRCP(UK) Personal Planner & Tracker

> A fully offline, browser-based personal study planner built for an Indian cardiologist with 25 years of experience — targeting the MRCP(UK) diploma by December 2026.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/YOUR_USERNAME/mrcp-guide-2026)
![HTML](https://img.shields.io/badge/HTML-Single%20File-orange)
![Storage](https://img.shields.io/badge/Storage-localStorage-blue)
![Deploy](https://img.shields.io/badge/Deploy-Vercel-black)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📸 Overview

This is a **single-file HTML application** — no frameworks, no backend, no database. Everything runs in the browser and persists via `localStorage`. Drop it on Vercel (or any static host) and it works immediately.

---

## ✨ Features

### 📊 Dashboard
- **Live countdown timers** to each exam (Part 1, Part 2, PACES) and the application deadline — colour-coded by urgency
- **Red flag alerts** — automatically detects and surfaces overdue subjects, at-risk topics, and approaching deadlines
- **Overall progress %** with a visual progress bar across all topics
- Phase-by-phase progress breakdown (Phase 1, 2, 3)
- Topic completion summary (Not Started / In Progress / Completed / Delayed)
- "Currently In Progress" and "Starting in Next 14 Days" panels

### 📚 Study Planner
- **Subject-level tracking** — name, phase, target start/end dates, actual start/completion dates, status
- **Topic-level tracking** — each subject contains individual topics with their own dates and status
- **Inline quick-add** — type a topic name and press Enter to add instantly
- **Full topic editor** — modal form for detailed entry including notes
- **Bulk date adjustment** — shift all pending target dates forward or backward by N days, per phase or across all phases
- **Status auto-detection** — statuses update automatically based on dates and completion flags:
  - `Not Started` → `At Risk` (start date imminent) → `In Progress` → `Delayed` (overdue) → `Completed`
- Phase filter to focus on one phase at a time

### 🔗 Resources
- **Suggested resources strip** — 13 pre-loaded MRCP resources with one-click enrolment:
  - Question banks: Passmedicine, OnExamination (BMJ), Zero to Finals
  - Textbooks: Kumar & Clark, Philip Kalra Notes, Iqbal & Iqbal PACES
  - Guidelines: NICE, ESC, BTS, BSG
  - Courses: ISC Medical PACES, RCP London PACES
  - Registration: MRCP(UK) Official
- **Full resource table** with clickable links, type badges, phase labels, and date tracking
- Overdue warning (⚠️) on resources past their target completion date
- Track start date, target completion, and actual completion for each resource
- Status tracking: Enrolled → In Progress → Completed / Paused

### 📅 Timeline (Gantt Chart)
- **Visual Gantt chart** spanning your entire prep period
- Faded bars = target date range
- Solid bars = actual progress
- Red vertical line = today
- Exam date markers (Part 1, Part 2, PACES) overlaid on the chart
- Month labels for easy navigation
- Per-phase grouping with colour-coded status

### ⚙ Setup
- Enter candidate name and qualification
- Set all **key dates**: preparation start, application deadline, Part 1 exam, Part 2 exam, PACES exam
- Choose **exam centres** (Mumbai, Delhi, Chennai, Kolkata, Hyderabad, Bangalore)
- Set daily study hours (used for planning context)
- **One-click MRCP Template** — loads 20 subjects with 100+ pre-defined topics across all 3 phases, auto-dated from your preparation start date

---

## 📋 Pre-loaded MRCP Subject Template

Clicking **"✨ Load MRCP Template"** in Setup auto-populates the planner with:

| Phase | Subjects |
|---|---|
| **Phase 1 — Part 1** | Cardiology, Respiratory, Nephrology, Gastroenterology & Hepatology, Neurology, Endocrinology & Diabetes, Rheumatology, Haematology, Infectious Diseases, Basic Sciences & Pharmacology, Dermatology & Ophthalmology |
| **Phase 2 — Part 2** | Clinical Management (Cardiology), Clinical Management (Respiratory), Clinical Management (Renal & GI), Data Interpretation, Statistics & EBM |
| **Phase 3 — PACES** | PACES Examination Technique, PACES History Taking, PACES Communication & Ethics, PACES Data Interpretation |

Each subject comes with pre-defined topics and auto-calculated target dates relative to your prep start.

---

## 🚀 Deployment Guide

### Prerequisites
- A free [GitHub](https://github.com) account
- A free [Vercel](https://vercel.com) account (sign in with GitHub)

---

### Step 1 — Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `mrcp-guide-2026`
3. Set visibility to **Public**
4. Click **Create repository**

---

### Step 2 — Upload Files

#### Option A — GitHub Web Interface (No Git Required)
1. In your new repo, click **Add file → Upload files**
2. Drag and drop these 3 files:
   - `index.html`
   - `vercel.json`
   - `README.md`
3. Scroll down → click **Commit changes**

#### Option B — Git Command Line
```bash
git clone https://github.com/YOUR_USERNAME/mrcp-guide-2026.git
cd mrcp-guide-2026

# Copy your 3 files into this folder, then:
git add .
git commit -m "Initial commit: MRCP Planner & Tracker"
git push origin main
```

---

### Step 3 — Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) → click **New Project**
2. Find `mrcp-guide-2026` in your repository list → click **Import**
3. Leave all settings as default — Vercel detects static HTML automatically
4. Click **Deploy**
5. ✅ Your app is live in ~30 seconds at `https://mrcp-guide-2026.vercel.app`

---

### Step 4 — (Optional) Custom Domain

1. Vercel project → **Settings → Domains**
2. Add a domain like `mrcp.yourdomain.com`
3. Follow Vercel's DNS instructions

---

### Automatic Redeployment

Every time you push changes to GitHub, Vercel redeploys automatically:

```bash
git add index.html
git commit -m "Update study template"
git push
# → Live within ~20 seconds
```

---

## 💾 Data Storage

All your data (subjects, topics, resources, setup) is stored in the browser's **`localStorage`**. This means:

| Behaviour | Detail |
|---|---|
| ✅ Persists across page refreshes | Yes — data survives closing and reopening the tab |
| ✅ No account or login required | Fully private, no data sent anywhere |
| ✅ Works offline | Once loaded, no internet needed |
| ⚠️ Device-specific | Data lives in the browser on that device |
| ⚠️ Clearing browser data | Will erase your progress — export periodically |

**Tip:** To back up your data, open the browser console (`F12`) and run:
```javascript
JSON.stringify(localStorage)
```
Copy and save the output. To restore, paste it back with `localStorage.setItem(...)`.

---

## 📁 Project Structure

```
mrcp-guide-2026/
├── index.html      ← Complete application (single file — HTML + CSS + JS)
├── vercel.json     ← Vercel deployment configuration
└── README.md       ← This file
```

---

## 🗓 Recommended Study Plan

| Phase | Period | Target Exam Diet | Daily Target |
|---|---|---|---|
| Phase 1 — Part 1 Prep | Feb → May 2026 | May/June diet | 100–120 questions/day |
| Phase 2 — Part 2 Written | June → Aug 2026 | Sept/Oct diet | Guidelines + clinical cases |
| Phase 3 — PACES | Oct → Dec 2026 | December diet | Daily examination practice |

**Monthly hours:** ~65 hrs (2.5 hrs/weekday + 4.5 hrs/weekend)  
**Total over 10 months:** ~650 hours

---

## 🔗 Key Resources

### Question Banks
| Resource | Link | Best For |
|---|---|---|
| Passmedicine | [passmedicine.com](https://www.passmedicine.com) | Part 1 & 2 — primary Q-bank |
| OnExamination (BMJ) | [onexamination.com](https://www.onexamination.com) | Part 1 & 2 — supplementary |
| Zero to Finals | [zerotofinals.com](https://zerotofinals.com/medicine/) | Free revision notes |

### Textbooks
| Resource | Link | Best For |
|---|---|---|
| Kumar & Clark's Clinical Medicine | [elsevier.com](https://www.elsevier.com/books/kumar-and-clarks-clinical-medicine) | Core reference — read selectively |
| MRCP Part 1 Revision Notes — Philip Kalra | [amazon.co.uk](https://www.amazon.co.uk/dp/1907904433) | Condensed Part 1 prep |
| PACES for the MRCP — Iqbal & Iqbal | [amazon.co.uk](https://www.amazon.co.uk/dp/1905635540) | PACES preparation |

### Clinical Guidelines
| Resource | Link |
|---|---|
| NICE Guidelines | [nice.org.uk/guidance](https://www.nice.org.uk/guidance) |
| ESC Guidelines | [escardio.org/Guidelines](https://www.escardio.org/Guidelines) |
| BTS Guidelines | [brit-thoracic.org.uk](https://www.brit-thoracic.org.uk/quality-improvement/guidelines/) |
| BSG Guidelines | [bsg.org.uk](https://www.bsg.org.uk/clinical-guidance/) |

### Courses & Official Registration
| Resource | Link |
|---|---|
| MRCP(UK) Official — Registration | [mrcpuk.org](https://www.mrcpuk.org) |
| ISC Medical PACES Course | [iscmedical.co.uk](https://www.iscmedical.co.uk/mrcp-paces-courses.html) |
| RCP London PACES Course | [rcplondon.ac.uk](https://www.rcplondon.ac.uk/education-practice/courses/mrcp-uk-paces-preparation-course) |

---

## 🩺 Tips for Experienced Cardiologists

### Leverage Your Strengths
- **Cardiology (Part 1 & 2)** — 15–20% of questions; aim for near-perfect scores
- **ECG interpretation (PACES Station 5)** — your strongest station; bank the marks
- **Data interpretation** — ABGs, CXR, spirometry will feel familiar
- **Clinical vignettes (Part 2)** — 25 years of instinct is a real asset

### Watch These Danger Zones
- **Basic sciences (Part 1)** — genetics, pharmacology mechanisms, statistics. Do not underestimate.
- **PACES communication station** — experienced doctors often default to paternalism; MRCP requires ICE-based patient-centred style
- **Examination technique** — must be textbook sequence, not clinical habit. Verbalise steps. Video yourself.
- **Dermatology, ophthalmology, psychiatry** — low clinical exposure, higher exam weight than expected
- **Gastroenterology & rheumatology management** — NICE guidelines, not just clinical instinct

---

## 📊 Exam Facts

| Item | Detail |
|---|---|
| Part 1 Fee | ~£450 |
| Part 2 Written Fee | ~£550 |
| PACES Fee | ~£800 |
| Attempts Allowed | 6 per part (within 3 years) |
| India Centres (Part 1 & 2) | Mumbai, Delhi, Chennai, Kolkata, Hyderabad |
| India Centres (PACES) | Selected centres — verify at mrcpuk.org |
| Exam Diets | 3 per year (approx. Jan, May, Sept) |

> ⚠️ All fees and dates are indicative. Always verify current information at [mrcpuk.org](https://www.mrcpuk.org) before registering.

---

## 🛠 Technical Notes

- **No build step required** — open `index.html` directly in a browser to test locally
- **No dependencies** — vanilla HTML, CSS, and JavaScript only
- **Google Fonts** — loads Playfair Display, DM Sans, DM Mono via CDN (requires internet on first load; cached thereafter)
- **localStorage keys** — `mrcp_setup`, `mrcp_subjects`, `mrcp_resources`
- **Browser support** — Chrome, Firefox, Safari, Edge (all modern versions)

---

## 📄 License

MIT License — free to use, modify, and redistribute.

---

*Built for a specific purpose: helping a dedicated cardiologist earn a well-deserved postgraduate diploma.*
