# 12 · Adaptive Palm 2032–2035
## Palma reconfigurable, táctil y compliant para una mano humanoide compatible con personas

**HARMONY IA LÍA · Public Research Article 02 · 4 de octubre de 2026**

**Autor:** Dr. Nelson Marcial Rivera Torrez  
**Horizonte de diseño:** 2032–2035  
**Ámbito:** robótica humanoide · embodied AI · mano antropomórfica · palma activa · tacto distribuido · manipulación diestra · HRI · seguridad física  
**Estado:** propuesta técnica pública, no especificación de producto ni divulgación de software privado.

> **Tesis central:** una mano humanoide avanzada no debería tratar la palma como un soporte rígido para dedos cada vez más complejos. La palma debe convertirse en un subsistema sensoriomotor activo: estructuralmente estable donde carga, compliant donde contacta, reconfigurable donde mejora la geometría de agarre, y sensorizada en las regiones que determinan estabilidad, deslizamiento y reparto de presión.

---

## Resumen

La investigación reciente está convergiendo en una conclusión que todavía no se refleja de forma uniforme en los humanoides comerciales: **la destreza no depende únicamente del número de dedos o grados de libertad de los dedos**. La oposición del pulgar, la geometría de la palma, la compliance espacialmente distribuida, la cobertura táctil, la capacidad de modificar el área de contacto y la coordinación entre palma y dedos pueden aportar ganancias importantes de agarre y manipulación sin exigir una explosión de actuadores.

Entre 2023 y 2026 aparecieron resultados especialmente relevantes. Una revisión específica sobre palmas actuadas identificó la palma como componente activo de la manipulación; mecanismos anatómicos compliant demostraron que la deformación palmar puede redistribuir fuerzas; diseños reconfigurables de un solo actuador mostraron mejoras de espacio de agarre; F-TAC Hand integró tacto de alta resolución en aproximadamente el 70 % de su superficie palmar y validó adaptación táctil en 600 ensayos reales; RIM Hand informó una deformación palmar de hasta 28 %, más del doble de capacidad de carga y aproximadamente tres veces el área de contacto frente a una palma rígida; y un gripper de 2026 con palma táctil activa mostró manipulación precisa con sólo siete grados de libertad, evidenciando que **la inteligencia mecánica de la palma puede sustituir parte de la complejidad cinemática bruta**.

Este artículo formula una hipótesis pública para 2032–2035: una mano humanoide de convivencia debería combinar una estructura palmar híbrida rígido-compliant, 2–4 variables efectivas de reconfiguración palmar, oposición del pulgar biomecánicamente útil, tacto distribuido de alta cobertura, control de fuerza/deslizamiento, interfaces de tiempo real y una arquitectura de seguridad que mantenga los reflejos físicos fuera del modelo generativo. La propuesta no reivindica haber inventado la palma activa; **propone criterios de integración, materiales, relaciones físicas, interfaces y métricas de validación para convertirla en un subsistema industrialmente útil dentro de un humanoide de propósito general**.

---

## 1. Por qué la mano merece una decisión arquitectónica propia

Una mano humanoide es simultáneamente:

- manipulador;
- sensor;
- interfaz social;
- herramienta de teleoperación;
- punto principal de contacto con objetos diseñados para seres humanos;
- y uno de los subsistemas con mayor densidad mecánica, sensorial y de mantenimiento del robot.

La relevancia económica también es material. En una presentación pública de 2026, Schaeffler estimó que la **mano diestra puede representar alrededor del 20 % del coste de materiales (BOM) de un humanoide**, incluyendo motores compactos, encoders, mini-transmisiones, sensores táctiles y tendones. Es una estimación industrial, no una constante universal, pero muestra por qué la arquitectura de la mano tiene consecuencias directas sobre coste, fiabilidad y escalabilidad.

Al mismo tiempo, una revisión sistemática publicada en 2026 analizó 125 trabajos de 2019–2025 y llegó a un matiz importante: **una mano antropomórfica compleja no es necesaria para todas las tareas**, pero la complejidad mecánica sí se relaciona con la amplitud del repertorio de tareas. El mismo trabajo sostiene que robustez, suavidad, sensorización e inteligencia de contacto están todavía infraexplotadas frente a la tendencia de aumentar dedos y DoF.

Por ello, el objetivo de diseño no debería ser:

> “maximizar los grados de libertad”.

Debería ser:

> **maximizar el repertorio manipulativo útil por unidad de masa, complejidad, energía, coste, mantenimiento y riesgo físico.**

Una función conceptual de decisión puede expresarse como:

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

donde:

