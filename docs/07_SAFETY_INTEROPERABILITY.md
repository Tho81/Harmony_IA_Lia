# 07 · Safety and interoperability principles

A useful humanoid platform should fail safely and support replacement of subsystems without rewriting the entire cognitive layer.

## Safety properties

- physical E‑Stop independent from high-level software;
- bounded joint speed/torque/force;
- self-collision and human-collision supervision;
- watchdogs and heartbeat monitoring;
- graceful loss-of-network behavior;
- explicit skill authorization;
- local deterministic control for safety-critical loops;
- logging sufficient for post-event diagnosis without unnecessary personal data.

## Interoperability boundary

A portable embodiment interface should exchange **intent and state**, not raw unrestricted actuator authority.

Potential fields:

```text
intent
body_regions
motion_skill
intensity
duration
gaze_target
contact_permission
safety_state
execution_result
```

The exact transport could evolve; the architectural boundary matters more than the protocol name.

## Standards

ISO 13482 remains an important reference for personal care robots. Any real product would require a fresh, product-specific safety and regulatory analysis rather than relying on this conceptual note.
