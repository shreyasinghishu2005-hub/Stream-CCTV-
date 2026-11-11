<div align="center">

# ◈ STREAM CCTV

### Smart Video Surveillance & Monitoring Dashboard

**A modern, real-time-style CCTV control center for camera feeds, people watchlists, alerts, and surveillance analytics.**

<br />

![Next.js](https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-19-20232A?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?style=for-the-badge&logo=tailwindcss)
![License](https://img.shields.io/badge/Status-Prototype-orange?style=for-the-badge)

<br />

[Features](#-features) · [Tech Stack](#-tech-stack) · [Getting Started](#-getting-started) · [Project Structure](#-project-structure) · [Important Notes](#-important-notes)

</div>

---

## ✨ Overview

**STREAM CCTV** is a browser-based surveillance dashboard built with Next.js, React, and TypeScript. It brings camera stream management, people/watchlist organization, alert monitoring, and footfall analytics into one dark, glass-style interface.

The project currently uses **demo authentication and mock/simulated surveillance data** to demonstrate the dashboard experience. It is a frontend prototype—not a production CCTV or facial-recognition backend.

## 🚀 Features

| Module | What it offers |
| --- | --- |
| 📹 **Camera Feeds** | Add, edit, and remove camera entries; view feeds in a responsive 2- or 3-column grid; open a camera in fullscreen. |
| ▶️ **HLS Playback** | HLS playback powered by `hls.js`, with native video support for compatible formats. |
| 👥 **People & Watchlist** | Enroll and manage profiles, search by name/designation, filter by category, and mute profile alerts. |
| 🔔 **Alert Center** | Review, mark as read, mark all as read, and dismiss watchlist alerts. |
| 📊 **Analytics** | Explore footfall summaries and camera-based charts using Recharts. |
| ⚙️ **Settings** | Configure prototype detection preferences, notification toggles, retention options, and clear local dashboard data. |
| ⌕ **Quick Search** | Open the global search modal with **Ctrl + K** or **⌘ + K**. |
| 💾 **Local Persistence** | Dashboard records are stored in browser `localStorage` between sessions. |

## 🧰 Tech Stack

<div align="center">

| Layer | Technology |
| --- | --- |
| Framework | [Next.js 16](https://nextjs.org/) (App Router) |
| UI | [React 19](https://react.dev/) |
| Language | [TypeScript](https://www.typescriptlang.org/) |
| Styling | [Tailwind CSS 4](https://tailwindcss.com/) + custom CSS |
| Video | [hls.js](https://github.com/video-dev/hls.js/) |
| Charts | [Recharts](https://recharts.org/) |
| Icons | [Lucide React](https://lucide.dev/) |

</div>

## 🖥️ Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 20 or later recommended
- npm (included with Node.js)
- A modern browser

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd STREAM-CCTV-main
```

### 2. Install dependencies

```bash
npm install
```

### 3. Start the development server

```bash
npm run dev
```

### 4. Open the application

Visit **http://localhost:3000** in your browser.

### Demo login

The current frontend includes a hard-coded demo login:

| Field | Value |
| --- | --- |
| Username | `admin` |
| Password | `admin` |

> ⚠️ These credentials are for local demonstration only. Replace the mock authentication flow with a secure server-side identity provider before deployment.

## 📁 Project Structure

```text
STREAM-CCTV-main/
├── app/
│   ├── (dashboard)/
│   │   ├── alerts/          # Alert center
│   │   ├── analytics/       # Footfall and camera analytics
│   │   ├── cameras/         # Camera feed management
│   │   ├── settings/        # Dashboard preferences
│   │   ├── watchlist/       # People and watchlist profiles
│   │   └── layout.tsx       # Shared dashboard shell/navigation
│   ├── login/               # Demo login screen
│   ├── globals.css          # Global styles and theme
│   ├── layout.tsx           # Root application layout
│   └── page.tsx             # Authentication redirect
├── components/
│   ├── camera-modal.tsx     # Add/edit camera dialog
│   ├── camera-tile.tsx      # Camera preview tile
│   ├── fullscreen-view.tsx  # Fullscreen camera view
│   ├── hls-player.tsx       # HLS/video player
│   └── search-modal.tsx     # Global command/search modal
├── lib/
│   ├── auth-context.tsx     # Demo authentication state
│   ├── dashboard-context.tsx# Dashboard state and localStorage
│   ├── mock-data.ts         # Sample dashboard data
│   └── types.ts             # TypeScript interfaces
├── package.json
└── README.md
```

## 📜 Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Run the local development server |
| `npm run build` | Create a production build |
| `npm run start` | Start the production server |
| `npm run lint` | Run ESLint checks |

## 🎥 Stream Compatibility

- **HLS (`.m3u8`)**: handled through `hls.js` where Media Source Extensions are supported; compatible browsers may use native playback.
- **MP4 / WebM**: passed to the browser's native video player.
- **RTSP / RTMP**: browsers cannot play these protocols directly. This prototype displays a simulated/transcoding state; a real deployment needs a media gateway (for example, FFmpeg or an RTSP-to-HLS/WebRTC service) to convert camera streams into a browser-compatible format.

Use a reachable stream URL and ensure the stream server permits browser access (CORS) where applicable.

## 🧪 Current Prototype Scope

This repository demonstrates the frontend workflow. Before treating it as a live surveillance platform, connect and validate the following production services:

- A secure backend/API and database for users, cameras, profiles, and event records.
- Real camera ingestion and stream transcoding for RTSP/RTMP sources.
- Actual person/face detection and identity-matching services (not included in this repository).
- Server-side authentication, authorization, audit logs, and secure session handling.
- Encrypted storage, access controls, retention enforcement, and consent/erasure workflows for any biometric data.
- Real notification delivery and verified analytics pipelines.

**Privacy & responsible use:** Obtain appropriate consent and legal authorization before collecting or processing identifiable or biometric information. Apply data minimization, retention limits, access controls, and applicable privacy laws.

## 🛣️ Roadmap Ideas

- [ ] Backend API and database integration
- [ ] Secure role-based authentication
- [ ] RTSP ingestion through a media gateway
- [ ] Real detection pipeline and event processing
- [ ] Exportable reports and audit history
- [ ] Automated tests and deployment workflow

## 🤝 Contributing

Contributions, bug reports, and feature suggestions are welcome.

1. Fork the repository.
2. Create a branch: `git checkout -b feat/your-feature`.
3. Commit your changes: `git commit -m "Add your feature"`.
4. Push the branch and open a Pull Request.

## 📄 License

No license file is currently included. Add a `LICENSE` file to define how this project may be used, modified, and distributed.

---

<div align="center">

**STREAM CCTV** · Built for a clearer view of your security operations.

</div>
