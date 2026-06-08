# ✋ Air Gesture Smart Coffee Menu

> **A touchless, AI-assisted coffee ordering experience — controlled entirely by your hand gestures via webcam.**

Built for the **[Microsoft Agents League: Creative Apps Battle](https://aka.ms/AgentsLeague/AISF)** hackathon, this project demonstrates how **GitHub Copilot** can accelerate the development of creative, real-time AI-powered web applications from concept to working demo.

---

## 🎥 Demo

[![Watch the Demo](https://img.shields.io/badge/▶%20Watch%20Demo-YouTube-red?style=for-the-badge&logo=youtube)](https://youtu.be/bb0vAKcl-7g)

> _Point your index finger at menu items. Hover for 1 second to select. Pinch and drag ingredients to the drop zone. Get an itemised bill. Order your custom drink — no keyboard or mouse required._

---

## 🤖 How GitHub Copilot Powered This Project

This project was built **end-to-end with GitHub Copilot** as the primary development tool:

| Task | How Copilot Helped |
|---|---|
| **MediaPipe integration** | Generated the `onResults()` hand landmark callback and camera loop boilerplate |
| **Gesture engine logic** | Suggested the hitbox collision detection and dwell timer pattern |
| **UI scaffolding** | Created the 3-column CSS grid layout and menu item components |
| **Recipe state machine** | Wrote the `currentRecipe` object and `executeItemIntegration()` logic |
| **Canvas rendering** | Generated the progress arc drawing code (`arc()` with `percentComplete`) |
| **Bug fixing** | Identified mirrored coordinate issue (`1 - indexFingerTip.x`) for webcam flip |
| **Drag-and-drop** | Suggested pinch detection via thumb-index distance threshold |
| **Billing system** | Generated itemised receipt, price lookup, and order counter logic |
| **Order history** | Wrote session-based history panel with last 5 orders |

> GitHub Copilot reduced development time by approximately **60%** — turning what would have been days of MediaPipe API research into hours of iterative refinement.

---

## 🏗️ Architecture

![Architecture Diagram](architecture_diagram.jpg)

### How it works

```
User's Hand
    │
    ▼
Webcam (getUserMedia)
    │  video frames
    ▼
MediaPipe Hands (CDN)
    │  21 landmark coordinates (x, y, z)
    ▼
Gesture Engine
    ├── Hitbox collision detection
    ├── Dwell timer (1 second hover = select)
    └── Pinch drag-and-drop (thumb-index distance < 35px)
    │
    ├──► Canvas Overlay (finger cursor, progress arc, webcam ghost)
    │
    └──► Menu UI DOM
            ├── Cup type selector (Tea ₹20 / Coffee ₹30 / Cold ₹35)
            ├── Water base selector
            ├── Mixins / Additives (multi-select)
            ├── Powders (multi-select)
            ├── Itemised bill with auto total
            ├── Order number (#001, #002...)
            ├── Order history panel (last 5 orders)
            └── Order / Reset / Cancel actions
```

### Tech Stack

| Layer | Technology |
|---|---|
| AI development | GitHub Copilot |
| Hand tracking | MediaPipe Hands (via CDN) |
| Rendering | HTML5 Canvas API |
| UI | Vanilla JS + CSS Grid |
| Deployment | Single `.html` file — zero dependencies, zero server |

---

## ✨ Features

- **👆 Dwell-to-select** — hover your index finger over any item for 1 second to activate it
- **🤌 Pinch drag-and-drop** — pinch (thumb + index) to grab an ingredient and release over the drop zone
- **☕ Custom drink builder** — mix any combination of cup type, water base, additives, and powders
- **💰 Live pricing** — every item shows a price in ₹, updated in real time as you build
- **🧾 Itemised bill receipt** — full breakdown of each item with individual prices and grand total
- **🔢 Order numbering** — auto-increments (#001, #002...) with timestamp per order
- **📋 Order history panel** — tracks last 5 orders in the session with drink name, time, and total
- **📷 Webcam ghost overlay** — semi-transparent camera feed as spatial context
- **🔄 Real-time hitbox recalculation** — UI layout dynamically mapped after each render
- **♿ Touchless interface** — fully accessible for users who cannot use traditional input devices

---

## 🚀 Getting Started

No installation. No server. No dependencies.

```bash
# Clone the repo
git clone https://github.com/Gomathi-devaraj/air-gesture-coffee-menu.git

# Open in browser
open air-gesture-coffee-shop.html
```

Or simply **download** `air-gesture-coffee-shop.html` and open it in Chrome/Edge.

> ⚠️ **Camera permission required.** Allow webcam access when prompted. Works best in good lighting with a plain background.

### Requirements

- Modern browser (Chrome 90+, Edge 90+)
- Webcam
- Good lighting

---

## 📁 Project Structure

```
air-gesture-coffee-menu/
│
├── air-gesture-coffee-shop.html   # Entire application (single file)
├── architecture_diagram.jpg       # System architecture diagram
└── README.md                      # This file
```

---

## 🎯 Hackathon Context

**Challenge:** Creative Apps — Build innovative creative applications using AI-assisted development (GitHub Copilot)

**Problem solved:** Traditional touchscreen coffee kiosks require physical contact — unhygienic in public spaces and inaccessible to users with motor impairments. This app demonstrates a **gesture-first ordering interface** that is completely touchless, generates an itemised bill, tracks order history, and requires zero server infrastructure.

**Judging criteria addressed:**

| Criterion | Weight | Implementation |
|---|---|---|
| ✅ Accuracy & Relevance | 20% | Fully meets Creative Apps challenge — built with GitHub Copilot |
| ✅ Reasoning & Multi-step Thinking | 20% | Gesture → hitbox → dwell → state → bill pipeline |
| ✅ Creativity & Originality | 15% | Novel gesture UI for a real-world kiosk scenario |
| ✅ User Experience & Presentation | 15% | Live pricing, itemised bill, order history, progress arc |
| ✅ Reliability & Safety | 20% | Graceful fallback if no hand detected; camera error handling |

---

## 👩‍💻 Author

**Gomathi Devaraj**
- 🔗 [LinkedIn](https://linkedin.com/in/gomathi-devaraj-09a98124a/)
- 💼 [Portfolio](https://gomathi-devaraj.github.io/Gomathi-Portfolio/)
  

---

## 📄 License

MIT License — feel free to fork, build, and extend.

---

*Built with ☕ and GitHub Copilot for Microsoft Agents League @ AI Skills Fest 2026*
