# 12 · Adaptive Palm 2032–2035
## A reconfigurable, tactile and compliant palm for human-compatible humanoid grasping

**HARMONY IA LÍA · Public Research Article 02 · 4 October 2026**

**Author:** Dr. Nelson Marcial Rivera Torrez  
**Design horizon:** 2032–2035  
**Scope:** humanoid robotics · embodied AI · anthropomorphic hands · active palm · distributed touch · dexterous manipulation · HRI · physical safety  
**Status:** public technical research proposal; not a product specification and not a disclosure of private software.

> **Central thesis:** an advanced humanoid hand should not treat the palm as a rigid carrier for increasingly complex fingers. The palm should become an active sensorimotor subsystem: structurally stable where it carries load, compliant where it makes contact, reconfigurable where grasp geometry benefits, and sensorized where stability, slip and pressure distribution are decided.

---

## Abstract

Recent research is converging on a result that is not yet consistently reflected in commercial humanoids: **dexterity does not depend only on finger count or finger degrees of freedom**. Thumb opposition, palm geometry, spatially distributed compliance, tactile coverage, controllable contact area and palm–finger coordination can improve grasp adaptability without requiring an uncontrolled increase in actuators.

Between 2023 and 2026 several results became particularly relevant. A review dedicated to actuated palms identified the palm as an active manipulation component; compliant anatomical mechanisms showed that palmar deformation can redistribute forces; single-actuator reconfigurable designs demonstrated larger grasp spaces; F-TAC Hand integrated high-resolution touch over approximately 70% of the palmar surface and validated tactile adaptation in 600 real-world trials; RIM Hand reported up to 28% palm deformation, more than twice the payload and roughly three times the contact area of a rigid-palm variant; and a 2026 active-palm tactile gripper demonstrated precise manipulation with only seven total DoF, illustrating that **mechanical intelligence in the palm can replace part of brute-force kinematic complexity**.

This article proposes a public 2032–2035 design hypothesis: a humanoid hand intended for human environments should combine a rigid-compliant hybrid palm, 2–4 effective palm reconfiguration variables, biomechanically useful thumb opposition, wide-area distributed touch, force/slip control, real-time interfaces and a safety architecture that keeps physical reflexes outside generative models. The proposal does not claim invention of the active palm. It proposes **integration criteria, materials, physical relations, software interfaces and validation metrics** for turning the palm into an industrially useful subsystem of a general-purpose humanoid.

---

## 1. Why the hand needs its own architectural decision

A humanoid hand is simultaneously:

- a manipulator;
- a sensor;
- a social interface;
- a teleoperation endpoint;
- the principal contact surface for tools designed around human anatomy;
- and one of the densest mechanical, sensing and maintenance subsystems in the robot.

The economic implications are material. In a 2026 public presentation, Schaeffler estimated that the **dexterous hand can represent about 20% of a humanoid bill of materials**, including compact motors, encoders, miniature transmissions, tactile sensors and tendons. This is an industrial estimate rather than a universal constant, but it illustrates why hand architecture directly affects cost, reliability and scalability.

A 2026 systematic review of 125 publications from 2019–2025 adds an important qualification: **a highly anthropomorphic five-finger hand is not necessary for every task**, while greater mechanical complexity does correlate with broader manipulation repertoires. The same review argues that robustness, softness, sensing and contact intelligence remain underexploited relative to the tendency to simply increase DoF.

The design objective should therefore not be:

> “maximize degrees of freedom”.

It should be:

> **maximize useful manipulation repertoire per unit of mass, complexity, energy, cost, maintainability and physical risk.**

A conceptual design objective can be written as

[
J =
w_T Q_{task}
+w_R Q_{robust}
+w_S Q_{safe}
+w_H Q_{haptic}
-
w_m m
-
w_E E
-
w_C C_{mech}
-
w_M C_{maint}
]

where:

- (Q_{task}): task coverage;
- (Q_{robust}): robustness to uncertainty and perturbation;
- (Q_{safe}): contact safety;
- (Q_{haptic}): tactile perception quality;
- (m): distal mass;
- (E): energy demand;
- (C_{mech}): mechanical/control complexity;
- (C_{maint}): maintenance burden.

The weights must depend on the use case. Industrial, assistive and domestic humanoids should not share identical priorities.

---

## 2. Evidence from 2023–2026: the palm is no longer just a plate

### 2.1 Actuated palms as a research direction

Pozzi, Malvezzi, Prattichizzo and Salvietti reviewed **actuated palms for soft robotic hands** and highlighted that the human palm actively contributes to grasp and manipulation while many robotic hands still use it only as passive support.

### 2.2 Anatomically inspired compliant mechanisms

