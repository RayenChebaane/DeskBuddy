# DeskBuddy — AI-Powered Smart Desk

> **Buddy Desk** is an intelligent, AI-driven desk system designed to boost productivity, support emotional well-being, and promote ergonomic health through computer vision, IoT sensors, and behavioral analysis.

---

## At a Glance

<p align="center">
  <img src="Phase%201%3A%20Research%20%26%20System%20Definition/GlobalBlockDiagram.jpg" alt="Global Block Diagram" width="700"/>
</p>
<p align="center"><em>Global Block Diagram</em></p>

<p align="center">
  <img src="Phase%201%3A%20Research%20%26%20System%20Definition/DataFlow.png" alt="Data Flow" width="700"/>
</p>
<p align="center"><em>Data Flow</em></p>

<p align="center">
  <img src="Phase%201%3A%20Research%20%26%20System%20Definition/PowerFlow.png" alt="Power Flow" width="700"/>
</p>
<p align="center"><em>Power Flow</em></p>

---

## Table of Contents

1. [Overview](#overview)
2. [Objectives / Problem Statement](#objectives--problem-statement)
3. [System Architecture](#system-architecture)
4. [Subsystems](#subsystems)
5. [Deliverables & Phases](#deliverables--phases)
6. [Constraints](#constraints)
7. [Documentation Index](#documentation-index)
8. [Repository Contents](#repository-contents)
9. [How to Use This Repo](#how-to-use-this-repo)
10. [Status / Next Steps](#status--next-steps)

---

## Overview

**DeskBuddy** (Buddy Desk) is a smart desk concept that integrates Artificial Intelligence, Computer Vision, IoT sensors, and Behavioral Analysis into a unified productivity platform. The desk recognizes its owner, detects emotional states, monitors posture, manages schedules, and creates an adaptive work environment. It communicates feedback through lighting, audio, and mobile notifications, acting as a personal productivity coach embedded in the physical workspace.

---

## Objectives / Problem Statement

Modern knowledge workers face chronic issues with focus, posture, stress, and time management. Existing solutions (apps, timers, ergonomic furniture) work in isolation and require manual intervention.

**DeskBuddy** aims to:

- **Eliminate friction** — the desk proactively detects user state without requiring any manual input.
- **Unify sensing and response** — combine vision, audio, and environmental sensors into a single coherent feedback loop.
- **Personalize over time** — use adaptive machine learning to tailor suggestions to each user's behavioral patterns.
- **Improve ergonomics and well-being** — automate posture correction, break reminders, and stress regulation.
- **Gamify productivity** — motivate users through a reward and progression system.

---

## System Architecture

The system follows a five-step pipeline:

| Step | Module | Description |
|------|--------|-------------|
| 1 | **Data Collection** | Camera, microphone, desk-movement sensors, temperature sensor, and user-interaction inputs gather raw data. |
| 2 | **Data Processing** | An embedded processing unit (TODO: confirm MCU/SBC) runs wake-word detection, face detection, and sensor fusion. |
| 3 | **AI Analysis** | An AI engine (TODO: confirm model stack) classifies emotional state, cognitive load, and productivity patterns. |
| 4 | **Decision Engine** | A rule-based + ML decision layer selects the optimal system response (lighting, audio, schedule, alerts). |
| 5 | **Feedback Output** | The selected response is delivered via smart lighting, speaker, and (optionally) mobile notifications. |

See the [Global Block Diagram](#at-a-glance) and [Data Flow diagram](#at-a-glance) above for a visual representation.

---

## Subsystems

### 1. Vision
- Captures a continuous video stream via an onboard camera.
- Performs **face detection & recognition** to authenticate the user and lock/unlock the desk.
- Runs **emotion detection** (stress, fatigue, anger, joy, hesitation, demotivation) using facial micro-expression analysis.
- Monitors **posture** and **screen distance** to generate ergonomic alerts.

### 2. Audio
- Microphone array for **wake-word detection**.
- Voice tone analysis as a secondary input to the emotion classification pipeline.
- Speaker output for auditory feedback (calm sounds, breathing exercises, break prompts).

### 3. Sensors
- **Desk movement / proximity** sensors to detect user presence and activity.
- **Temperature / environmental** sensor for ambient monitoring.
- (TODO: confirm additional sensor list — e.g., ambient light, heart rate)

### 4. Decision Engine
- Combines emotion classification, task context, and productivity data.
- Selects actions: adjust lighting, suggest a break, activate focus mode, reorder tasks.
- Implements a **Strategic Decision Assistant** for task prioritization based on deadlines and cognitive state.

### 5. Feedback Outputs
- **Smart lighting** — color and intensity adjustments per emotional state or focus mode.
- **Audio** — calm soundscapes, break prompts, breathing-exercise guides.
- **Mobile / desktop notifications** — (TODO: confirm connectivity protocol and app status).

### 6. Connectivity
- (TODO: confirm wireless protocol — Wi-Fi / BLE / MQTT)
- Synchronizes user productivity data and schedule with external services.

### 7. Power
- See [Power Flow diagram](#at-a-glance) for the full power architecture.
- (TODO: confirm power supply specs, battery backup, and rated consumption)

---

## Deliverables & Phases

| Phase | Title | Deliverables |
|-------|-------|--------------|
| **Phase 1** | Research & System Definition | Mind map, global block diagram, data-flow diagram, power-flow diagram, subsystem breakdown, workflow definition, project description document, cahier des charges (specification document). |
| **Phase 2** | Prototyping | Hardware prototype assembly, firmware bring-up, initial CV/AI experiments, integration tests. *(In progress)* |
| **Phase 3** | PCB Design | Custom PCB schematic & layout, BOM, fabrication-ready Gerber files. *(Planned)* |
| **Phase 4** | 3D Mechanical Design | Enclosure/desk CAD models, mechanical integration, final assembly documentation. *(Planned)* |

---

## Constraints

### Time
- Project is divided into four sequential phases (see above). Exact deadlines: TODO (refer to `Cahier_de_charge.pdf`).

### Budget
- Budget envelope: TODO (refer to `Cahier_de_charge.pdf` for approved budget).
- Component cost targets are tracked per phase.

---

## Documentation Index

All confirmed assets are listed below. Links use repository-relative paths.

| Asset | Location | Description |
|-------|----------|-------------|
| `GlobalBlockDiagram.jpg` | `Phase 1: Research & System Definition/` | High-level system block diagram |
| `DataFlow.png` | `Phase 1: Research & System Definition/` | End-to-end data flow between subsystems |
| `PowerFlow.png` | `Phase 1: Research & System Definition/` | Power distribution architecture |
| `Subsystems.png` | `Phase 1: Research & System Definition/` | Subsystem decomposition overview |
| `MindMap.jpg` | `Phase 1: Research & System Definition/` | Project mind map / ideation |
| `WorkflwDefinition.pdf` | `Phase 1: Research & System Definition/` | Detailed workflow definition document |
| `descrip-desk-buddy.docx` | `Phase 1: Research & System Definition/` | Functional specifications & system description |
| `Cahier_de_charge.pdf` | *(repo root)* | Full project specification / requirements document |

---

## Repository Contents

```
DeskBuddy/
├── Cahier_de_charge.pdf                      # Project specification document
├── README.md                                 # This file
│
├── Phase 1: Research & System Definition/
│   ├── GlobalBlockDiagram.jpg                # System block diagram
│   ├── DataFlow.png                          # Data flow diagram
│   ├── PowerFlow.png                         # Power flow diagram
│   ├── Subsystems.png                        # Subsystem breakdown
│   ├── MindMap.jpg                           # Project mind map
│   ├── WorkflwDefinition.pdf                 # Workflow definition
│   └── descrip-desk-buddy.docx              # Functional description & specs
│
├── Phase 2: Prototyping/                     # Hardware prototype & firmware (in progress)
├── Phase 3: PCB Design/                      # PCB schematics & layout (planned)
└── Phase 4: 3D Mechanical Design/            # CAD models & enclosure (planned)
```

> **Note:** Phases 2–4 are currently empty placeholders awaiting active development.

---

## How to Use This Repo

- **Diagrams & architecture:** All design diagrams (block diagram, data flow, power flow, subsystems) are in `Phase 1: Research & System Definition/`.
- **Specification documents:** `Cahier_de_charge.pdf` (root) and `WorkflwDefinition.pdf` (Phase 1) contain the full requirements and workflow definitions.
- **Functional description:** `descrip-desk-buddy.docx` (Phase 1) describes each subsystem's inputs, processing logic, and outputs in detail.
- **Firmware / prototyping:** Will be added to `Phase 2: Prototyping/` — TODO once active development begins.
- **PCB files:** Will be added to `Phase 3: PCB Design/` — TODO.
- **Mechanical/CAD files:** Will be added to `Phase 4: 3D Mechanical Design/` — TODO.

---

## Status / Next Steps

- [x] Phase 1: Research & System Definition — complete
  - [x] Mind map
  - [x] Global block diagram
  - [x] Data flow & power flow diagrams
  - [x] Subsystem breakdown
  - [x] Workflow definition document
  - [x] Cahier des charges
- [ ] Phase 2: Prototyping — in progress
  - [ ] Hardware prototype assembly
  - [ ] Firmware bring-up (TODO: confirm target MCU/SBC)
  - [ ] Computer vision experiments (TODO: confirm Python/OpenCV stack)
  - [ ] Sensor integration tests
- [ ] Phase 3: PCB Design — planned
- [ ] Phase 4: 3D Mechanical Design — planned