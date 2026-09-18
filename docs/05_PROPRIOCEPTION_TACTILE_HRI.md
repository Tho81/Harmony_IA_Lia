# 05 · Proprioception, tactile feedback and HRI

## Two sensory streams

A useful humanoid body needs both:

**Deep proprioception**
- joint position/velocity;
- inertial state;
- motor current/torque estimate;
- internal forces and load paths.

**Surface exteroception**
- normal pressure;
- shear/slip;
- strain;
- vibration;
- temperature and contact events.

The two streams converge into body-state estimation and task control.

## Why the skin changes control

A soft sensorized surface changes more than appearance:

- friction coefficient;
- pressure distribution;
- impact energy transmission;
- sensor signal quality;
- object slip detection;
- perceived safety during human contact.

Therefore surface material, sensor layout and control tuning should be designed together.

## HRI as a physical subsystem

Human-facing motion should communicate intent before contact. Gaze, head orientation, hand preparation, body posture and facial micro-movements can function as **predictive safety signals** as well as social expression.

A face capable of expressive movement should still have hard constraints on speed, travel and collision behavior. Expressivity is an HRI layer, not an exemption from physical safety.
