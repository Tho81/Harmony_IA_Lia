# Technology Watch 2026 · La piel robótica deja de ser una carcasa

**HARMONY IA LÍA · Public Physical Embodiment Proposal · 20 de septiembre de 2026**

**Temas:** humanoid robotics · electronic skin · e-skin · neuromorphic tactile sensing · whole-body tactile sensing · embodied AI · proprioception · reflex control · self-damage detection · human-robot interaction

## Una frontera que empieza a converger

Durante años, gran parte de la robótica humanoide ha concentrado su progreso visible en locomoción, equilibrio, visión, manipulación y modelos de IA. Sin embargo, un cuerpo destinado a convivir con personas necesita algo más elemental: **saber qué le está ocurriendo físicamente a su propia superficie**.

El 19 de septiembre de 2026, *Gizmodo en Español* volvió a poner este problema en primer plano al divulgar una piel robótica neuromórfica capaz de distinguir tacto ordinario de estímulos potencialmente dañinos, localizar lesiones y activar respuestas protectoras. El reportaje se apoya en un trabajo científico publicado por Gao y colaboradores en *Proceedings of the National Academy of Sciences* (PNAS) a finales de 2025.

La relevancia de ese trabajo no está en atribuir “dolor” humano a una máquina. Está en algo más útil desde la ingeniería: **convertir la superficie del robot en una red capaz de detectar contacto, reconocer riesgo, localizar daño y desencadenar una respuesta local antes de que un controlador cognitivo de alto nivel tenga que deliberar**.

Ese principio coincide con una cuestión central de la propuesta pública HARMONY IA LÍA 2032–2035: una futura piel humanoide no debería ser un recubrimiento cosmético colocado encima de la robótica. Debería funcionar como parte de una **envolvente sensoriomotora**, integrada con propiocepción, control de fuerza, materiales blandos, mantenimiento y seguridad.

## De “sentir presión” a proteger el cuerpo

La NRE-skin descrita por Gao et al. introduce una arquitectura inspirada en la organización jerárquica del sistema somatosensorial. El sistema codifica estímulos táctiles dinámicos como trenes de pulsos de tipo neural, incorpora detección de estímulos excesivos con respuesta refleja local y puede localizar zonas dañadas para facilitar su sustitución modular.

Esta combinación reúne tres capacidades que históricamente se han desarrollado por separado:

1. **Tacto distribuido:** saber dónde y con qué intensidad se produce el contacto.
2. **Autoprotección:** reaccionar localmente cuando el estímulo supera un umbral seguro.
3. **Autodiagnóstico físico:** identificar qué región de la piel ha resultado dañada.

Para un humanoide doméstico, clínico, asistencial o de servicio, esa separación es decisiva. Un sistema que sólo “nota” una fuerza no necesariamente sabe si debe mantener el contacto, reducir presión, retirar una extremidad o marcar una región para mantenimiento.

## Dos velocidades para el tacto: reflejo y razonamiento

En julio de 2026, Sun et al. publicaron en *Nature Sensors* un paso complementario: una arquitectura de doble vía que procesa los mismos estímulos táctiles de dos formas.

La primera vía codifica la información como spikes para una red neuronal de respuesta rápida. La segunda transforma la información relevante en una representación que puede alimentar un modelo de lenguaje para razonamiento semántico. Un mecanismo de confianza decide cuándo basta la vía rápida y cuándo conviene recurrir a la vía cognitiva más costosa.

La consecuencia es importante para la robótica embodied: **no toda sensación necesita “pensamiento” de alto nivel**.

Un contacto rutinario puede clasificarse y responderse localmente en milisegundos. Un contacto ambiguo —por ejemplo, una interacción nueva, un material inesperado o una situación social compleja— puede escalarse a una capa cognitiva que interprete contexto y significado.

La arquitectura pública que defendemos para un humanoide sensible sigue esa misma separación conceptual:

```text
piel / sensores
      ↓
procesamiento local y reflejos
      ↓
estado corporal fusionado
      ↓
razonamiento de alto nivel cuando sea necesario
```

La idea no es que un modelo generativo controle directamente reflejos, torque o estabilidad. Es exactamente lo contrario: **la inteligencia cognitiva debe recibir un cuerpo que ya sabe protegerse en tiempo real**.

## El tacto tiene que salir de las manos

Otra limitación habitual de la robótica actual es concentrar casi todo el tacto útil en pinzas, manos o yemas. Un cuerpo que comparte espacio con personas necesita percepción más extensa.

