# Unity Mobile Game Prototypes (APK + Videos)

A small collection of Unity mobile prototypesI built to improve my gameplay programming, architecture, and mobile-friendly performance practices.  
Each project includes a playable **.apk** (Android) and a short gameplay video.

> **Author:** Atalay Şehoğlu  
> **Engine:** Unity  
> **Platform:** Android

---

## Table of Contents
- [Downloads (APK)](#downloads-apk)
- [Projects](#projects)
  - [1) Match-3 (8x8) — Data-Driven Grid + New Input System](#1-match-3-8x8--data-driven-grid--new-input-system)
  - [2) Water Pump Game — Particles + Pooling + Asset Integration](#2-water-pump-game--particles--pooling--asset-integration)
  - [3) Number Puzzle — 3x3 / 4x4 Sliding Puzzle](#3-number-puzzle--3x3--4x4-sliding-puzzle)
- [What I Focused On / What I Learned](#what-i-focused-on--what-i-learned)
- [Repo Structure](#repo-structure)
- [Notes](#notes)

---

## Downloads (APK)

- **Match-3 (8x8):** [Download APK](apks/MatchRoyaleBlastClashofTools8.2.apk)
- **Water Pump Game:** [Download APK](apks/PumpUpTheJam1.0.apk)
- **Number Puzzle:** [Download APK](apks/SlidingNumbers1.1.apk)

---

## Projects

### 1) Match-3 (8x8) — Data-Driven Grid + New Input System

A Match-3 prototype built around a **data-driven 8x8 grid** with clean separation of **logic (data)** and **visuals (view)**.  
I focused on making the core loop robust (swap → match → explode → gravity → cascade) while keeping the architecture maintainable.

**Key Features**
- 8x8 grid with deterministic cell logic
- Unity New Input System based interactions
- Combo / cascade flow (swap → resolve → fall → refill)
- Event/state driven approach (avoiding “Update-everything” patterns) for a better optimization

**Tech Notes**
- Grid logic designed to be stable under cascading changes
- Clear responsibility split: board controller, cells, tile view/animation layer
- DOTween-style animation flow

**Gameplay Video**
- Add a GIF (recommended):  
  `![Match3 Demo](./media/match3_demo.gif)`
- Or link a video:  
  [Watch video](./media/match3_demo.mp4)

---

### 2) Water Pump Game — Particles + Pooling + Asset Integration

A casual prototype where I experimented with a water/flow feel using a ready-made liquid/particle asset (I initially wanted to make metaballs myself, but switched to an asset for a realistic production approach).

**Key Features**
- Water-like visuals using particle systems / asset-based liquid rendering
- Object pooling to reduce spikes and improve runtime stability
- Practical learning: integrating third-party assets into an actual gameplay loop

**What I Practiced**
- Pooling patterns (prewarm, reuse, return-to-pool)
- Particle configuration (emission, collision, lifetime tuning)
- Clean integration layer so the asset stays replaceable later

**Gameplay Video**
- `![Water Pump Demo](./media/waterpump_demo.gif)`
- Or: [Watch video](./media/waterpump_demo.mp4)

---

### 3) Number Puzzle

A classic sliding puzzle prototype with selectable board sizes.  
The main goal was building a solid grid representation and reliable user interaction for moving tiles.

**Key Features**
- Board size variants: 3x3, 4x4, 5x5, 6x6 
- Tap/drag friendly movement logic
- Focus on UI layout consistency and spacing

**What I Practiced**
- Grid indexing & coordinate mapping
- UI layout + scaling considerations for different device resolutions
- Valid move checks and clean puzzle state handling

**Gameplay Video**
- `![Number Puzzle Demo](./media/numberpuzzle_demo.gif)`
- Or: [Watch video](./media/numberpuzzle_demo.mp4)

---

## What I Focused On / What I Learned

Across these prototypes, I improved in:
- **Data-driven gameplay architecture** (separating rules from visuals)
- Building systems that don’t rely on “Update() everywhere”
- **Input handling** with Unity’s **New Input System**
- **Async gameplay sequencing** (swap → resolve → fall → refill) without spaghetti logic
- **Object pooling** for effects and frequently spawned objects
- Real-world **asset integration** (adapting to constraints, shipping something playable)

---