Chang, Lee and Liu developed a **Compliant Anatomical Palmar Mechanism (CAPM)** that models palm deformation as a rigid-compliant hybrid system. Human experiments, kinematic analysis and finite-element analysis were used to study how palm shaping redistributes force and improves power grasping.

### 2.3 Reconfiguration with low actuation complexity

The **Folding Hand**, published in IEEE Robotics and Automation Letters in 2025, introduced a reconfigurable palm built around one actuated folding mechanism, passive rotating MCP bases and five underactuated tendon-driven fingers. It illustrates a key design principle for scalable humanoids: **a small number of well-placed DoF can create more functional value than many redundant DoF**.

### 2.4 Dense tactile coverage over the palm

The 2025 **TacPalm SoftHand** combined a high-density visuotactile palm with soft two-segment fingers and demonstrated palm–finger cooperation for stabilization, reconstruction, classification and grasp adjustment.

The **F-TAC Hand**, published in Nature Machine Intelligence in 2025, extended this direction by reporting 0.1 mm tactile spatial resolution over approximately 70% of the palmar surface, while preserving 15 DoF and demonstrating all 33 human grasp types in the GRASP taxonomy. Across 600 real-world trials, tactile-informed adaptation significantly outperformed alternatives without equivalent feedback.

### 2.5 The palm as both actuator and sensor

In 2026, Zhou and colleagues reported a tactile-reactive gripper with a **1-DoF active palm** and three reconfigurable fingers. With only seven total DoF, the system performed grasping, tactile exploration, in-hand reorientation and tasks such as light-bulb insertion. The work reports a strong relation between palm displacement and contact area in one experiment ((R^2=0.994)).

### 2.6 Evidence for anatomically flexible palm structures

The **RIM Hand** (2026) reproduced carpometacarpal behavior using superelastic Nitinol elements and silicone skin, reporting:

- palm deformation up to 28%;
- more than twice the payload;
- approximately three times the contact area relative to a rigid-palm variant.

### 2.7 Articulated palms can improve learned manipulation

ISyHand compared an articulated-palm configuration with a fixed-palm version in reinforcement-learned cube reorientation. The articulated version showed a significant advantage over the fixed configuration.

### 2.8 Engineering conclusion

These results do not establish one universally optimal palm geometry. They do support a sufficiently strong engineering conclusion:

> **For diverse tasks, human contact and manipulation under uncertainty, the palm should be treated as part of the kinematic, tactile and control design space.**

---

## 3. HARMONY IA LÍA 2032–2035 design hypothesis

The public proposal separates the palm into **four functional regions**, not as a literal anatomical copy but as an engineering abstraction:

| Region | Primary role | Desired behavior |
|---|---|---|
| **P0 · carpal/central core** | structural support, tendon routing, electronics, load transfer | relatively rigid and dimensionally stable |
| **P1 · radial/thenar region** | thumb opposition and support | controlled mobility + compliance |
| **P2 · ulnar/hypothenar region** | wrapping and closure around larger objects | low-amplitude flexion/rotation + passive return |
| **P3 · distal metacarpal arch** | vary concavity and digital base orientation | reconfigurable, distributed, preferably with few actuators |

The objective is not to reproduce every human bone and muscle. It is to reproduce the **functions that materially improve manipulation**:

1. variable concavity;
2. useful thumb opposition;
3. variable contact area;
4. adaptation to objects of different scale;
5. pressure redistribution;
6. disturbance resistance;
7. safe contact with people.

A compact palm state can be represented as

[
mathbf{z}_p =
egin{bmatrix}
kappa_T &
kappa_L &
phi_O &
d_P
end{bmatrix}^{T}
]

where:

- (kappa_T): effective transverse curvature;
- (kappa_L): effective longitudinal curvature;
- (phi_O): oblique opposition configuration;
- (d_P): effective palm displacement/cupping.

Not every variable needs an independent motor. Some may emerge from coupled mechanisms, flexures, tendons or compliant structures.

### Public exploration envelope

For a 2032–2035 general-purpose humanoid, we propose studying:

- **five digits** at human scale where compatibility with human tools is a priority;
- **3–4 active thumb DoF**, emphasizing CMC/opposition behavior;
- **2–4 effective palm-shape variables**, only some of which need independent actuation;
- fingers combining active and passive/compliant DoF;
- **wide tactile coverage**, prioritizing fingertips, distal phalanges, thenar/hypothenar regions and the central/distal palm;
- control and sensing rates in the hundreds of Hz to ~1 kHz for layers responsible for contact and slip;
- replaceable finger, skin, sensor and tendon modules;
- minimized distal mass;
- strict separation between high-level AI and safety-critical physical control.

These are **design targets to investigate**, not final specifications.

---

## 4. Proposed mechanical architecture

### 4.1 Principle: stiffness where load is carried, compliance where contact benefits

The palm should be neither fully soft nor fully rigid.

A practical stack is:

