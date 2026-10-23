# Personal Study Planner – Intelligent Revision Schedules

> Turn exam stress into a clear, manageable plan. Add your subjects and availability, then get a day-by-day revision schedule built around your deadlines.

![HTML5](https://img.shields.io/badge/HTML5-single--file-orange?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-yellow?logo=javascript&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-CDN-38B2AC?logo=tailwindcss&logoColor=white)
![No installation](https://img.shields.io/badge/setup-no_installation-brightgreen)

## The Problem & The Solution

### The problem

Pre-exam panic often comes from decision paralysis: students have several subjects, different deadlines, and limited time, but no clear way to balance them. The result can be poor time management and last-minute cramming.

### The solution

Personal Study Planner is a client-side, offline-first study planner that calculates the days remaining until exams, gives harder subjects more scheduling priority, and balances study blocks against the student's daily availability. Subject data and plan progress are saved in the browser, so they stay available on return visits without an account.

> **Data note:** Planner data is stored locally in your browser. Tailwind CSS and Confetti are loaded from CDNs, so an internet connection is needed to fetch those assets when they are not cached.

## Key Features

| Feature | What it does |
| --- | --- |
| **Dynamic scheduling engine** | Prioritizes subjects by difficulty and urgency, then distributes target hours across available study days. |
| **Capacity protection** | Keeps the total scheduled study time for each day within the selected daily availability limit. |
| **Interactive daily timetable** | Groups sessions by date with color-coded subject badges, task descriptions, and completion checkboxes. |
| **Persistent progress tracking** | Updates the completion progress bar and saves checked tasks and planner data in browser LocalStorage. |
| **Pomodoro focus timer** | Provides a 25-minute focus timer with start, pause, reset, and a completion sound cue. |
| **⚡ Demo Mode** | Loads sample subjects and generates a plan instantly for presentations. |
| **Print / Save PDF** | Provides a print-friendly schedule that can be printed or saved as a PDF from the browser. |
| **Confetti celebration** | Celebrates when all scheduled sessions are marked complete. |

## How the Scheduling Algorithm Works

- **Calculate urgency:** The planner measures the number of days between today and each exam date. It schedules study sessions from tomorrow through the day before the exam.
- **Weight difficulty:** Hard subjects receive weight **3**, Medium subjects **2**, and Easy subjects **1**. The weights affect scheduling priority; Hard subjects also receive longer sessions where capacity allows.
- **Distribute and protect capacity:** Remaining study hours are spread across each subject's available days. The planner fills each day's available study time while checking that the combined sessions never exceed the daily availability setting.
- **Reserve the exam eve:** Sessions on the day before an exam are labeled **Final Review & Past Papers**.

If the available days and daily capacity cannot accommodate all target hours, the planner displays a high-workload warning.

## Tech Stack

- **HTML5** and modern **Vanilla JavaScript (ES6+)** in a single `index.html` file.
- **Tailwind CSS**, loaded via CDN, for responsive styling.
- **Web Storage API (`localStorage`)** for private, browser-based persistence.
- **Canvas-Confetti**, loaded via CDN, for completion celebrations.
- Browser **Web Audio API** for the focus timer sound cue.

## Getting Started

No installation or build step is required.

1. **Get the project:** Clone or download this repository to your computer.
2. **Open the app:** Double-click `index.html` to open it in a modern web browser.

For Tailwind styling and confetti animations, allow the page to load its CDN assets. Your subjects, daily availability, and schedule progress are saved in that browser's LocalStorage.

## Screenshots

Add screenshots here to show the planner and its features:

| Planner overview | Revision plan |
| --- | --- |
| **Screenshot placeholder**<br>Add `screenshots/planner-overview.png` | **Screenshot placeholder**<br>Add `screenshots/revision-plan.png` |

| Focus timer | Completed plan |
| --- | --- |
| **Screenshot placeholder**<br>Add `screenshots/focus-timer.png` | **Screenshot placeholder**<br>Add `screenshots/completed-plan.png` |

## “Vibecoding” Methodology & Reflection

The app was designed and architected by a student working as the Product Manager and Architect. Through iterative prompting and AI pairing, the student shaped the requirements, engineered and tested features in modular sprints, and refined the experience as each part of the planner came together. This “vibecoding” approach moves quickly from an idea to a working interface while keeping the student involved in product decisions and feature review.

## Future Roadmap

- **Google Calendar sync** to bring revision sessions into a student's calendar.
- **Adaptive auto-rescheduling** to adjust the plan when study days are missed.
