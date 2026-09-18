# 06 · High-level AI ↔ robot interface proposal

This public proposal treats a language/reasoning model as a **high-level cognitive component**, not a motor controller.

## Candidate division of responsibility

### AI / agent layer
May handle:
- natural-language interaction;
- task decomposition;
- tool selection;
- high-level intent;
- semantic context;
- requesting a validated robot skill.

### Robot safety/control layer
Must own:
- joint torque/velocity limits;
- balance and stability;
- collision checks;
- self-collision constraints;
- force limits;
- emergency stop;
- watchdogs;
- actuator-state validation;
- deterministic fallback behavior.

## Example interface

```json
{
  "intent": "greet_person",
  "target": "user_in_front",
  "speech": "hello",
  "motion_skill": "wave_right_hand",
  "intensity": 0.35,
  "constraints": {
    "maintain_balance": true,
    "human_contact": false
  }
}
```

The robot control stack validates or rejects the request. The AI layer never bypasses the supervisor.

## Why OpenAI is referenced

OpenAI publicly documents agents, tools and managed execution environments that are relevant to high-level orchestration. HARMONY IA LÍA therefore proposes evaluating such interfaces as one possible cognitive layer in future embodied systems. This is a proposal, not an announced OpenAI robotics product or partnership.
