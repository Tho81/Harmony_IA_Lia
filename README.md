<div align="center">
  <img src="assets/harmony-ia-lia-logo.webp" alt="HARMONY IA LÍA" width="720">

# HARMONY IA LÍA
## Propuesta pública de embodiment humanoide · horizonte 2032–2035

**Las piezas ya existen. El reto es integrarlas.**

[Web del proyecto](https://harmonyialia.com/) · [Nota técnica](docs/01_DESIGN_THESIS.md) · [English summary](README.en.md)
</div>

---

### Resumen

**HARMONY IA LÍA** presenta una propuesta técnica pública para explorar cómo podría construirse un cuerpo humanoide de interacción avanzada combinando tecnologías que ya existen —o están en desarrollo activo— en robótica, materiales, sensorización, control y HRI.

El objetivo de este repositorio **no es publicar el software cognitivo del proyecto ni una arquitectura privada**, sino poner sobre la mesa una hipótesis de integración física suficientemente concreta para que equipos de robótica, materiales, control, piel electrónica, manipulación y expresión social puedan evaluarla, cuestionarla y mejorarla.

> **Tesis:** el salto hacia un humanoide social más convincente puede depender menos de una tecnología milagrosa que de integrar correctamente estructura ligera, actuación compliant, propiocepción, tacto distribuido, superficie sintética, expresión social y una interfaz cognitiva de alto nivel bajo una arquitectura de seguridad separada.

### Objetivo físico

Un cuerpo orientado a convivencia humana debería buscar simultáneamente:

- **baja masa e inercia distal** para mejorar seguridad y control;
- **actuación precisa y compliant** en vez de rigidez innecesaria;
- **propiocepción continua** mediante encoders, IMU y estimación de torque/fuerza;
- **e-skin multimodal** para presión, slip, strain, temperatura y vibración;
- **manos sensoriales** con control fuerza–posición;
- **rostro, mirada y microgestos legibles** para interacción humano–robot;
- **superficie sintética mantenible y reemplazable**;
- **separación estricta** entre razonamiento de alto nivel y control físico crítico;
- **plataforma de cómputo local suficiente**: 64 GB como suelo práctico, **128 GB recomendados** y margen hacia 256 GB+; **2–4 TB NVMe** como base de almacenamiento local, ampliable según modelos, mapas y telemetría.

### Envolvente sensoriomotora de cinco capas

| Capa | Función | Candidatos públicos |
|---|---|---|
| **1 · Estructura interna** | soporte, geometría, anclaje, rutas de servicio | Ti‑6Al‑4V, aluminio, CFRP |
| **2 · Sistema muscular artificial** | torque, velocidad, compliance, retorno energético | PMSM/BLDC, transmisiones de precisión, SEA/VSA según articulación |
| **3 · Red sensorial distribuida** | equivalente funcional de un sistema nervioso periférico | encoders, IMU, torque/corriente, fuerza, presión, slip, strain, temperatura |
| **4 · Dermis sintética** | distribuir cargas, amortiguar, proteger sensores, gestionar deformación | elastómeros, poliuretanos, estructuras multicapa |
| **5 · Epidermis sintética** | contacto, fricción, estética, protección ambiental | silicona/TPE y recubrimientos funcionales reemplazables |

La analogía es **funcional, no biológica**. La e-skin aporta principalmente exterocepción; la propiocepción profunda depende del estado articular e inercial. Ambas corrientes deben fusionarse para mantener un esquema corporal continuo.

### Relaciones físicas públicas de referencia

Estas expresiones son relaciones estándar de robótica y control, no algoritmos propietarios del proyecto:

```text
τ = Jᵀ F_ext
p = F / A
F_contact ≈ K Δx + D Δv
x̂_body = f(q, q̇, IMU, τ, tacto, visión)
```

Para manipulación, la meta no es maximizar fuerza sino mantener **el mínimo esfuerzo suficiente**, con margen de seguridad y realimentación táctil para detectar deslizamiento y ajustar el agarre.

### Mapa de convergencia tecnológica

Este repositorio usa productos y compañías únicamente como **referencias públicas de capacidades**, no como socios ni como afirmación de afiliación:

- **OpenAI** — modelos y agentes como candidato de capa cognitiva/orquestadora de alto nivel; el control motor crítico debe permanecer fuera del modelo generativo.
- **Tesla Optimus** — integración de equilibrio, navegación, percepción e interacción con el mundo físico.
- **Unitree G1** — locomoción humanoide, motores PMSM de baja inercia y manos con control híbrido fuerza–posición; existen arrays táctiles opcionales.
- **ENGINEAI** — plataformas humanoides dinámicas y abiertas, locomoción antropomórfica y alta densidad de torque.
- **Engineered Arts / Ameca** — referencia de HRI expresiva: rostro, mirada, gestos y microcomportamiento; la plataforma pública documenta 61 movimientos actuados y 27 DoF en cabeza/rostro.
- **Investigación e-skin** — materiales flexibles y sensorización multimodal orientados a tacto, manipulación y HRI.

Ver: [Mapa de convergencia](docs/02_CONVERGENCE_MAP.md).

### Cómputo, memoria y almacenamiento

El cuerpo necesita también una infraestructura computacional proporcional a sus sensores y a la carga cognitiva. Como referencia pública de diseño proponemos **64 GB de RAM como mínimo práctico, 128 GB como baseline recomendado y 128–256 GB+ como margen futuro**, junto con **2 TB NVMe como mínimo y 4 TB recomendados**, ampliables a 8 TB+ en plataformas de I+D. El almacenamiento debe ser SSD NVMe, cifrado y con recuperación A/B. El control motor y de seguridad debe vivir en un dominio determinista separado del computador de IA.

La plataforma NVIDIA Jetson AGX Thor de 2026 demuestra que un formato embebido de robótica ya puede integrar **128 GB LPDDR5X**, alto ancho de banda, aceleración Blackwell y redes multi-gigabit; se usa aquí solo como referencia contemporánea, no como especificación cerrada para 2032–2035.

Ver: [Compute, memory, storage and real-time domains](docs/10_COMPUTE_MEMORY_STORAGE.md).

### Propuesta de interfaz cognitiva

Una futura plataforma física podría exponer una interfaz segura a una capa cognitiva externa:

```text
Percepción + contexto
        ↓
Capa cognitiva / agente
        ↓
Intención estructurada
        ↓
Supervisor de seguridad
        ↓
Planificación de movimiento
        ↓
Control determinista / límites físicos
        ↓
Actuadores
```

La capa cognitiva puede proponer intención, lenguaje, planificación de alto nivel o selección de herramientas. **Torque, balance, colisión, límites de fuerza, E‑Stop y control de estabilidad no deben depender directamente de una salida generativa.**

### HORIZONTE 2032–2035

El horizonte 2032–2035 aquí publicado es **una dirección conceptual de diseño**, no el roadmap interno del proyecto. Busca responder una pregunta concreta:

> ¿Qué combinación de materiales, actuación, sensorización, superficie, expresión y control permitiría un cuerpo humanoide suficientemente sensible, mantenible, seguro y socialmente legible para convivir con personas?

### Qué se publica y qué no

Este repositorio contiene únicamente material deliberadamente sanitizado para publicación.

**Público:** tesis física, referencias externas, relaciones estándar de robótica, arquitectura sensoriomotora de alto nivel, fuentes y criterios de diseño.

**No publicado:** código fuente privado, memoria, prompts, datasets, voces, credenciales, rutas locales, implementación cognitiva, arquitectura interna, experimentos no liberados, metodologías propietarias y detalles que puedan crear riesgo de seguridad o de propiedad intelectual.

No existen enlaces, submódulos, tokens, acciones ni rutas de confianza hacia repositorios privados.

### Licencia y atribución

El **texto técnico original y diagramas textuales propios** de este repositorio se ofrecen bajo **Creative Commons Attribution‑ShareAlike 4.0 International (CC BY‑SA 4.0)** salvo indicación contraria. Se permite estudiar, compartir y adaptar ese material, incluso comercialmente, siempre que se atribuya la fuente y las adaptaciones se distribuyan bajo la misma licencia.

**No se concede licencia** sobre marcas, logotipos, identidad visual, material privado, software no publicado, secretos empresariales o posibles derechos de patente. Véase [LICENSE.md](LICENSE.md), [TRADEMARKS.md](TRADEMARKS.md) y [IP_NOTICE.md](IP_NOTICE.md).

Cita recomendada:

> Rivera Torrez, Nelson Marcial (2026). *HARMONY IA LÍA — Public Technical Proposal for Human-Compatible Humanoid Physical Embodiment, 2032–2035*. HARMONY IA LÍA.

### Colaboración pública

Son bienvenidos comentarios técnicos sobre:

- materiales y fatiga;
- actuadores y compliance;
- e-skin y tacto multimodal;
- propiocepción y fusión sensorial;
- control de manos y manipulación;
- HRI y expresividad;
- seguridad física y estándares;
- interoperabilidad entre agentes IA y plataformas robóticas.

No se aceptarán solicitudes de acceso a sistemas privados ni contribuciones que requieran exponerlos. Véase [CONTRIBUTING.md](CONTRIBUTING.md).

### Palabras clave / discovery

`humanoid robotics` · `embodied AI` · `electronic skin` · `e-skin` · `tactile sensing` · `proprioception` · `compliant actuation` · `dexterous manipulation` · `human robot interaction` · `HRI` · `Ti-6Al-4V` · `CFRP` · `synthetic skin` · `robot body schema` · `humanoid design` · `AI robotics`

---

© 2026 Dr. Nelson Marcial Rivera Torrez · HARMONY IA LÍA. Public technical proposal. Third-party marks belong to their respective owners.
