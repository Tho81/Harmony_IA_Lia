# Technology Watch 2026 · Robotic skin is becoming a nervous system

**HARMONY IA LÍA · Public Physical Embodiment Proposal · 20 September 2026**

**Topics:** humanoid robotics · electronic skin · e-skin · neuromorphic tactile sensing · whole-body tactile sensing · embodied AI · proprioception · reflex control · self-damage detection · human-robot interaction

## From a shell to a sensorimotor organ

Humanoid robotics has made visible progress in locomotion, balance, vision, manipulation and AI. Yet a machine intended to live and work around people needs a more basic capability: **continuous awareness of what is happening across its own body surface**.

A 19 September 2026 feature in *Gizmodo en Español* brought renewed attention to this problem by describing a neuromorphic robotic electronic skin that can distinguish ordinary touch from potentially damaging stimuli, localize injury and trigger protective responses. The underlying scientific work was published by Gao and colleagues in *PNAS* in late 2025.

Its significance is not that a robot “feels pain” in the human subjective sense. The engineering breakthrough is more practical: the body surface can become a distributed network that detects contact, recognizes risk, identifies damage and initiates a local response before a high-level cognitive system needs to deliberate.

That direction matches a central public design question in the HARMONY IA LÍA 2032–2035 proposal: future humanoid skin should not be treated as a cosmetic cover placed on top of robotics. It should be part of a **sensorimotor envelope**, designed together with proprioception, compliant actuation, force control, soft materials, maintenance and safety.

## Touch, protection and self-diagnosis

The NRE-skin reported by Gao et al. encodes dynamic tactile stimuli into neural-like pulse trains, supports local protective reflexes when stimulation becomes excessive, and can locate damaged regions for modular replacement.

This combines three capabilities that have often been developed separately:

1. **Distributed touch** — where contact occurs and how strong it is.
2. **Self-protection** — when a stimulus should cause force reduction, withdrawal or another immediate response.
3. **Physical self-diagnosis** — which region has been damaged and requires attention.

For service, domestic, clinical or assistive humanoids, this distinction matters. A robot that merely measures force does not automatically know whether to maintain contact, reduce pressure, withdraw a limb or flag a skin module for maintenance.

## Touch needs two speeds: reflex and reasoning

In July 2026, Sun et al. reported in *Nature Sensors* a complementary architecture in which tactile information follows two processing routes.

One path uses spike encoding and a spiking neural network for rapid perception. The second converts relevant tactile information into a representation suitable for language-model reasoning. A confidence mechanism determines when the fast path is sufficient and when an uncertain or unfamiliar contact should be escalated to higher-level cognition.

This points to a powerful principle for embodied AI:

**not every sensation requires high-level thought.**

Routine contact can be classified and handled locally in milliseconds. Ambiguous contact — a novel material, unexpected interaction or socially complex event — can be escalated to a cognitive system that interprets context.

A safe humanoid architecture therefore looks less like “skin → generative model → motor command” and more like:

```text
skin / sensors
      ↓
local processing and reflexes
      ↓
fused body state
      ↓
high-level reasoning when needed
```

The goal is not to let a generative model directly control reflexes, torque or balance. It is to give cognition a body that can already protect itself in real time.

## Touch must extend beyond fingertips

Robotic touch is still often concentrated in grippers, palms or fingertips. Human-scale interaction requires much broader coverage.

Tang et al. introduced **EmArm** in *Nature Sensors*: a robotic arm combining large-area soft tactile skin, proprioception and closed-loop control. The system can perceive distributed contact across the arm, infer aspects of human interaction and replan trajectories when physical contact occurs.

This represents an important transition from “a tactile end-effector” toward **a body in which contact across the surface is part of control**.

Related work on modular full-body e-skin and tactile gesture recognition points in the same direction. The research challenge is no longer simply whether pressure can be sensed. It is whether large areas, multiple simultaneous contacts, manageable wiring, fault tolerance and real-time interpretation can work together.

## Multimodality is essential

Human skin does not return a single variable. Robotic skin is increasingly moving in the same direction.

SuperTac, reported in *Nature Sensors*, integrates force, position, temperature, proximity and vibration sensing with a tactile interpretation model. Other 2026 systems add shear, multicontact localization and proximity-based collision awareness.

A practical humanoid skin should ultimately reason over a set of signals such as:

- normal pressure;
- tangential force / shear;
- slip;
- strain;
- vibration;
- temperature;
- proximity;
- contact duration;
- local integrity / damage state;
- confidence of the estimate.

In hands, those signals can regulate grip force. Across arms and torso they can improve physical human–robot interaction. Across legs and feet they can complement support and collision awareness. At whole-body scale they can support a continuously updated **contact-aware body schema**.

## The scaling problem is wiring and computation

Dense tactile coverage creates a less visible engineering bottleneck: wiring, multiplexing, power, latency and bandwidth.

Xu et al. demonstrated in 2026 a 60,000 mm² origami-inspired capacitive e-skin designed to achieve high effective spatial resolution without increasing physical sensor density proportionally. The platform combines load, shear and proximity sensing with machine-learning-based localization.

