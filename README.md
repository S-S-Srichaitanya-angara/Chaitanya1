# FocusMate Dashboard

A production-grade productivity tracking dashboard built with React, Recharts, and Lucide React. Pixel-faithful recreation of the FocusMate UI design.

## 🚀 Quick Start

```bash
# 1. Clone / enter the project
cd focusmate

# 2. Install dependencies
npm install

# 3. Start dev server
npm start
# Opens at http://localhost:3000
```

## 📁 File Structure

```
focusmate/
├── public/
│   └── index.html              # HTML entry point
├── src/
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Sidebar.jsx     # Left navigation sidebar
│   │   │   └── Topbar.jsx      # Top header bar with live timer
│   │   └── dashboard/
│   │       ├── Dashboard.jsx         # Main page layout / grid
│   │       ├── FocusScoreCard.jsx    # Circular score ring + stats
│   │       ├── MiniStatCard.jsx      # Small metric cards (top row)
│   │       ├── SessionTimeline.jsx   # Focus/distraction timeline chart
│   │       ├── TopDistractions.jsx   # Distraction app breakdown
│   │       ├── TasksCard.jsx         # Interactive task checklist
│   │       ├── FocusScoreTrend.jsx   # Weekly line chart
│   │       ├── FocusHoursChart.jsx   # Daily bar chart
│   │       ├── ProductivityHeatmap.jsx # GitHub-style heatmap
│   │       ├── InsightsPanel.jsx     # AI-style insight cards
│   │       └── AchievementCard.jsx   # Achievement / leaderboard card
│   ├── data/
│   │   └── mockData.js         # All static mock data & generators
│   ├── App.jsx                 # Root component
│   ├── index.js                # React DOM entry
│   └── index.css               # Global styles + CSS design tokens
├── package.json
└── README.md
```

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| **React 18** | UI framework |
| **Recharts** | Charts (line, bar, area, composed) |
| **Lucide React** | Icon library |
| **CSS Variables** | Design tokens / theming |
| **Google Fonts** | Syne (display) + DM Sans (body) |

## ✨ Features

- **Live Session Timer** — ticks every second in the topbar
- **Interactive Tasks** — click to toggle completion, progress bar updates
- **Animated Charts** — line chart, bar chart, area sparklines via Recharts
- **Focus Score Ring** — SVG circle with animated stroke-dashoffset
- **Productivity Heatmap** — GitHub-style calendar heat grid
- **Session Timeline** — stacked bar chart with focus/distraction/idle
- **Dark Theme** — full dark design with CSS variable system
- **Micro-animations** — fade-in cards on load, hover states, glow effects

## 🎨 Design Tokens (CSS Variables)

Edit `src/index.css` to change the theme:

```css
:root {
  --green-primary: #22C55E;   /* Primary accent */
  --bg-card: #181C22;         /* Card background */
  --text-primary: #F1F5F9;    /* Main text */
  --font-display: 'Syne';     /* Headings */
  --font-body: 'DM Sans';     /* Body text */
}
```

## 📦 Building for Production

```bash
npm run build
# Output in /build folder — ready to deploy on Vercel, Netlify, etc.
```

## 🔧 Connecting Real Data

Replace `src/data/mockData.js` exports with API calls. Suggested endpoints:

```
GET /api/session/current     → sessionStats
GET /api/sessions/timeline   → sessionTimeline
GET /api/distractions        → topDistractions
GET /api/tasks               → tasks
GET /api/analytics/weekly    → focusScoreTrend, focusHoursPerDay
GET /api/heatmap             → heatmapData
```