- (Q_{task}): cobertura de tareas;
- (Q_{robust}): robustez ante incertidumbre y perturbaciones;
- (Q_{safe}): seguridad de contacto;
- (Q_{haptic}): calidad de percepción táctil;
- (m): masa distal;
- (E): consumo energético;
- (C_{mech}): complejidad mecánica/control;
- (C_{maint}): coste de mantenimiento.

Los pesos deben depender del caso de uso. Un humanoide industrial, asistencial o doméstico no necesita la misma función objetivo.

---

## 2. Evidencia 2023–2026: la palma deja de ser una placa

### 2.1 Palma actuada como línea de investigación propia

Pozzi, Malvezzi, Prattichizzo y Salvietti revisaron las **palmas actuadas para manos robóticas blandas** y señalaron que la palma humana participa activamente en agarre y manipulación, mientras muchas manos robóticas continúan utilizándola únicamente como soporte pasivo.

### 2.2 Mecanismos anatómicos compliant

Chang, Lee y Liu desarrollaron un **Compliant Anatomical Palmar Mechanism (CAPM)** que modela la deformación de la palma como un sistema híbrido rígido/compliant. Su trabajo combina experimentos humanos, análisis cinemático y FEA para estudiar cómo el conformado de la palma redistribuye fuerzas y mejora agarres de potencia.

### 2.3 Reconfiguración con baja complejidad

La **Folding Hand** publicada en IEEE Robotics and Automation Letters en 2025 introdujo una palma reconfigurable con un solo mecanismo actuado, dedos subactuados y bases MCP pasivas. El trabajo muestra una idea central para humanoides comerciales: **una pequeña cantidad de DoF bien situada puede producir más valor que muchos DoF redundantes**.

### 2.4 Tacto de palma con alta densidad

La **TacPalm SoftHand** de 2025 integró una palma visuotáctil de alta densidad con dedos blandos de dos segmentos. El sistema mostró cooperación palma-dedo para estabilización, reconstrucción superficial, clasificación y reajuste de agarre.

La **F-TAC Hand** publicada en Nature Machine Intelligence en 2025 llevó esta dirección más lejos: informó una resolución espacial táctil de 0,1 mm y cobertura sensorial sobre aproximadamente el 70 % de la superficie palmar, manteniendo 15 DoF y capacidad para ejecutar los 33 tipos de agarre humano de la taxonomía GRASP. En 600 ensayos reales, la adaptación informada por tacto superó de forma significativa a las alternativas sin esa realimentación.

### 2.5 La palma como actuador y sensor

En 2026, Zhou y colaboradores publicaron un gripper táctil-reactivo con **palma activa de 1 DoF** y tres dedos reconfigurables. Con sólo siete DoF totales, el sistema consiguió agarre, exploración táctil, reorientación en mano y tareas como inserción de una bombilla. El artículo reporta una correlación (R^2=0.994) entre desplazamiento de la palma y área de contacto en una de sus tareas de control.

### 2.6 Evidencia de una palma anatómicamente flexible

La **RIM Hand** de 2026 reprodujo articulaciones carpometacarpianas, empleó alambres superelásticos de Nitinol y piel de silicona, e informó:

- deformación de palma de hasta 28 %;
- más del doble de capacidad de carga;
- aproximadamente tres veces el área de contacto frente a una variante de palma rígida.

### 2.7 La palma articulada mejora aprendizaje/manipulación

ISyHand comparó una versión con palma articulada frente a su propia variante de palma fija en tareas de reorientación de cubos aprendidas por refuerzo. La versión articulada mostró una ventaja significativa frente al diseño fijo.

### 2.8 Conclusión de la evidencia

Los resultados no demuestran que exista una única geometría de palma óptima. Sí respaldan una conclusión de ingeniería suficientemente fuerte:

> **Para tareas diversas, contacto humano y manipulación bajo incertidumbre, la palma debe considerarse parte del espacio de diseño cinemático, táctil y de control.**

---

## 3. Hipótesis de diseño HARMONY IA LÍA 2032–2035

La propuesta pública separa la palma en **cuatro regiones funcionales**, no como copia anatómica literal sino como abstracción de ingeniería:

| Región | Función principal | Comportamiento deseado |
|---|---|---|
| **P0 · núcleo carpal/central** | soporte, anclaje, rutas de tendones, electrónica, transmisión de carga | relativamente rígido y dimensionalmente estable |
| **P1 · región radial/tenar** | oposición y soporte del pulgar | movilidad controlada + compliance |
| **P2 · región ulnar/hipotenar** | envolvimiento, cierre sobre objetos voluminosos | flexión/rotación de baja amplitud + retorno pasivo |
| **P3 · arco metacarpal distal** | variar concavidad y orientación de bases digitales | reconfigurable, distribuido, preferiblemente con pocos actuadores |