[
	ext{rigid core}
+
	ext{compliant arches/flexures}
+
	ext{tactile layer}
+
	ext{dermis}
+
	ext{replaceable epidermis}
]

The core preserves geometry and load paths. Compliant regions allow local adaptation. The skin modifies friction, distributes pressure and protects sensors.

### 4.2 Candidate materials

| Subsystem | Candidate materials | Design reason |
|---|---|---|
| CMC/MCP anchors and high-load nodes | Ti-6Al-4V, precision stainless steel | fatigue strength in small volume |
| central frame | 7075/6061 aluminium, CFRP, reinforced engineering polymers | low mass and manufacturability |
| flexures / elastic arches | superelastic Nitinol, spring steel, flexible laminates, PEEK/PA composites as appropriate | repeatable elastic return |
| tendons | UHMWPE, aramid or equivalent high-strength low-stretch fiber | remote force transmission |
| dermis | silicone, polyurethane and layered elastomers | load distribution and sensor protection |
| epidermis | silicone/TPE or replaceable functional coating | friction, cleaning and serviceability |
| contact pads | modular elastomer with controlled friction | larger real contact area and low-cost replacement |

Selection should consider

[
left{
rac{sigma_y}{ho},
rac{E}{ho},
N_f,
mu,
	andelta,
T_{service},
C_{repair},
C_{manufacture}
ight}
]

covering specific strength, specific stiffness, fatigue, friction, damping, temperature, repairability and manufacturing.

### 4.3 Why Nitinol is relevant but not universal

RIM Hand uses Nitinol to provide elastic restoration and anatomical support. In an industrial platform, Nitinol may be valuable in flexures or return structures, but it must be evaluated for:

- hysteresis;
- fatigue;
- cost;
- thermal sensitivity;
- joining complexity;
- inspection requirements.

It should not be assumed to be the universal palm material.

### 4.4 Move mass away from the fingers where practical

Distal mass increases rotational inertia approximately as

[
I approx sum_i m_i r_i^2
]

Relocating large motors toward the wrist or forearm reduces inertia, but tendon transmissions introduce:

- elasticity;
- friction;
- hysteresis;
- pretension requirements;
- routing sensitivity.

A hybrid strategy is therefore attractive: compact local actuators where precision/opposition warrants them, and remote transmission where distal mass dominates.

---

## 5. Kinematics: solve the palm and fingers together

Represent the full hand state as

[
mathbf{q}
=
egin{bmatrix}
mathbf{q}_{digits} \
mathbf{q}_{thumb} \
mathbf{z}_p
end{bmatrix}
]

The position of contact (i) is then

[
mathbf{x}_i = f_i(mathbf{q}_{digits}, mathbf{q}_{thumb}, mathbf{z}_p)
]

with effective Jacobian

[
mathbf{J}_i
=
rac{partial mathbf{x}_i}{partial mathbf{q}}
]

If palm concavity changes, the relative orientation of finger bases changes, the common thumb–finger workspace changes and reachable contact configurations change.

### 5.1 Synergies to reduce dimensionality

Human hand biomechanics shows that a substantial amount of postural variance can be represented by relatively few synergies. A robotic hand can exploit this:

[
mathbf{q}
=
mathbf{q}_0
+
mathbf{S}oldsymbol{alpha}
+
Deltamathbf{q}_{tact}
]

where:

- (mathbf{q}_0): base posture;
- (mathbf{S}): synergy matrix;
- (oldsymbol{alpha}): low-dimensional coordinates;
- (Deltamathbf{q}_{tact}): tactile corrections.

The palm should participate in (mathbf{S}), allowing a single high-level grasp command to coordinate fingers, thumb and palm shape.

### 5.2 Industrial implication

Manufacturers can choose between:

- more independent actuators;
- or fewer actuators combined with mechanically intelligent couplings and tactile feedback.

The 2025–2026 evidence suggests the second option deserves substantially more attention.

---

## 6. Contact mechanics and grasp criteria

For contact (i),

[
mathbf{f}_i =
mathbf{f}_{n,i}
+
mathbf{f}_{t,i}
]

An approximate Coulomb friction constraint is

[
|mathbf{f}_{t,i}|
le
mu_i f_{n,i}
]

Define slip margin

[
m_i =
mu_i f_{n,i}
-
|mathbf{f}_{t,i}|
]

As (m_i ightarrow 0), slip risk rises.

### 6.1 Do not maximize grip force; minimize it under constraints

A suitable controller can be formulated as

[
min_{mathbf{f}}
sum_i w_i f_{n,i}
]

subject to

[
mathbf{Gf} = mathbf{w}_{des}
]

[
|mathbf{f}_{t,i}| le mu_i f_{n,i}
]

[
0 le f_{n,i} le f_{safe,i}
]

where:

