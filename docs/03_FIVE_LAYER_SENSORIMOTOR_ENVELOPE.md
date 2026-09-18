# 03 · Five-layer sensorimotor envelope

A humanoid body should not treat "skin" as a cosmetic shell. The public hypothesis is a serviceable envelope in which structure, actuation, sensing and soft materials work as one system.

## Layer 1 — internal structure

**Purpose:** carry loads, define geometry, anchor joints/actuators, route services and maintain alignment.

Candidate families:
- Ti‑6Al‑4V at highly loaded or fatigue-critical nodes;
- aluminium where machinability and cost dominate;
- CFRP in selected links where low mass and low distal inertia justify composite complexity.

## Layer 2 — artificial muscle / actuation

**Purpose:** generate torque and velocity while preserving controllable compliance.

Candidates:
- PMSM/BLDC joints;
- compact transmissions;
- series-elastic or variable-stiffness mechanisms where contact safety or force control benefits.

## Layer 3 — distributed sensory network

**Purpose:** provide the functional analogue of a peripheral sensing network.

Deep state:
- encoders;
- current/torque estimation;
- IMU;
- joint/structure force sensing.

Surface state:
- pressure;
- shear/slip;
- strain;
- vibration;
- temperature.

## Layer 4 — synthetic dermis

**Purpose:** distribute contact load, protect electronics, shape mechanical impedance and decouple sensors from hard structure.

Candidate families include elastomers, polyurethane systems, cellular structures and other soft composites compatible with embedded sensing and maintenance.

## Layer 5 — synthetic epidermis

**Purpose:** provide the replaceable human-facing contact surface: friction, environmental protection, cleanability and socially acceptable appearance.

Silicone/TPE-style systems are candidate material families, with final selection depending on tear resistance, ageing, friction, thermal behavior, cleanability and compatibility with the underlying sensors.

## Sensory fusion

Electronic skin is primarily **exteroceptive**. Whole-body proprioception still requires joint and inertial state.

```text
x̂_body = f(q, q̇, IMU, τ, tactile, vision)
```

The design target is a continuously updated body schema, not a collection of disconnected sensors.