El objetivo no es reproducir todos los huesos y músculos humanos. El objetivo es reproducir **las funciones que aportan valor**:

1. concavidad variable;
2. oposición útil del pulgar;
3. variación del área de contacto;
4. adaptación a objetos de distinta escala;
5. redistribución de presión;
6. estabilidad ante perturbaciones;
7. contacto seguro con personas.

Una representación compacta del estado de la palma puede ser:

[
mathbf{z}_p =
egin{bmatrix}
kappa_T &
kappa_L &
phi_O &
d_P
end{bmatrix}^{T}
]

donde:

- (kappa_T): curvatura transversal efectiva;
- (kappa_L): curvatura longitudinal efectiva;
- (phi_O): configuración oblicua de oposición;
- (d_P): desplazamiento/abombamiento palmar efectivo.

No es necesario que cada variable corresponda a un motor independiente. Puede emerger de mecanismos acoplados, flexuras, tendones o estructuras compliant.

### Envolvente pública propuesta

Para un humanoide 2032–2035, proponemos estudiar como punto de partida:

- **5 dedos** a escala humana cuando la compatibilidad con herramientas humanas sea prioritaria;
- **3–4 DoF activos del pulgar**, con énfasis en CMC/oposición;
- **2–4 variables efectivas de forma palmar**, de las cuales sólo una parte necesita actuadores independientes;
- dedos con una mezcla de DoF activos y pasivos/compliant;
- **cobertura táctil amplia**, priorizando yemas, falanges distales, tenar, hipotenar y centro/distal de la palma;
- transmisión y sensado con tasas de control del orden de cientos de Hz a 1 kHz para las capas que gestionan contacto/deslizamiento;
- módulos reemplazables de dedos, piel, sensores y tendones;
- masa distal minimizada;
- desacoplamiento estricto entre IA de alto nivel y control físico crítico.

Estos valores son **objetivos de exploración**, no especificaciones cerradas.

---

## 4. Arquitectura mecánica propuesta

### 4.1 Principio: rigidez donde se transmite carga, compliance donde se necesita contacto

La palma no debería ser completamente blanda ni completamente rígida.

Una arquitectura razonable es:

[
	ext{núcleo rígido}
+
	ext{arcos/flexuras compliant}
+
	ext{capa táctil}
+
	ext{dermis}
+
	ext{epidermis reemplazable}
]

El núcleo conserva precisión geométrica y rutas de fuerza. Las regiones compliant permiten adaptación local. La piel modifica fricción, distribuye presión y protege sensores.

### 4.2 Materiales candidatos

| Subsistema | Materiales candidatos | Razón de diseño |
|---|---|---|
| anclajes CMC/MCP y nodos de alta carga | Ti-6Al-4V, acero inoxidable de precisión | alta resistencia/fatiga en poco volumen |
| bastidor central | aluminio 7075/6061, CFRP, polímeros técnicos reforzados | baja masa y manufacturabilidad |
| flexuras/arcos elásticos | Nitinol superelástico, acero de muelle, laminados flexibles, PEEK/PA reforzada según carga | retorno elástico, deformación repetible |
| tendones | UHMWPE/aramida u otros cordones de alta resistencia y baja elongación | transmisión remota de fuerza |
| dermis | silicona, poliuretano y elastómeros multicapa | distribución de carga y protección sensorial |
| epidermis | silicona/TPE o recubrimiento funcional reemplazable | fricción, limpieza, tacto y mantenimiento |
| pads de contacto | elastómero de fricción controlada, modular | mayor área real de contacto y reemplazo económico |

La selección final debe basarse en:

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

es decir, resistencia específica, rigidez específica, fatiga, fricción, amortiguamiento, temperatura, reparabilidad y fabricación.

### 4.3 Por qué Nitinol es relevante pero no universal

La RIM Hand utiliza Nitinol para aportar restauración elástica y soporte anatómico. Para una plataforma industrial, Nitinol puede ser valioso en flexuras o elementos de retorno, pero debe evaluarse frente a:

- histéresis;
- fatiga por ciclos;
- coste;
- sensibilidad térmica;
- dificultad de unión;
- requisitos de inspección.

No debería adoptarse como material único de la palma.

### 4.4 Alejar masa de los dedos cuando sea posible

La masa distal incrementa inercia aproximadamente como:

[
I approx sum_i m_i r_i^2
]

Mover motores voluminosos hacia antebrazo o muñeca puede reducir inercia, pero las transmisiones por tendón introducen:

- elasticidad;
- fricción;
- histéresis;
- necesidad de pretensión;
- sensibilidad al enrutamiento.

Por ello, una solución híbrida es preferible: actuadores compactos donde la respuesta directa aporte valor y transmisión remota donde la masa sea dominante.

---

## 5. Cinemática: mano y palma deben resolverse juntas

Definimos el estado cinemático de la mano como:

[
mathbf{q}
=
egin{bmatrix}
mathbf{q}_{digits} \
mathbf{q}_{thumb} \
mathbf{z}_p
end{bmatrix}
]

La posición de un contacto (i) depende entonces no sólo de los dedos:

[
mathbf{x}_i = f_i(mathbf{q}_{digits}, mathbf{q}_{thumb}, mathbf{z}_p)
]

y su Jacobiano efectivo:

[
mathbf{J}_i
=
rac{partial mathbf{x}_i}{partial mathbf{q}}
]

Esto es importante: si cambia la concavidad palmar, cambia la orientación relativa de las bases digitales, el espacio común pulgar-dedos y el conjunto de contactos alcanzables.

### 5.1 Sinergias para reducir dimensionalidad

La biomecánica humana muestra que una parte importante de la varianza postural puede describirse mediante pocas sinergias. Una mano robótica puede explotar esa idea:

[
mathbf{q}
=
mathbf{q}_0
+
mathbf{S}oldsymbol{alpha}
+
Deltamathbf{q}_{tact}
]

donde:

- (mathbf{q}_0): postura base;
- (mathbf{S}): matriz de sinergias;
- (oldsymbol{alpha}): coordenadas de baja dimensión;
- (Deltamathbf{q}_{tact}): correcciones por tacto.

La palma puede participar en (mathbf{S}), permitiendo que un único comando de “power wrap”, “pinch” o “cage grasp” coordine dedos, pulgar y forma palmar.

### 5.2 Consecuencia industrial

Un fabricante puede elegir:

- más actuadores y control independiente;
- o menos actuadores con acoplamientos mecánicos inteligentes y realimentación táctil.

La evidencia 2025–2026 sugiere que la segunda vía merece mucha más atención de la que recibe.

---

## 6. Mecánica del contacto y criterio de agarre

Para un contacto (i):

[
mathbf{f}_i =
mathbf{f}_{n,i}
+
mathbf{f}_{t,i}
]

El criterio de fricción de Coulomb aproximado exige:

[
|mathbf{f}_{t,i}|
le
mu_i f_{n,i}
]

Definimos un margen de deslizamiento:

[
m_i =
mu_i f_{n,i}
-
|mathbf{f}_{t,i}|
]

Cuando (m_i ightarrow 0), aumenta el riesgo de slip.

### 6.1 No maximizar la fuerza: minimizarla bajo restricciones

El control deseable no es “apretar más”. Puede formularse:

[
min_{mathbf{f}}
sum_i w_i f_{n,i}
]

sujeto a:

[
mathbf{Gf} = mathbf{w}_{des}
]

[
|mathbf{f}_{t,i}| le mu_i f_{n,i}
]

[
0 le f_{n,i} le f_{safe,i}
]

donde:

- (mathbf{G}): matriz de agarre;
- (mathbf{w}_{des}): wrench deseado sobre el objeto;
- (f_{safe,i}): límite seguro por contacto.

La palma activa añade contactos y modifica sus normales. Eso puede ampliar el conjunto de wrenches realizables sin aumentar excesivamente la fuerza de los dedos.

### 6.2 Contacto y presión

[
p = rac{F}{A}
]

Una palma que aumenta (A) puede reducir presión local para la misma fuerza total y estabilizar objetos deformables o frágiles.

El objetivo debe ser doble:

[
max A_{contact}
qquad
	ext{y}
qquad
min p_{peak}
]

sin perder libertad de manipulación.

### 6.3 Calidad de agarre

La estabilidad puede evaluarse con métricas basadas en:

- force closure;
- isotropía de la matriz de agarre;
- margen de perturbación;
- Ferrari–Canny (epsilon);
- área de contacto;
- resistencia a torque externo;
- deslizamiento incipiente.

La palma fija, compliant pasiva y activa deberían compararse bajo exactamente la misma batería de pruebas.

---

## 7. Compliance e impedancia

Una aproximación local:

[
mathbf{F}_{contact}
=
mathbf{K}Deltamathbf{x}
+
mathbf{D}Deltadot{mathbf{x}}
]

La matriz de rigidez (mathbf{K}) no debería ser uniforme.

Una mano humana presenta compliance espacialmente distribuida. Para una mano humanoide futura proponemos:

- mayor rigidez en núcleo y anclajes;
- rigidez intermedia en bases digitales;
- compliance superior en pads, piel y regiones de conformado;
- rigidez regulable o dependiente del estado cuando sea técnicamente viable.

La energía elástica almacenada:

[
U =
rac{1}{2}
Deltamathbf{x}^{T}
mathbf{K}
Deltamathbf{x}
]

puede utilizarse como indicador de contacto excesivo o como parte de una función de seguridad.

---

## 8. Modelo del material blando

Para prototipos de silicona sometidos a grandes deformaciones, un modelo hiperlástico de Yeoh es una opción pública habitual:

[
W =
C_{10}(I_1-3)
+
C_{20}(I_1-3)^2
+
C_{30}(I_1-3)^3
]

donde:

- (W): densidad de energía de deformación;
- (I_1): primer invariante del tensor de deformación;
- (C_{10},C_{20},C_{30}): parámetros identificados experimentalmente.

No deben reutilizarse parámetros de literatura sin caracterizar el elastómero real. Para un diseño serio se necesitan ensayos de:

- tracción;
- compresión;
- cizalla;
- fatiga;
- creep;
- histéresis;
- envejecimiento térmico;
- interacción con aceites, sudor artificial, detergentes y UV según aplicación.

---

## 9. Sensores: de las yemas a toda la mano

### 9.1 Mapa sensorial recomendado

| Región | Sensores prioritarios |
|---|---|
| yemas | fuerza normal/tangencial, slip, microgeometría |
| falanges distales | presión, shear, contacto lateral |
| falanges proximales | contacto envolvente, presión |
| tenar | presión, shear, temperatura |
| hipotenar | presión, shear, deformación |
| centro palmar | contacto/forma, presión |
| arco distal | presión distribuida + strain |
| dorso/flexuras | strain, integridad estructural, temperatura |

### 9.2 Densidad heterogénea

No toda la mano necesita la misma resolución.

Una arquitectura eficiente puede combinar:

- **alta resolución:** yema, pulgar, índice, región tenar y centro palmar;
- **resolución media:** demás dedos y borde ulnar;
- **eventos binarios/strain:** dorso y zonas de protección.

F-TAC demuestra que una cobertura palmar extensa es técnicamente posible. No implica que todos los robots necesiten 10.000 píxeles sensoriales/cm²; esa cifra depende del principio óptico utilizado y no equivale directamente a taxels de fuerza independientes.

### 9.3 Tasas temporales

Para el horizonte 2032–2035 proponemos separar bandas:

- control motor y estado articular: **500–1000 Hz o superior según actuador**;
- slip/reflejo táctil: **200–1000 Hz**;
- geometría/contacto táctil de alta resolución: **30–200 Hz**, según sensor;
- temperatura: **10–100 Hz**;
- percepción semántica/política de tarea: **10–50 Hz**.

Productos actuales ya publican buses y sensado del orden de 1 kHz, de modo que esta separación es realista como punto de partida.

---

## 10. Arquitectura de control propuesta

La mano debe disponer de varias escalas temporales:

[
	ext{IA de tarea}
ightarrow
	ext{coordinador de agarre}
ightarrow
	ext{reflejo táctil}
ightarrow
	ext{control motor}
ightarrow
	ext{hardware}
]

### Nivel 0 · seguridad electromecánica

Autoridad sobre:

- corriente máxima;
- temperatura;
- recorrido;
- E-stop;
- desconexión;
- modo pasivo/seguro.

### Nivel 1 · servo local

Control:

- posición;
- velocidad;
- torque/corriente;
- stiffness/damping cuando exista.

### Nivel 2 · reflejo táctil

Funciones:

- detectar contacto;
- detectar slip;
- reducir presión excesiva;
- compensar pérdidas de contacto;
- proteger piel/objeto/persona.

### Nivel 3 · coordinador palma-dedos

Decide:

- preshape;
- oposición;
- concavidad;
- contacto palmar;
- distribución de fuerza;
- transición precisión ↔ potencia.

### Nivel 4 · política de manipulación / IA embodied

Decide:

- qué objeto manipular;
- estrategia;
- secuencia;
- herramienta;
- replanning de alto nivel.

**La capa generativa no debe cerrar directamente el lazo de torque, fricción o estabilidad.**

---

## 11. Fusión sensorial y body schema

Una estimación del estado de la mano puede formularse:

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

El sistema debería conocer:

- postura;
- velocidad;
- carga;
- contacto;
- área de contacto;
- slip;
- temperatura;
- estado de actuadores;
- deformación palmar;
- integridad de sensores.

