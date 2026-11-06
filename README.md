# NOVA-UI 🪐

> **The Production-Grade, Highly Aesthetic AI-Native UI Component System for React & Next.js.**
> 
> *Beyond simplistic chat bubbles. Built for Agentic AI, RAG Knowledge Governance, 3D Spatial Swarm Topology, and Human-in-the-Loop Intercepts.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-3178C6.svg)](https://www.typescriptlang.org/)
[![React 19](https://img.shields.io/badge/React-19.x-61DAFB.svg)](https://react.dev/)
[![Three.js](https://img.shields.io/badge/Three.js-WebGL-black.svg)](https://threejs.org/)

---

## 🌟 Why NOVA-UI?

Most modern UI libraries (Ant Design, Tailwind, Shadcn UI) were engineered for conventional CRUD apps. When engineering **production LLM and Agentic systems**, developers face unsolved user-experience dilemmas:

1. **RAG Hallucinations & The Black-Box Dilemma**: Users don't trust raw markdown answers.
2. **Autonomous Agent Drift & Dangerous Side Effects**: Agents calling tools (dropping databases, updating infrastructure, transferring funds) require **Hardened Human-in-the-Loop Gates** with live parameter overrides.
3. **Streaming Telemetry & Latency Metrics**: Real-time throughput (TPS), first-token latency (TTFT), and cost observability.
4. **Visualizing Complex Workflows**: 2D DAG pipelines and immersive **Three.js 3D Spatial Swarm Topology** for executive demos and operational monitoring.

**NOVA-UI provides production-ready, highly aesthetic components to solve these exact engineering challenges.**

---

## 📦 Components Overview

### 1. `AgentSwarm3D`
An interactive WebGL / Three.js 3D canvas mapping autonomous agents into a celestial gravity network:
- **Celestial Agent Spheres**: Glowing planetary cores with breathing halo rings that pulsate dynamically during computation.
- **Alert State Flare**: Emissive coral alert flashes when a node reaches an approval gate.
- **Bezier Energy Streams**: Flying energy particles visualizing real-time packet communication between agents.
- **Vector Memory Cloud**: A 3D spatial particle cluster representing embedding retrieval spaces.
- **Interactive Parallax**: Inertia-damped mouse dragging and raycasted holographic HUD tooltips.

```tsx
import { AgentSwarm3D, initialAIOpsSteps } from "@2889036556/nova-ui";

<AgentSwarm3D
  currentStepIndex={4}
  steps={initialAIOpsSteps}
  overallStatus="gate_approval"
  onSelectAgent={(agentId) => console.log("Selected agent:", agentId)}
/>
```

### 2. `HumanApprovalGate`
A 3-level human-in-the-loop intervention system for sensitive tool calls:
- **Level 1 (Direct Gate)**: Quick Authorize (Approve) or Emergency Terminate (Reject).
- **Level 2 (Live Parameter Override)**: Allows the human operator to edit/override parameters (e.g. timeout, target node, dry-run flags) on-the-fly before authorizing.
- **Level 3 (Step-Back & Replay)**: Step back to earlier DAG stages to re-analyze.

```tsx
import { HumanApprovalGate } from "@2889036556/nova-ui";

<HumanApprovalGate
  step={currentAgentStep}
  onIntervene={(action, overriddenParams) => {
    if (action === "override_and_approve") {
      console.log("Authorized with modified parameters:", overriddenParams);
    }
  }}
/>
```

### 3. `CitationInspector`
Ground your RAG outputs with mathematical confidence and verifiable evidence:
- **Clickable Anchor Badges**: Links directly from generated text (`[01 架构白皮书 §4.2]`).
- **Slide-over Evidence Drawer**: Shows Cosine Similarity scores, hallucination risk tiers (LOW/MED/HIGH), latency benchmarks, and the raw document snippet (`Raw Chunk`).

```tsx
import { CitationInspector } from "@2889036556/nova-ui";

<CitationInspector
  citations={citationsData}
  selectedCitationId={1}
  onSelectCitation={(id) => setSelectedCitation(id)}
  onViewSourceFullText={(item) => openDocumentModal(item.source)}
/>
```

### 4. `StreamingTerminal`
A high-precision streaming typewriter console:
- Instantaneous token rate telemetry (`tok/s`), elapsed time, token count, and TTFT tracking.
- Interactive stream controls (Pause, Resume, Abort).
- Live pulsing cursor and citation badge hooks.

```tsx
import { StreamingTerminal } from "@2889036556/nova-ui";

<StreamingTerminal
  streamedText={streamedText}
  isGenerating={isStreaming}
  isPaused={isPaused}
  telemetry={{ elapsed: 1.84, tokens: 142, ttft: "180ms", tps: "52.4 tok/s", cost: "$0.0018" }}
  promptValue={prompt}
  onPromptChange={setPrompt}
  onStart={startGeneration}
  onPause={togglePause}
  onStop={abortGeneration}
  onOpenCitationDrawer={(id) => openDrawer(id)}
/>
```

### 5. `AgentPipeline2D`
A crisp, high-density 2D DAG execution track displaying stage roles, execution durations, alert status, and manual step inspection.

---

## 🚀 Quick Start

### Installation

```bash
npm install @2889036556/nova-ui three react react-dom
```

### Basic Usage

```tsx
import React, { useState } from "react";
import {
  AgentSwarm3D,
  AgentPipeline2D,
  HumanApprovalGate,
  initialAIOpsSteps,
} from "@2889036556/nova-ui";

export default function AgentOperationsConsole() {
  const [currentStep, setCurrentStep] = useState(4);
  const [viewMode, setViewMode] = useState<"2d" | "3d">("3d");

  return (
    <div style={{ background: "#0e1013", minHeight: "100vh", color: "#fff", padding: "24px" }}>
      <div style={{ display: "flex", gap: "12px", marginBottom: "16px" }}>
        <button onClick={() => setViewMode("3d")}>3D Spatial View</button>
        <button onClick={() => setViewMode("2d")}>2D DAG Track</button>
      </div>

      {viewMode === "3d" ? (
        <AgentSwarm3D
          currentStepIndex={currentStep}
          steps={initialAIOpsSteps}
          overallStatus="gate_approval"
        />
      ) : (
        <AgentPipeline2D
          currentStepIndex={currentStep}
          steps={initialAIOpsSteps}
          overallStatus="gate_approval"
        />
      )}
    </div>
  );
}
```

---

## 🎨 Design Philosophy

NOVA-UI combines **Swiss Editorial Graphic Design** (strict typography grids, hairline borders, metric axes, and film grain) with **Sci-Fi Industrial HUD** aesthetics. It is purposefully designed for enterprise developers, AI researchers, and mission-critical operations rooms where clarity, certainty, and aesthetic authority matter.

---

## 📄 License

MIT License © 2026 杨宇 (2889036556). Open-source and free for commercial and personal use.
