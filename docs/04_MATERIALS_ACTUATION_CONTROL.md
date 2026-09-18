# 04 · Materials, actuation and control relationships

This note uses standard public robotics relations as design anchors. It does not disclose a proprietary controller.

## Structural selection

Material choice should be based on function and location rather than a single-material body.

Useful criteria include:

- specific strength `σ / ρ`;
- specific stiffness `E / ρ`;
- fatigue behavior;
- impact tolerance;
- thermal expansion;
- corrosion;
- repairability;
- manufacturability and joining method.

A hybrid body is therefore plausible: titanium at critical joints/nodes, aluminium or CFRP in selected links, and soft polymer systems near human contact surfaces.

## Joint force mapping

A standard relationship between external Cartesian force and joint torque is:

```text
τ = Jᵀ F_ext
```

This is useful for reasoning about contact, manipulation and how load propagates through the kinematic chain.

## Dynamic model

```text
M(q) q̈ + C(q,q̇) q̇ + g(q) + τ_fric = τ_act + Jᵀ F_ext
```

A human-compatible design should treat external contact as a normal operating condition, not merely as an ignored disturbance.

## Compliance / impedance

A conceptual local relation is:

```text
F_contact ≈ K Δx + D Δv
```

The engineering question is how much stiffness/damping belongs in mechanics and how much in control for each joint and use case.

## Manipulation

Grip control should seek the **minimum normal force that prevents slip** while staying within object- and human-safe limits. Tactile sensing closes that loop; simply raising grip force is not a general solution.

## Compute hardware is part of the body design

Physical embodiment also imposes compute, memory, storage, timing and thermal requirements. The public proposal therefore treats the onboard compute stack as another engineered subsystem, not as an external accessory. See [10 · Compute, memory, storage and real-time domains](10_COMPUTE_MEMORY_STORAGE.md).