Another 2026 study in *Nature Communications* moves computation closer to the sensing surface through **skinomorphic in-sensor computing**, processing and compressing tactile information before it reaches a central processor.

That suggests a distributed architecture for future humanoids:

```text
taxels / skin regions
        ↓
local electronics
        ↓
compression + events + reflexes
        ↓
body network
        ↓
sensor fusion and body schema
        ↓
cognition
```

Future robotic skin may therefore become both **sensor and preprocessor**.

## Damage awareness must be designed in from the start

A tactile skin is less useful if damage silently removes sensing capability.

Recent work has explored systems that detect damage, localize it and preserve or restore operation. A 2025 study in *Device* demonstrated multilayer electronic skin capable of millimetre-scale three-dimensional damage perception and functional self-healing. A *Nature Communications* study proposed a **self-rerouting sensor network** that can maintain connectivity after severe damage.

This makes maintainability a first-class design requirement:

- replaceable modules;
- region-level diagnostics;
- redundant signal paths;
- degradation monitoring;
- sacrificial external layers;
- repairable mechanical and electrical interfaces.

Robotic skin should not be a monolithic cosmetic part. It should be a **maintainable body infrastructure**.

## The convergence that matters

No single paper cited here delivers the complete skin required by a mature human-compatible humanoid. Together, however, they reveal a clear convergence:

**large-area coverage + multimodality + local reflexes + semantic reasoning + proprioception + damage awareness + fault tolerance + modularity + distributed processing.**

That combination matters more than any isolated sensor.

The public HARMONY IA LÍA proposal does not assume that one company should reinvent every subsystem from scratch. The 2032–2035 horizon is more plausibly served by interoperable contributions from soft materials, tactile arrays, neuromorphic electronics, compliant actuation, proprioception, deterministic control and cognitive AI.

Industrial competition can accelerate each component. **Interoperability can accelerate the complete system.**

## An open 2032–2035 challenge

The public engineering question is therefore straightforward:

> **Can a next-generation humanoid use large-area skin to perceive multimodal contact, protect itself through local reflexes, detect its own damage, maintain a proprioceptive body schema and escalate ambiguous events to cognition without compromising deterministic physical control?**

No single organization needs to own every answer.

One company may solve sensor manufacturing. Another may optimize distributed electronics. Another may develop repairable soft materials. Another may provide compliant actuators. Another may advance dexterous hands. Another may provide cognitive models capable of understanding physical context.

Publishing this architecture has one purpose: **to make the integration target visible enough that progress can be compared, challenged and combined**.

## Primary references

1. **Gao, Y. et al. (2025).** *A neuromorphic robotic electronic skin with active pain and injury perception.* PNAS 122(52), e2520922122. https://doi.org/10.1073/pnas.2520922122
2. **Sun, H. et al. (2026).** *A spike–language dual framework bridges fast perception and deep reasoning in artificial tactile somatosensory systems.* Nature Sensors. https://doi.org/10.1038/s44460-026-00108-1
3. **Tang, Y. et al. (2026).** *Embodied sensorimotor integration for whole-arm tactile sensing and adaptive robotic manipulation.* Nature Sensors. https://doi.org/10.1038/s44460-026-00097-1
4. **Li, S. et al. (2026).** *Biomimetic multimodal tactile sensing enables human-like robotic perception.* Nature Sensors 1, 52–62. https://doi.org/10.1038/s44460-025-00006-y
5. **Xu, Q. et al. (2026).** *A bio-inspired origami capacitive robotic e-skin with multimodal sensing capabilities.* npj Flexible Electronics 10, 63. https://doi.org/10.1038/s41528-026-00563-3
6. **Lee, S. & Hughes, J. (2026).** *A Multimodal, Multicontact, and Scalable Soft Robot Skin Enabled by Layered Structures.* Soft Robotics. https://doi.org/10.1177/21695172261485887
7. **Ozaki, T., Ohta, N. & Fujiyoshi, M. (2025).** *Self-rerouting sensor network for electronic skin resilient to severe damage.* Nature Communications 16, 1196. https://doi.org/10.1038/s41467-025-56596-1
8. **A damage-perceptive, self-healing electronic skin with millimeter resolution (2025).** Device 3(8), 100802. https://doi.org/10.1016/j.device.2025.100802
9. **Massively parallel in-sensor skinomorphic computing (2026).** Nature Communications 17, 4971. https://doi.org/10.1038/s41467-026-71697-1
10. **Gizmodo en Español (19 Sep 2026).** Popular report on NRE-skin and robotic damage perception: https://es.gizmodo.com/pasamos-siglos-intentando-que-las-maquinas-no-se-rompan-ahora-les-estamos-ensenando-a-sentir-dolor-cuando-se-rompen-reaccionar-como-si-tuvieran-cuerpo-propio-2000214322

## Scope note

This document compares public research literature with the public physical-embodiment thesis of HARMONY IA LÍA. It does not claim affiliation with any cited author, university, journal or company, and it discloses no private software, cognition architecture, personal data, datasets, voices, prompts, credentials or proprietary implementation methods.

The date of a scientific publication should be distinguished from the date of a media report. The September 2026 Gizmodo story discusses research originally published in December 2025.