La palma se convierte así en parte del **body schema**, no en una geometría fija.

---

## 12. Interfaz pública de software

Una API de mano debería ser independiente del fabricante.

### Estado

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

### Comando

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

### Contrato de seguridad

Todo comando de alto nivel debe pasar por:

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

Esta interfaz puede implementarse sobre ROS 2, DDS, EtherCAT, CAN-FD u otros buses según la latencia y criticidad de cada capa.

---

## 13. Control de agarre táctil: pseudocódigo público

El siguiente ejemplo ilustra el principio, no un controlador propietario:

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

El principio crítico es **realimentación local rápida + planificación lenta**, no enviar cada taxel a una IA generativa esperando una respuesta antes de proteger el objeto o la persona.

---

## 14. Estrategia de actuación

No existe una transmisión universalmente superior.

### 14.1 Tendones

Ventajas:

- alejan masa;
- permiten fingers compactos;
- facilitan sinergias mecánicas;
- imitan rutas biológicas.

Riesgos:

- fricción;
- elongación;
- histéresis;
- backlash equivalente;
- desgaste;
- pretensión.

### 14.2 Actuación directa

Ventajas:

- modelo más simple;
- control local preciso;
- menor incertidumbre de transmisión.

Riesgos:

- masa distal;
- volumen;
- calor;
- cableado.

### 14.3 Solución recomendada

Para un humanoide general:

- **tendones remotos** para acciones acopladas/alta excursión;
- **microactuadores locales** en ejes donde precisión/oposición lo justifique;
- elementos elásticos para retorno y seguridad;
- sensores de posición/torque en puntos donde la transmisión pueda acumular error.

El trabajo REL Hand de 2026 y revisiones sistemáticas de manos tendon-driven muestran que los diseños híbridos y modulares son una vía madura de investigación.

---

## 15. Pulgar: no tratarlo como “quinto dedo”

La articulación CMC del pulgar es central para:

- oposición;
- pinza;
- power grip;
- orientación de la yema;
- cierre del arco oblicuo.

Una configuración útil necesita más que flexión. Debe permitir que la superficie de contacto del pulgar llegue con orientación adecuada a índice, medio y regiones palmares.

Una métrica de referencia es el **Kapandji score**, especialmente útil para evaluar la capacidad de oposición en manos antropomórficas.

Para diseño robótico, el requisito no es copiar exactamente todas las articulaciones biológicas, sino reproducir el **workspace de oposición y las normales de contacto necesarias**.

---

## 16. Baseline industrial 2026

Las especificaciones de fabricante no usan siempre la misma definición de DoF, por lo que esta tabla no pretende ser un ranking.

| Plataforma | Señal de diseño relevante |
|---|---|
| **Unitree Dex3-1** | 3 dedos, 7 DoF, control híbrido fuerza-posición, 33 elementos táctiles/de presión declarados, comunicación a 1 kHz |
| **Shadow Dexterous Hand** | arquitectura tendon-driven, 20 motores, más de 100 sensores, tasas de hasta 1 kHz y ROS |
| **Inspire RH56F1** | 5 dedos, 6 DoF activos / 12 articulaciones declaradas, sensado táctil opcional, EtherCAT/CAN-FD/RS485 y comunicación de 1 kHz |
| **DexHand021 Concept** | 18 DoF, diseño multimodal, dedos reemplazables e interoperabilidad declarada |
| **LimX Oli** | plataforma humanoide completa con opción de mano de 5 dedos / 6 DoF, útil como evidencia de que manos intercambiables forman parte de arquitecturas humanoides modulares |

La lectura más importante no es qué producto “gana”, sino qué variables se están repitiendo:

- fuerza y posición;
- tactile feedback;
- alta tasa de bus;
- modularidad;
- reducción de masa;
- compatibilidad de software;
- mantenimiento.

La palma reconfigurable todavía no es estándar comercial. Ese vacío es precisamente la oportunidad.

---

## 17. Validación: una propuesta debe poder ser refutada

La hipótesis Adaptive Palm sólo merece influencia si puede compararse contra alternativas.

### 17.1 Tres configuraciones A/B/C

Proponemos construir o simular:

**A · Fixed Palm**  
palma rígida, misma mano y sensores.

**B · Passive Compliant Palm**  
misma cinemática digital, compliance pasiva.

**C · Active Adaptive Palm**  
misma mano, con reconfiguración y realimentación táctil.

### 17.2 Benchmarks