En 2026, Tang et al. presentaron en *Nature Sensors* **EmArm**, un brazo que combina una estructura rígida, piel táctil blanda de gran superficie, propiocepción y control de circuito cerrado. El sistema consigue percepción distribuida a lo largo del brazo, interpreta interacción humana y puede replanificar trayectorias cuando entra en contacto con el entorno.

Ese resultado refuerza una transición conceptual: pasar de “sensores táctiles en la herramienta” a **un cuerpo que considera el contacto en toda su superficie como parte del control**.

La misma dirección aparece en trabajos sobre reconocimiento táctil de cuerpo completo y en sistemas modulares de e-skin que convierten miles de puntos de presión en gestos interpretables. El reto ya no es demostrar que un sensor puede detectar una presión; es integrar grandes superficies, múltiples contactos, cableado manejable, tolerancia a fallos y procesamiento en tiempo real.

## Multimodalidad: una piel no debería medir una sola cosa

La piel humana no entrega una variable única. Por eso varias líneas de investigación convergen hacia la **multimodalidad**.

El sistema SuperTac publicado en *Nature Sensors* integra presión, posición, temperatura, proximidad y vibración, además de interpretación mediante un modelo táctil especializado. Otros trabajos de 2026 añaden fuerzas tangenciales, shear, multitacto o aproximación sin contacto.

Para una piel humanoide futura, una taxonomía mínima razonable debería contemplar:

- presión normal;
- fuerzas tangenciales / shear;
- slip o deslizamiento;
- strain / deformación;
- vibración;
- temperatura;
- proximidad;
- duración del contacto;
- integridad o daño local;
- confianza de la estimación.

En las manos, estos datos pueden regular la fuerza de agarre. En brazos y torso pueden mejorar seguridad durante HRI. En pies y piernas pueden complementar equilibrio, apoyo y detección de colisiones. En una superficie amplia permiten construir un **mapa corporal dinámico de contacto**.

## El cuello de botella real: escalar sin llenar el robot de cables

La densidad sensorial introduce un problema menos visible pero crucial: cableado, multiplexación, energía, latencia y ancho de banda.

Xu et al. demostraron en 2026 una e-skin capacitiva de gran área inspirada en origami y escamas, de 60.000 mm², diseñada precisamente para obtener más resolución efectiva sin multiplicar proporcionalmente el número de sensores físicos. El trabajo combina detección de carga, shear y proximidad con aprendizaje automático para localizar contactos y estimar fuerzas.

Otra línea, publicada en *Nature Communications*, lleva parte del cómputo directamente al sensor mediante **skinomorphic computing**. La idea es procesar y comprimir información táctil cerca de donde se origina, en lugar de transmitir sin filtrar enormes matrices de datos al computador principal.

Para cuerpos humanoides completos, esto apunta a una arquitectura distribuida:

```text
taxels / regiones de piel
        ↓
electrónica local
        ↓
compresión + eventos + reflejos
        ↓
bus corporal
        ↓
fusión sensorial y body schema
        ↓
cognición
```

La piel del futuro probablemente será tanto **sensor** como **preprocesador**.

## Una piel que se daña debe saberlo

La sensibilidad pierde parte de su valor si la propia red sensorial deja de funcionar silenciosamente al sufrir un corte, pinchazo o desgarro.

Además de la NRE-skin, trabajos recientes han abordado pieles capaces de detectar daño, localizarlo e incluso recuperar funcionalidad. Un estudio de 2025 en *Device* demostró una piel electrónica multicapa capaz de identificar daños tridimensionales a escala milimétrica y utilizar materiales autorreparables. Otro trabajo en *Nature Communications* propuso redes de sensores capaces de **rerutear señales** cuando partes de la piel sufren daños severos.

Esto sugiere que “mantenibilidad” no debe tratarse como un detalle posterior. Una piel para servicio cotidiano debería diseñarse desde el inicio con:

- módulos reemplazables;
- diagnóstico por región;
- rutas de señal redundantes;
- detección de degradación;
- capas externas sacrificables;
- interfaces eléctricas/mecánicas reparables.

La piel deja así de ser una pieza monolítica para convertirse en una **infraestructura mantenible del cuerpo**.

## La convergencia que importa

Ninguno de estos trabajos, por sí solo, constituye todavía la piel humanoide completa que exige un asistente físico maduro. Pero juntos muestran una convergencia clara:

**gran superficie + multimodalidad + reflejos locales + razonamiento semántico + propiocepción + tolerancia al daño + modularidad + procesamiento distribuido.**

Esa combinación es más importante que cualquier sensor aislado.