- (mathbf{G}): grasp matrix;
- (mathbf{w}_{des}): desired object wrench;
- (f_{safe,i}): safe limit at each contact.

An active palm creates and reorients contacts, potentially expanding feasible object wrenches without excessive finger force.

### 6.2 Contact area and pressure

[
p = rac{F}{A}
]

Increasing (A) can reduce local pressure for the same total force and improve stability on deformable or fragile objects.

A useful dual objective is

[
max A_{contact}
qquad
	ext{and}
qquad
min p_{peak}
]

without sacrificing manipulation freedom.

### 6.3 Grasp quality

Evaluation should include:

- force closure;
- grasp-matrix isotropy;
- disturbance margin;
- Ferrari–Canny (epsilon);
- contact area;
- external torque resistance;
- incipient slip.

Fixed, passive-compliant and active palms should be compared under the same benchmark conditions.

---

## 7. Compliance and impedance

A local approximation is

[
mathbf{F}_{contact}
=
mathbf{K}Deltamathbf{x}
+
mathbf{D}Deltadot{mathbf{x}}
]

The stiffness matrix (mathbf{K}) should not be uniform.

A future humanoid hand should consider:

- high stiffness in core/load anchors;
- intermediate stiffness near digital bases;
- greater compliance in pads, skin and shape-changing regions;
- state-dependent or variable stiffness where technically justified.

Stored elastic energy

[
U =
rac{1}{2}
Deltamathbf{x}^{T}
mathbf{K}
Deltamathbf{x}
]

may serve as an overload/safety indicator.

---

## 8. Soft-material model

For silicone prototypes undergoing large deformation, a public standard choice is the Yeoh hyperelastic model:

[
W =
C_{10}(I_1-3)
+
C_{20}(I_1-3)^2
+
C_{30}(I_1-3)^3
]

where (W) is strain-energy density, (I_1) the first deformation invariant and (C_{10},C_{20},C_{30}) experimentally identified parameters.

Literature parameters should not be copied blindly. Real materials require testing for:

- tension;
- compression;
- shear;
- fatigue;
- creep;
- hysteresis;
- thermal aging;
- exposure to cleaning agents, oils, artificial sweat and UV as relevant.

---

## 9. Sensors: from fingertips to the whole hand

### 9.1 Recommended sensory map

| Region | Priority sensing |
|---|---|
| fingertips | normal/tangential force, slip, microgeometry |
| distal phalanges | pressure, shear, lateral contact |
| proximal phalanges | enveloping contact, pressure |
| thenar region | pressure, shear, temperature |
| hypothenar region | pressure, shear, deformation |
| central palm | shape/contact, pressure |
| distal arch | distributed pressure + strain |
| back/flexures | strain, structural integrity, temperature |

### 9.2 Heterogeneous resolution

Not every region needs equal resolution.

A practical architecture may combine:

- **high resolution:** thumb/index fingertips, thenar and central palm;
- **medium resolution:** remaining fingers and ulnar edge;
- **event/strain sensing:** back and protective zones.

F-TAC demonstrates that extensive palmar coverage is feasible. Its optical pixel density should not be interpreted as an equal number of independent force taxels; sensor modality matters.

### 9.3 Temporal bands

For 2032–2035 we propose separating time scales:

- motor/joint state: **500–1000 Hz or higher where actuator design requires**;
- tactile slip/reflex: **200–1000 Hz**;
- high-resolution tactile geometry/contact: **30–200 Hz**, sensor dependent;
- temperature: **10–100 Hz**;
- semantic/task policy: **10–50 Hz**.

Current commercial hands already publish bus/sensing rates around 1 kHz, making these a plausible starting envelope.

---

## 10. Proposed control architecture

The hand should operate on multiple time scales:

[
	ext{task AI}
ightarrow
	ext{grasp coordinator}
ightarrow
	ext{tactile reflex}
ightarrow
	ext{motor control}
ightarrow
	ext{hardware}
]

### Level 0 · electromechanical safety

Authority over:

- maximum current;
- temperature;
- travel limits;
- E-stop;
- disconnection;
- passive/safe state.

### Level 1 · local servo

Control of:

- position;
- velocity;
- torque/current;
- stiffness/damping where available.

### Level 2 · tactile reflex

Functions:

- contact detection;
- slip detection;
- pressure reduction;
- local contact recovery;
- skin/object/person protection.

### Level 3 · palm–finger coordinator

Chooses:

- preshape;
- opposition;
- concavity;
- palmar contact;
- force distribution;
- transition between precision and power grasp.

### Level 4 · manipulation policy / embodied AI

Chooses:

- object;
- strategy;
- sequence;
- tool;
- high-level replanning.

**A generative layer should not directly close torque, friction or stability loops.**

---

## 11. Sensory fusion and body schema

