# 10 · Compute, memory, storage and real-time domains

A humanoid intended to host advanced multimodal AI should not be designed only around mechanics. The body also needs a **computational nervous system** with enough local memory, storage, sensor bandwidth and deterministic safety control to support perception, planning, language, body-state estimation and maintenance.

This document defines a **public, non-proprietary hardware envelope** for the 2032–2035 design horizon. It is not a bill of materials and does not disclose private software architecture.

## 1. Compute should be split into domains

A robust design should avoid placing every function on one computer. At minimum, evaluate three domains:

### A · High-level AI / perception compute

Responsible for workloads such as:

- multimodal perception;
- language and agent reasoning;
- scene understanding;
- local model inference;
- body-schema estimation at non-safety-critical level;
- semantic memory/cache access;
- high-level task planning;
- speech, vision and HRI processing.

### B · Real-time motor and safety compute

Independent deterministic controllers should retain authority over:

- torque/current loops;
- joint position/velocity loops;
- balance and stabilization;
- contact-force limits;
- collision handling;
- watchdogs;
- emergency stop;
- safe-state transitions.

A generative model should never be the only control path for these functions.

### C · Sensor / I/O aggregation

A separate sensor and timing domain can reduce jitter and improve synchronization for:

- cameras;
- IMUs;
- encoders;
- tactile arrays;
- joint torque/force sensing;
- microphones;
- environmental sensors.

Hardware timestamping and a common time base should be considered for sensor fusion.

## 2. Working memory / RAM

For a mature embodied multimodal assistant, memory capacity should be treated as a design resource rather than an afterthought.

### Public proposal

| Tier | Unified / system memory | Intended role |
|---|---:|---|
| **Minimum practical floor** | **64 GB** | perception + speech + moderate local models + robotics stack |
| **Recommended baseline** | **128 GB** | concurrent multimodal AI, local inference, vision, mapping, HRI and development headroom |
| **High-end / future-ready** | **128–256 GB or more** | larger local multimodal models, multiple accelerators, richer world models and longer-lived sensor/model caches |

For 2032–2035, the exact number should be selected from **model footprint, memory bandwidth, thermal budget and workload concurrency**, not from capacity alone.

High bandwidth is as important as capacity. Architectures with unified CPU/GPU memory can reduce copies between perception and inference workloads.

### 2026 reference point

NVIDIA Jetson AGX Thor currently provides a useful public reference point: the T5000 configuration exposes **128 GB LPDDR5X** with **273 GB/s** memory bandwidth, while T4000 provides **64 GB**. These are current examples, not prescriptions for a 2032–2035 final platform.

## 3. Local storage

For this class of system, use **NVMe SSD**, not a mechanical hard disk.

### Public proposal

| Tier | NVMe capacity | Intended role |
|---|---:|---|
| **Minimum** | **2 TB** | OS, models, speech/vision assets, diagnostics and limited local cache |
| **Recommended** | **4 TB** | multiple model variants, logs, maps, local retrieval index, updates and rollback images |
| **Development / research** | **4–8 TB or more** | long test runs, multimodal datasets, simulation artifacts and extensive telemetry before archival |

Storage should be sized together with a retention policy. More capacity is not a substitute for data minimization.

A plausible 4 TB layout could reserve separate logical areas for:

- system + A/B recovery image;
- model weights and runtime caches;
- maps / world-state assets;
- encrypted user data;
- diagnostic telemetry;
- temporary update staging.

Prefer high-endurance TLC/industrial NVMe where continuous logging is expected, and evaluate power-loss protection for safety/diagnostic records.

## 4. Accelerator class

The high-level compute domain should include an accelerator capable of concurrent:

- transformer inference;
- vision encoders;
- depth / segmentation;
- audio processing;
- policy or world-model inference;
- local tool orchestration.

As a current 2026 reference, Jetson AGX Thor advertises up to **2070 TFLOPS FP4 sparse**, a Blackwell GPU and a 40–130 W module power envelope. A 2032–2035 design should treat this only as a contemporary baseline and expect a later generation with better performance per watt.

## 5. CPU and real-time controllers

The general-purpose CPU should be multicore and sized for robotics middleware, sensor orchestration, encryption, storage and non-GPU tasks.

Separately, the motor/safety domain should use dedicated real-time controllers or safety-capable SoCs/MCUs with:

- deterministic scheduling;
- hardware watchdogs;
- independent E-stop path;
- current/torque limit enforcement;
- safe boot/recovery behavior;
- fault isolation from the high-level AI computer.

## 6. Internal networking and buses

A humanoid of this complexity will need more than one bus class.

Candidates to evaluate by subsystem include:

- CAN-FD for distributed controllers;
- EtherCAT or TSN-class Ethernet for deterministic motion/sensor networks;
- multi-gigabit Ethernet for high-bandwidth perception and development;
- PCIe for local accelerators and NVMe;
- MIPI CSI / equivalent camera links;
- USB only where deterministic timing is not required.

Current Jetson Thor modules expose multi-25-GbE networking and PCIe Gen5 capability, showing that high-bandwidth embedded robotic backplanes are already practical in 2026.

## 7. Security hardware

The compute stack should include a hardware root of trust and support:

- secure boot;
- signed firmware and OTA images;
- encrypted storage;
- TPM/HSM-class key protection or equivalent;
- rollback protection;
- isolated credentials;
- authenticated service/update interfaces.

User data and robot-control credentials should not share an unrestricted trust domain.

## 8. Thermal design

A high-end AI computer can become one of the robot's major thermal sources. Packaging should therefore plan for:

- heat spreaders;
- vapor chamber / heat-pipe solutions;
- forced-air or sealed liquid-loop options depending on enclosure;
- thermal isolation from synthetic skin;
- temperature sensing near batteries, compute and actuators;
- graceful performance reduction rather than uncontrolled shutdown.

## 9. Redundancy and graceful degradation

A mature humanoid should be able to lose the high-level AI computer without losing the ability to stop safely.

Useful design goals include:

- independent safety controller;
- secondary low-power supervisory compute;
- watchdog heartbeat between compute domains;
- local safe-state behavior if cognition/network connectivity disappears;
- immutable recovery image;
- A/B software update slots.

## 10. Design target

The public target is therefore not merely "a powerful computer inside a robot". It is a layered computational architecture:

```text
Multimodal AI / reasoning / perception
        ↓
128 GB-class high-bandwidth memory
        ↓
2–4 TB+ encrypted NVMe model/data plane
        ↓
Safety-gated intent interface
        ↓
Independent real-time motor/safety controllers
        ↓
Deterministic buses + synchronized sensor network
        ↓
Actuators / tactile skin / body state
```

For the HARMONY IA LÍA 2032–2035 physical-design hypothesis, **128 GB RAM and 4 TB NVMe are a sensible recommended public baseline today**, while retaining architectural space for **256 GB+ memory and 8 TB+ storage** if future local models and sensor workloads justify it.