La tesis pública HARMONY IA LÍA no plantea que una sola empresa deba investigar desde cero todos los componentes. Al contrario: el horizonte 2032–2035 parece favorecer una arquitectura interoperable en la que materiales blandos, arrays táctiles, electrónica neuromórfica, actuadores compliant, propiocepción, control determinista y modelos cognitivos puedan integrarse mediante interfaces bien definidas.

La competencia industrial puede acelerar cada componente. **La interoperabilidad puede acelerar el sistema completo.**

## Un desafío abierto para 2032–2035

La pregunta pública que proponemos a investigadores, fabricantes y desarrolladores de embodied AI es concreta:

> **¿Puede un humanoide de próxima generación disponer de una piel de gran superficie que perciba contacto multimodal, proteja el cuerpo mediante reflejos locales, detecte su propio daño, mantenga un body schema fusionado con propiocepción y escale eventos ambiguos a una capa cognitiva sin comprometer el control físico determinista?**

No hace falta que una sola organización tenga todas las respuestas.

Un fabricante de sensores puede resolver la superficie. Otro puede optimizar buses y electrónica distribuida. Otro puede desarrollar materiales reparables. Otro puede aportar actuadores compliant. Otro puede resolver control de manos. Otro puede ofrecer modelos cognitivos capaces de interpretar el contexto.

El objetivo de hacer pública esta arquitectura es sencillo: **poner una meta de integración suficientemente clara para que los avances puedan compararse, combinarse y mejorar unos a otros**.

Si en los próximos años los distintos equipos compiten por resolver mejor cada pieza, esa competencia será productiva. Si además esas piezas llegan a ser interoperables, el resultado puede avanzar mucho más rápido que cualquier desarrollo monolítico.

## Referencias principales

1. **Gao, Y. et al. (2025).** *A neuromorphic robotic electronic skin with active pain and injury perception.* Proceedings of the National Academy of Sciences, 122(52), e2520922122. DOI: https://doi.org/10.1073/pnas.2520922122

2. **Sun, H. et al. (2026).** *A spike–language dual framework bridges fast perception and deep reasoning in artificial tactile somatosensory systems.* Nature Sensors. DOI: https://doi.org/10.1038/s44460-026-00108-1

3. **Tang, Y. et al. (2026).** *Embodied sensorimotor integration for whole-arm tactile sensing and adaptive robotic manipulation.* Nature Sensors. DOI: https://doi.org/10.1038/s44460-026-00097-1

4. **Li, S. et al. (2026).** *Biomimetic multimodal tactile sensing enables human-like robotic perception.* Nature Sensors, 1, 52–62. DOI: https://doi.org/10.1038/s44460-025-00006-y

5. **Xu, Q. et al. (2026).** *A bio-inspired origami capacitive robotic e-skin with multimodal sensing capabilities.* npj Flexible Electronics, 10, 63. DOI: https://doi.org/10.1038/s41528-026-00563-3

6. **Lee, S. & Hughes, J. (2026).** *A Multimodal, Multicontact, and Scalable Soft Robot Skin Enabled by Layered Structures.* Soft Robotics. DOI: https://doi.org/10.1177/21695172261485887

7. **Ozaki, T., Ohta, N. & Fujiyoshi, M. (2025).** *Self-rerouting sensor network for electronic skin resilient to severe damage.* Nature Communications, 16, 1196. DOI: https://doi.org/10.1038/s41467-025-56596-1

8. **A damage-perceptive, self-healing electronic skin with millimeter resolution (2025).** Device, 3(8), 100802. DOI: https://doi.org/10.1016/j.device.2025.100802

9. **Massively parallel in-sensor skinomorphic computing (2026).** Nature Communications, 17, 4971. DOI: https://doi.org/10.1038/s41467-026-71697-1

10. **Gizmodo en Español (19 Sep 2026).** Reportaje de divulgación sobre NRE-skin y percepción de daño: https://es.gizmodo.com/pasamos-siglos-intentando-que-las-maquinas-no-se-rompan-ahora-les-estamos-ensenando-a-sentir-dolor-cuando-se-rompen-reaccionar-como-si-tuvieran-cuerpo-propio-2000214322

## Nota de alcance

Este documento compara literatura pública con la tesis pública de embodiment físico de HARMONY IA LÍA. No afirma afiliación con los autores, universidades, revistas o empresas citadas. Tampoco publica software privado, arquitectura cognitiva interna, datos personales, datasets, voces, prompts, credenciales ni metodologías propietarias.

La fecha de publicación de una referencia científica debe distinguirse de la fecha en que un medio de comunicación la divulga. El reportaje de Gizmodo de septiembre de 2026 comenta un trabajo científico publicado originalmente en diciembre de 2025.