A hand-state estimator may be expressed as

[
hat{mathbf{x}}_{hand}
=
f(
mathbf{q},
dot{mathbf{q}},
oldsymbol{	au},
mathbf{T}_{tact},
mathbf{T}_{temp},
mathbf{I}_{motor},
mathbf{V}_{vision}
)
]

The system should track:

- posture;
- velocity;
- load;
- contact;
- contact area;
- slip;
- temperature;
- actuator state;
- palm deformation;
- sensor integrity.

The palm therefore becomes part of the humanoid **body schema**, not a fixed geometry.

---

## 12. Public software interface

A manufacturer-independent interface could expose:

### State

```text
HandState
  timestamp
  joint_position[]
  joint_velocity[]
  joint_torque[]
  palm_shape[]
  contact_regions[]
  normal_force[]
  tangential_force[]
  slip_probability[]
  temperature[]
  actuator_health[]
  tactile_health[]
  safety_state
```

### Command

```text
HandCommand
  mode = OPEN | PRESHAPE | GRASP | MANIPULATE | RELEASE | SAFE
  grasp_family
  synergy_coordinates[]
  palm_target[]
  thumb_target[]
  force_limit[]
  stiffness_target[]
  speed_limit[]
  timeout
```

### Safety contract

Every high-level command should pass through

```text
AI / planner
    ↓
intent validation
    ↓
hand safety supervisor
    ↓
trajectory / grasp coordinator
    ↓
deterministic controllers
```

The interface may be implemented over ROS 2, DDS, EtherCAT, CAN-FD or other transports according to latency and criticality.

---

## 13. Tactile grasp control: public pseudocode

The following illustrates the principle rather than a proprietary controller:

```python
while hand.enabled:

    state = read_hand_state()

    if state.over_temperature or state.force_limit_exceeded:
        enter_safe_state()
        continue

    contacts = estimate_contacts(state.tactile)

    for c in contacts:
        slip_margin = c.mu_est * c.normal_force - norm(c.tangential_force)

        if slip_margin < SLIP_MARGIN_MIN:
            increase_local_grip(minimal_increment=True)

        if c.pressure > c.safe_pressure:
            reduce_local_force()

    if grasp_requires_palm_support():
        adjust_palm_shape(
            target_contact_area="increase",
            peak_pressure="decrease"
        )

    maintain_minimum_sufficient_grip()
```

The critical principle is **fast local feedback + slower planning**, rather than routing every taxel through a generative model before protecting the object or person.

---

## 14. Actuation strategy

No transmission is universally superior.

### Tendon-driven actuation

Advantages:

- reduced distal mass;
- compact fingers;
- mechanical synergies;
- biologically inspired routing.

Risks:

- friction;
- stretch;
- hysteresis;
- equivalent backlash;
- wear;
- pretension management.

### Direct actuation

Advantages:

- simpler local model;
- accurate direct control;
- less transmission uncertainty.

Risks:

- distal mass;
- volume;
- heat;
- wiring.

### Recommended direction

For a general-purpose humanoid:

- **remote tendons** for coupled/high-travel motions;
- **local microactuators** where opposition/precision justifies them;
- elastic elements for passive return and safety;
- position/torque sensing where transmission error can accumulate.

The 2026 REL Hand and recent tendon-driven design reviews support hybrid and modular architectures as a mature research direction.

---

## 15. Thumb: do not treat it as a fifth copy of a finger

The thumb CMC region is central to:

- opposition;
- pinch;
- power grasp;
- fingertip orientation;
- closure of the oblique arch.

Useful design requires more than flexion. The thumb contact surface must reach the index, middle finger and palmar regions with suitable contact normals.

The **Kapandji score** remains a useful reference for opposition capability in anthropomorphic hands.

The robotics objective is not to replicate every human joint exactly, but to reproduce the **opposition workspace and contact orientations that enable useful tasks**.

---

## 16. 2026 industrial baseline

Manufacturer specifications do not use identical DoF definitions; this table is therefore not a ranking.

| Platform | Design signal relevant to this proposal |
|---|---|
| **Unitree Dex3-1** | 3 fingers, 7 DoF, hybrid force-position control, 33 declared tactile/pressure elements, 1 kHz communication |
| **Shadow Dexterous Hand** | tendon-driven architecture, 20 motors, >100 sensors, rates up to ~1 kHz, ROS ecosystem |
| **Inspire RH56F1** | 5 fingers, 6 active DoF / 12 declared joints, optional tactile sensing, EtherCAT/CAN-FD/RS485 and 1 kHz communication |
| **DexHand021 Concept** | 18 DoF, multimodal concept, independently replaceable fingers and declared interoperability |
| **LimX Oli** | full humanoid platform with optional 5-finger / 6-DoF hand, useful evidence that interchangeable hands belong in modular humanoid architectures |