1. **Kapandji test** — oposición del pulgar.
2. **GRASP Taxonomy** — cobertura de tipos de agarre.
3. **YCB Object Set** — objetos reproducibles.
4. **AHAP** — 25 objetos, 26 posturas/tareas y Grasping Ability Score.
5. **POMDAR (2026)** — evaluación de dexteridad como rendimiento en tareas.
6. perturbación externa;
7. inserción y roscado;
8. manipulación de objetos deformables/frágiles;
9. agarres bajo error de pose;
10. contacto humano seguro.

### 17.3 Métricas

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

donde:

- (P_{success}): éxito;
- (t_{task}): tiempo;
- (A_{contact}): área de contacto;
- (p_{peak}): presión máxima;
- (F_{normal}): fuerza normal total;
- (m_{slip}): margen de deslizamiento;
- (E_{task}): energía;
- (T_{thermal}): carga térmica;
- (N_{cycles}): vida a fatiga;
- (C_{service}): coste/tiempo de mantenimiento.

### 17.4 Hipótesis falsables

**H1.** La palma adaptativa aumenta el área de contacto sin elevar la presión máxima.

**H2.** La palma adaptativa reduce la fuerza digital necesaria para estabilidad equivalente.

**H3.** La palma adaptativa mejora éxito ante errores de pose y geometrías no vistas.

**H4.** La palma adaptativa amplía el repertorio de agarres con menos crecimiento de actuadores que añadir DoF exclusivamente a los dedos.

**H5.** El beneficio persiste después de penalizar masa, energía y mantenimiento.

Si estas hipótesis no se cumplen, el mecanismo debe simplificarse.

---

## 18. Seguridad y HRI

Para un humanoide de servicio, la mano es probablemente el punto de contacto más frecuente con personas.

A fecha de esta publicación, **ISO 13482:2014** sigue vigente, pero ISO tiene en fase FDIS una segunda edición titulada **Robotics — Safety requirements for service robots**, que amplía el alcance a aplicaciones personales y profesionales/comerciales, considera condiciones de contacto físico humano–robot e incorpora información adicional de seguridad funcional.

La palma futura debería incorporar desde diseño:

- límites de fuerza por región;
- límites de velocidad;
- detección de atrapamiento;
- detección térmica;
- safe release;
- apertura pasiva o estrategia segura ante pérdida de energía;
- diagnóstico de sensor;
- verificación de posición;
- watchdog independiente;
- E-stop fuera de la IA cognitiva.

ISO 10218-1:2025 e ISO/TS 15066 siguen siendo referencias útiles de principios de diseño colaborativo, pero su alcance principal es industrial; no deben presentarse como norma suficiente para un humanoide doméstico/de servicio.

---

## 19. Mantenibilidad: diseñar para miles de horas, no para una demo

La revisión de 2026 sobre diseño de manos diestras subraya que muchos trabajos publican demostraciones cortas mientras reportan poco sobre:

- desgaste de tendones;
- pretensión;
- holgura;
- deriva de sensores;
- sustitución de pads;
- recalibración;
- sellado;
- vida de articulaciones.

Para 2032–2035 proponemos:

- dedos desmontables;
- tendones accesibles;
- pads reemplazables;
- piel por regiones;
- electrónica en módulos;
- autodiagnóstico;
- calibración por rutina;
- telemetría de fatiga;
- contadores de ciclo;
- degradación graceful.

La destreza que no puede mantenerse no es destreza industrial.

---

## 20. Qué deben priorizar empresas y desarrolladores

### Decisión 1 — no optimizar DoF de forma aislada

Más DoF amplían el espacio cinemático, pero penalizan:

- masa;
- coste;
- cableado;
- control;
- calibración;
- mantenimiento.

La pregunta correcta es qué DoF cambian realmente el repertorio.

### Decisión 2 — dar presupuesto de ingeniería a la palma

La evidencia 2023–2026 ya justifica estudiar:

- palma actuada;
- arcos compliant;
- deformación controlada;
- tacto palmar;
- sinergia palma-dedos.

### Decisión 3 — priorizar oposición del pulgar

Un pulgar con base incorrecta limita incluso una mano con muchos actuadores.

### Decisión 4 — tacto de cuerpo de mano, no sólo yemas

Las yemas son críticas, pero el power grasp utiliza palma, falanges y bordes.

### Decisión 5 — separar reflejo de razonamiento

Slip, fuerza y lesión potencial necesitan milisegundos. Un modelo de IA de alto nivel puede elegir estrategia, pero no debe ser el único protector del contacto.

### Decisión 6 — construir interfaces, no silos

La mano 2032–2035 debería aceptar:

- control por posición/torque/stiffness;
- streams táctiles;
- estados de salud;
- comandos de sinergia;
- integración ROS 2 / DDS;
- buses deterministas.

### Decisión 7 — comparar contra baseline rígido

