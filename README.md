# Unity Mobile Game Prototypes (APK + Videos)

A small collection of Unity mobile prototypes I built to improve my gameplay programming, architecture, and mobile-friendly performance practices.  
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
  - [4) Piece Assembly Puzzle — Drag & Snap](#4-piece-assembly-puzzle--drag--snap)
- [What I Focused On / What I Learned](#what-i-focused-on--what-i-learned)
- [Repo Structure](#repo-structure)
- [Notes](#notes)

---

## Downloads (APK)

- **Match-3 (8x8):** [Download APK](apks/MatchRoyaleBlastClashofTools8.2.apk)
- **Water Pump Game:** [Download APK](apks/PumpUpTheJam1.0.apk)
- **Number Puzzle:** [Download APK](apks/SlidingNumbers1.1.apk)
- **Piece Assembly Puzzle:** [Download APK](apks/PieceAssemblyPuzzle1.0.apk)

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
- [Watch video](media/Match3.mp4)
- ![Image](https://github.com/user-attachments/assets/53e2e5cf-79f0-4fa8-961d-02e72ffb9f59)
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
- [Watch video](https://github.com/user-attachments/assets/e2626b55-a95b-4d39-997d-3ac7881ce854)
- ![Image](https://github.com/user-attachments/assets/f29ab9d7-7377-4dcc-b47e-eb26b10eb544)

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
- [Watch video](https://github.com/user-attachments/assets/1329ceb0-7349-44db-8fb6-b5875eeb5c11)
- ![Image](https://github.com/user-attachments/assets/c6087604-de5a-4e2d-a591-81c4facda64c)

---


### 4) Piece Assembly Puzzle — Drag & Snap

A piece-assembly (jigsaw-style) puzzle prototype where the player drags scattered pieces and **snaps** them into the correct slots to complete the picture.  
This project was mainly about building a clean **drag & drop** interaction, reliable snapping rules, and a simple completion pipeline.

**Key Features**
- Touch-friendly **drag & drop** piece interaction
- **Snap-to-slot** placement with configurable tolerance (distance threshold)
- Piece shuffling / reset flow (so every session starts slightly different)
- Placement validation via **piece ↔ slot** mapping (ID-based matching)
- Lightweight feedback (highlight / front-sorting / optional SFX)

**What I Practiced**
- Unity UI + EventSystem workflows (pointer/drag handlers) and canvas coordinate conversions
- Snapping logic (distance checks, nearest slot search, locking a piece when placed)
- Keeping interaction stable on mobile (sorting order, raycast blocking, preventing double-grabs)
- Simple puzzle state tracking and **completion detection**
- Content pipeline basics (preparing piece sprites, importing textures, and organizing assets)

**Gameplay Video**
- [Watch video](media/PieceAssemblyPuzzle.mp4)
- ![Image](https://github.com/user-attachments/assets/REPLACE_WITH_YOUR_GIF_OR_IMAGE)

---


## What I Focused On / What I Learned

Across these prototypes, I improved in:
- **Data-driven gameplay architecture** (separating rules from visuals)
- Building systems that don’t rely on “Update() everywhere”
- **Input handling** with Unity’s **New Input System**
- **Async gameplay sequencing** (swap → resolve → fall → refill) without spaghetti logic
- **Object pooling** for effects and frequently spawned objects
- Real-world **asset integration** (adapting to constraints, shipping something playable)
- UI-heavy interactions: **drag & drop + snapping**, coordinate mapping, and stable touch behavior

---

## Repo Structure

```
/apks
  MatchRoyaleBlastClashofTools8.2.apk
  PumpUpTheJam1.0.apk
  SlidingNumbers1.1.apk
  PieceAssemblyPuzzle1.0.apk

/media
  Match3.mp4
  WaterPump.mp4 (or user-attachments link)
  NumberPuzzle.mp4 (or user-attachments link)
  PieceAssemblyPuzzle.mp4
  (optional) *.gif previews
```

---

## Notes
- APKs are provided for portfolio/testing purposes. On Android you may need to allow installing from unknown sources.
- Videos/GIFs can be stored in `/media` or uploaded via GitHub issues/comments to get a `user-attachments` link.

---