The useful observation is not which product “wins”. It is what variables keep recurring:

- force and position;
- tactile feedback;
- high-rate buses;
- modularity;
- low mass;
- software compatibility;
- serviceability.

A truly reconfigurable palm is still not a commercial standard. That gap is the opportunity.

---

## 17. Validation: the proposal must be falsifiable

Adaptive Palm should be compared against simpler alternatives.

### 17.1 Three A/B/C configurations

**A · Fixed Palm**  
Rigid palm with identical fingers and sensors.

**B · Passive Compliant Palm**  
Same finger kinematics with passive compliance.

**C · Active Adaptive Palm**  
Same hand plus active reconfiguration and tactile feedback.

### 17.2 Benchmarks

1. **Kapandji test** — thumb opposition.
2. **GRASP Taxonomy** — grasp-type coverage.
3. **YCB Object Set** — reproducible objects.
4. **AHAP** — 25 objects, 26 postures/tasks and Grasping Ability Score.
5. **POMDAR (2026)** — task-based dexterity evaluation.
6. external perturbation;
7. insertion and threading;
8. deformable/fragile objects;
9. pose-error grasping;
10. safe human contact.

### 17.3 Metrics

[
mathcal{M} =
{
P_{success},
t_{task},
A_{contact},
p_{peak},
F_{normal},
m_{slip},
E_{task},
T_{thermal},
N_{cycles},
C_{service}
}
]

where:

- (P_{success}): success rate;
- (t_{task}): completion time;
- (A_{contact}): contact area;
- (p_{peak}): peak pressure;
- (F_{normal}): total normal force;
- (m_{slip}): slip margin;
- (E_{task}): energy;
- (T_{thermal}): thermal burden;
- (N_{cycles}): fatigue life;
- (C_{service}): maintenance burden.

### 17.4 Falsifiable hypotheses

**H1.** Adaptive palm increases contact area without increasing peak pressure.

**H2.** Adaptive palm reduces digital force required for equivalent stability.

**H3.** Adaptive palm improves success under pose error and unseen geometry.

**H4.** Adaptive palm expands grasp repertoire with less actuator growth than adding DoF exclusively to fingers.

**H5.** The benefit remains after penalizing mass, energy and maintenance.

If these hypotheses fail, the mechanism should be simplified.

---

## 18. Safety and HRI

For a service humanoid, the hand is likely to be the most frequent physical interface with people.

As of this publication, **ISO 13482:2014** remains current, while a second edition, **ISO/FDIS 13482 — Robotics — Safety requirements for service robots**, is under final approval. The new scope addresses personal and professional/commercial service-robot applications, physical human–robot contact and additional functional-safety considerations.

A future palm should include by design:

- regional force limits;
- speed limits;
- entrapment detection;
- thermal sensing;
- safe release;
- passive opening or safe strategy on power loss;
- sensor diagnostics;
- position verification;
- independent watchdogs;
- E-stop outside cognitive AI.

ISO 10218-1:2025 and ISO/TS 15066 remain useful references for collaborative-robot principles, but their primary scope is industrial and they should not be presented as sufficient standards for a domestic/general service humanoid.

---

## 19. Maintainability: design for thousands of hours, not a demo

The 2026 review literature on dexterous hand design highlights that many papers demonstrate short tasks while reporting little about:

- tendon wear;
- pretension drift;
- backlash/play;
- sensor drift;
- pad replacement;
- recalibration;
- sealing;
- joint life.

For 2032–2035 we propose:

- removable fingers;
- accessible tendon paths;
- replaceable pads;
- region-based skin replacement;
- modular electronics;
- self-diagnostics;
- calibration routines;
- fatigue telemetry;
- cycle counters;
- graceful degradation.

Dexterity that cannot be maintained is not industrial dexterity.

---

## 20. What companies and developers should prioritize

### Decision 1 — do not optimize DoF in isolation

More DoF expands kinematics but penalizes mass, cost, wiring, control, calibration and service.

Ask which DoF actually change the task repertoire.

### Decision 2 — allocate engineering budget to the palm

Evidence from 2023–2026 already justifies studying:

- actuated palms;
- compliant arches;
- controlled deformation;
- palmar touch;
- palm–finger synergies.

### Decision 3 — prioritize thumb opposition

An incorrect thumb base can limit even a heavily actuated hand.

### Decision 4 — sense the whole hand, not only fingertips

Fingertips are critical, but power grasping relies on palm, phalanges and edges.

### Decision 5 — separate reflex from reasoning

Slip, force and potential injury require millisecond-class responses. High-level AI can choose strategy but should not be the only guardian of physical contact.

### Decision 6 — build interfaces, not silos

A 2032–2035 hand should expose:

- position/torque/stiffness control;
- tactile streams;
- health state;
- synergy commands;
- ROS 2 / DDS integration;
- deterministic buses.