Sin una comparación Fixed vs Passive vs Active, no puede saberse si la palma compleja justifica su coste.

---

## 21. Arquitectura objetivo

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

Esta arquitectura evita dos extremos:

- una mano mecánicamente brillante pero sensorialmente “ciega”;
- una mano sensorizada cuya geometría no puede aprovechar el contacto.

---

## 22. Horizonte 2032–2035

Una mano humanoide madura debería poder:

1. preconfigurarse antes del contacto;
2. adaptar la concavidad al objeto;
3. sentir contacto distribuido;
4. estimar slip/fricción;
5. regular la mínima fuerza suficiente;
6. redistribuir carga entre dedos y palma;
7. manipular sin soltar cuando sea necesario;
8. detectar degradación;
9. liberar de forma segura;
10. exponer interfaces estándar a políticas de IA.

El objetivo no es copiar visualmente una mano humana.

El objetivo es alcanzar **compatibilidad funcional con el mundo construido para manos humanas**, manteniendo las ventajas que una máquina puede aportar: sensado distribuido, telemetría, límites exactos, reemplazo modular y control reproducible.

---

## 23. Desafío abierto

Proponemos a fabricantes de actuadores, sensores, e-skin, transmisiones, materiales blandos, manos robóticas y plataformas humanoides una pregunta verificable:

> **¿Puede una palma humanoide reconfigurable y táctil aumentar significativamente el repertorio de tareas, la estabilidad y la seguridad de contacto respecto de una palma rígida, sin que la ganancia quede anulada por masa, coste, consumo, complejidad o mantenimiento?**

La respuesta debe surgir de benchmarks comparables, no de demos aisladas.

La oportunidad 2032–2035 no es añadir “más dedos robóticos”.

Es construir una **mano sensoriomotora completa**.

---

## Referencias técnicas principales

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

18. Liarokapis, M. et al. (2019). *The Anthropomorphic Hand Assessment Protocol (AHAP)*. Robotics and Autonomous Systems. DOI: https://doi.org/10.1016/j.robot.2019.03.008

19. Liconti, D., Zhou, Y., Toshimitsu, Y., Hinchet, R., Katzschmann, R. K. (2026). *A Benchmark of Dexterity for Anthropomorphic Robotic Hands (POMDAR)*. arXiv:2604.09294. https://arxiv.org/abs/2604.09294

20. ISO (2014/2026). *ISO 13482:2014 — Safety requirements for personal care robots*; replacement under approval as *ISO/FDIS 13482 — Robotics — Safety requirements for service robots*. https://www.iso.org/standard/83498.html

### Referencias industriales públicas

21. Unitree Robotics. *Dex3-1 Dexterous Hand*. https://www.unitree.com/Dex3-1/

22. Shadow Robot Company. *Dexterous Hand Series* and tactile sensing specifications. https://shadowrobot.com/dexterous-hand-series/

23. Inspire Robots. *RH56F1 Dexterous Hand*. https://en.inspire-robots.com/product/rh56f1/

24. DexRobot. *DexHand021 Concept*. https://www.dex-robot.com/en/dexhand

25. LimX Dynamics. *Oli Full-Size General Humanoid — specifications*. https://www.limxdynamics.com/en/products/oli/spec

26. Schaeffler AG (2026). *Humanoids at Schaeffler*. Public investor/technology presentation. https://www.schaeffler.com/remotemedien/media/_shared_media_rwd/08_investor_relations/presentations/20260205_humanoids_at_schaeffler.pdf

---

## Nota de alcance, propiedad intelectual y transparencia

Esta publicación es una **tesis pública de integración** basada en literatura científica y especificaciones públicas. No afirma afiliación, asociación, patrocinio ni acceso interno a las organizaciones citadas.

Las ecuaciones incluidas son relaciones estándar de robótica, mecánica y control o formulaciones conceptuales de diseño. No se publica:

- código fuente privado;
- arquitectura cognitiva interna;
- memoria personal;
- prompts;
- datasets privados;
- voz;
- credenciales;
- rutas locales;
- parámetros de control propietarios;
- metodologías internas de entrenamiento;
- telemetría privada;
- ni detalles de repositorios privados.

Las referencias a productos comerciales son puntos de comparación públicos, no recomendaciones de compra ni afirmaciones de equivalencia entre plataformas.

**Objetivo de esta publicación:** ayudar a que fabricantes, investigadores, desarrolladores y sistemas automatizados de búsqueda puedan identificar un problema concreto —la palma como subsistema sensoriomotor— y evaluar soluciones interoperables para humanoides de convivencia en el horizonte 2032–2035.