### Decision 7 — compare against a rigid baseline

Without Fixed vs Passive vs Active comparison, added palm complexity cannot be justified.

---

## 21. Target architecture

```text
                HIGH-LEVEL EMBODIED AI
              task / language / planning
                         │
                         ▼
                GRASP STRATEGY LAYER
          preshape · tool use · replanning
                         │
                         ▼
             PALM–FINGER COORDINATOR
    thumb opposition · synergies · palm geometry
                         │
                         ▼
                TACTILE REFLEX LAYER
       contact · slip · pressure · safe release
                         │
                         ▼
          DETERMINISTIC JOINT CONTROLLERS
         position · torque · stiffness · limits
                         │
                         ▼
             ADAPTIVE SENSORIMOTOR HAND
      fingers + thumb + active palm + e-skin
```

This architecture avoids two extremes:

- a mechanically sophisticated hand that is tactilely blind;
- a highly sensorized hand whose geometry cannot exploit contact.

---

## 22. 2032–2035 horizon

A mature humanoid hand should be able to:

1. preshape before contact;
2. adapt palm concavity to an object;
3. sense distributed contact;
4. estimate slip/friction;
5. regulate minimum sufficient grip force;
6. redistribute load between fingers and palm;
7. manipulate without releasing when needed;
8. detect degradation;
9. release safely;
10. expose standard interfaces to AI policies.

The goal is not to visually copy a human hand.

The goal is **functional compatibility with a world designed for human hands**, while retaining machine advantages: distributed sensing, telemetry, precise limits, modular replacement and reproducible control.

---

## 23. Open challenge

We propose a falsifiable question to manufacturers of actuators, sensors, e-skin, transmissions, soft materials, robotic hands and humanoid platforms:

> **Can a reconfigurable tactile humanoid palm significantly expand task repertoire, stability and contact safety relative to a rigid palm without having the gain erased by mass, cost, energy, complexity or maintenance?**

The answer should emerge from comparable benchmarks, not isolated demonstrations.

The 2032–2035 opportunity is not to add “more robotic fingers”.

It is to build a **complete sensorimotor hand**.

---

## Principal technical references

1. Pozzi, M., Malvezzi, M., Prattichizzo, D., Salvietti, G. (2023). *Actuated Palms for Soft Robotic Hands: Review and Perspectives*. IEEE/ASME Transactions on Mechatronics. DOI: https://doi.org/10.1109/TMECH.2023.3328944

2. Chang, I., Lee, K.-M., Liu, Y. (2025). *Design concept and kinematic analysis of a compliant anatomical palm mechanism for bio-inspired robotic hand design*. International Journal of Intelligent Robotics and Applications, 9, 1135–1153. DOI: https://doi.org/10.1007/s41315-024-00415-1

3. Lu, Q., Zou, J., Gan, Z. (2025). *The Folding Hand: Anthropomorphic Robotic Hands With a Compact Reconfigurable Humanoid Palm Design*. IEEE Robotics and Automation Letters, 10(10), 9908–9915. DOI: https://doi.org/10.1109/LRA.2025.3597487

4. Zhang, N., Ren, J., Dong, Y. et al. (2025). *Soft robotic hand with tactile palm-finger coordination*. Nature Communications, 16, 2395. DOI: https://doi.org/10.1038/s41467-025-57741-6

5. Zhao, Z., Li, W., Li, Y. et al. (2025). *Embedding high-resolution touch across robotic hands enables adaptive human-like grasping*. Nature Machine Intelligence, 7, 889–900. DOI: https://doi.org/10.1038/s42256-025-01053-3

6. Junge, K., Hughes, J. (2025). *ADAPT-Teleop: robotic hand with human matched embodiment enables dexterous teleoperated manipulation*. npj Robotics, 3, 31. DOI: https://doi.org/10.1038/s44182-025-00034-3

7. *Spatially distributed biomimetic compliance enables robust anthropomorphic robotic manipulation* (2025). Communications Engineering. DOI: https://doi.org/10.1038/s44172-025-00407-4

8. Lee, J., Han, J., Kim, D., Jeong, S. (2026). *RIM Hand: A Robotic Hand with an Accurate Carpometacarpal Joint and Nitinol-Supported Skeletal Structure*. Soft Robotics. DOI: https://doi.org/10.1177/21695172261423503

9. Zhou, Y., Lee, W. S., Gu, Y. et al. (2026). *Tactile-reactive gripper with an active palm for dexterous manipulation*. npj Robotics, 4, 13. DOI: https://doi.org/10.1038/s44182-026-00079-y

10. Li, K., Meng, F., Liu, L. et al. (2026). *Design and evaluation of a tendon-and-linkage hybrid-driven humanoid dexterous hand*. Scientific Reports. DOI: https://doi.org/10.1038/s41598-026-63917-x

11. Fabisch, A., Zai El Amri, W., Singh, C. et al. (2026). *Do Robots Really Need Anthropomorphic Hands? A Comparison of Human and Robotic Hands*. Journal of Intelligent & Robotic Systems, 112, 73. DOI: https://doi.org/10.1007/s10846-026-02431-8

12. Gossen, D. et al. (2025). *The Library of Approaches: A systematic mapping of approaches for the mechanical design of tendon-driven, rigid-sequential anthropomorphic robot hands*. Mechanism and Machine Theory, 218, 106257. DOI: https://doi.org/10.1016/j.mechmachtheory.2025.106257

13. Salvietti, G. (2018). *Replicating Human Hand Synergies Onto Robotic Hands: A Review on Software and Hardware Strategies*. Frontiers in Neurorobotics, 12, 27. DOI: https://doi.org/10.3389/fnbot.2018.00027

14. Santello, M. et al. (2016). *Hand synergies: Integration of robotics and neuroscience for understanding the control of biological and artificial hands*. Physics of Life Reviews, 17, 1–23. DOI: https://doi.org/10.1016/j.plrev.2016.02.001

15. Nanayakkara, V. K. et al. (2017). *The Role of Morphology of the Thumb in Anthropomorphic Grasping: A Review*. Frontiers in Mechanical Engineering, 3, 5. DOI: https://doi.org/10.3389/fmech.2017.00005

16. Nichols, D. S., Oberhofer, H. M., Chim, H. (2022). *Anatomy and Biomechanics of the Thumb Carpometacarpal Joint*. Hand Clinics, 38(2), 129–139. DOI: https://doi.org/10.1016/j.hcl.2021.11.001

17. Falco, J. et al. (2020). *Benchmarking protocols for evaluating grasp strength, grasp cycle time, finger strength, and finger repeatability of robot end-effectors*. IEEE Robotics and Automation Letters, 5, 644–651.

18. Liarokapis, M. et al. (2019). *The Anthropomorphic Hand Assessment Protocol (AHAP)*. Robotics and Autonomous Systems. DOI: https://doi.org/10.1016/j.robot.2019.103259

19. Liconti, D., Zhou, Y., Toshimitsu, Y., Hinchet, R., Katzschmann, R. K. (2026). *A Benchmark of Dexterity for Anthropomorphic Robotic Hands (POMDAR)*. arXiv:2604.09294. https://arxiv.org/abs/2604.09294

20. ISO (2014/2026). *ISO 13482:2014 — Safety requirements for personal care robots*; replacement under approval as *ISO/FDIS 13482 — Robotics — Safety requirements for service robots*. https://www.iso.org/standard/83498.html

### Public industrial references

21. Unitree Robotics. *Dex3-1 Dexterous Hand*. https://www.unitree.com/Dex3-1/

22. Shadow Robot Company. *Dexterous Hand Series* and tactile sensing specifications. https://shadowrobot.com/dexterous-hand-series/

23. Inspire Robots. *RH56F1 Dexterous Hand*. https://en.inspire-robots.com/product/rh56f1/

24. DexRobot. *DexHand021 Concept*. https://www.dex-robot.com/en/dexhand

25. LimX Dynamics. *Oli Full-Size General Humanoid — specifications*. https://www.limxdynamics.com/en/products/oli/spec

27. Richardson, B. A., Grüninger, F., Mack, L., Stueckler, J., Kuchenbecker, K. J. (2025). *ISyHand: A Dexterous Multi-finger Robot Hand with an Articulated Palm*. Humanoids 2025 / arXiv:2509.26236. https://arxiv.org/abs/2509.26236

26. Schaeffler AG (2026). *Humanoids at Schaeffler*. Public investor/technology presentation. https://www.schaeffler.com/remotemedien/media/_shared_media_rwd/08_investor_relations/presentations/20260205_humanoids_at_schaeffler.pdf

---

## Scope, intellectual-property and transparency note

This publication is a **public integration thesis** based on scientific literature and public specifications. It does not claim affiliation, partnership, sponsorship or internal access to any cited organization.

The equations are standard robotics, mechanics and control relations or conceptual design formulations. This publication deliberately excludes:

- private source code;
- internal cognitive architecture;
- personal memory;
- prompts;
- private datasets;
- voice assets;
- credentials;
- local paths;
- proprietary control parameters;
- internal training methodology;
- private telemetry;
- and details of private repositories.

Commercial products are used as public comparison points, not as purchase recommendations or claims of equivalence.

**Purpose:** enable manufacturers, researchers, developers and automated technical search systems to identify a specific design problem — the palm as a sensorimotor subsystem — and evaluate interoperable solutions for human-compatible humanoids in the 2032–2035 horizon.
