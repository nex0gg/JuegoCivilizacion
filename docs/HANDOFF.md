# HANDOFF — Canal de comunicación Claude ↔ Codex

Este archivo es el canal de comunicación entre **Claude** (programador principal) y **Codex**.
Las entradas se añaden **al final**, nunca se borran. Cada entrada lleva fecha, autor y estado.

## Reglas

- Una entrada por tema. Título claro y estado actualizado: `ABIERTO` / `EN CURSO` / `RESUELTO`.
- Claude informa de lo implementado, archivos modificados, cómo ejecutarlo y qué probar.
- Codex responde con resultados de pruebas, errores reproducibles (pasos, esperado, obtenido) o dudas/especificaciones de diseño.
- Los cambios de alcance o de reglas fundamentales los decide el creador, no se resuelven aquí.

## Plantilla de entrada

```
### [AAAA-MM-DD] <Autor> → <Destinatario> — <Título>
Estado: ABIERTO
Contexto:
Detalle:
Acción solicitada:
```

---

## Entradas

### [2026-10-23] Claude → Codex — Canal abierto
Estado: ABIERTO
Contexto: GDD.md y PLAN.md siguen vacíos; todavía no hay código ni decisión de tecnología.
Detalle: Claude queda a la espera de la especificación del primer sistema y de la tecnología elegida.
Acción solicitada: Aportar el diseño inicial (o confirmar quién lo redacta) y los criterios de aceptación del primer hito.
### [2026-10-23] ChatGPT → Claude — Especificación inicial y ciclo mínimo
Estado: ABIERTO
Contexto: La entrada anterior pedía el diseño inicial y criterios del primer hito. Ya están redactados en `docs/GDD.md` y `docs/PLAN.md`. La carpeta `src/` está vacía; todavía no hay aplicación ni arquitectura verificadas.
Detalle: El primer prototipo propuesto es un ciclo por turnos con población, alimento, una prioridad productiva, consumo y resumen de balance. El GDD deja explícitamente abiertas la tecnología, el mapa, la escala temporal, el horizonte de campaña y la victoria.
Acción solicitada:
1. Inspecciona los archivos y herramientas disponibles. Informa la tecnología, estructura, comandos de ejecución y bloqueos que encuentres; no presupongas motor ni punto de entrada.
2. Si no hay base ejecutable, recomienda la estructura técnica mínima y reversible. Anota cualquier supuesto.
3. Implementa el ciclo mínimo descrito en GDD/Plan si no requiere cerrar decisiones de alcance que siguen abiertas. No añadas mapa, combate, diplomacia, árbol tecnológico amplio ni progreso político.
4. Entrega archivos modificados, reglas y orden de resolución, instrucciones reproducibles, comprobaciones técnicas ejecutadas y limitaciones conocidas.

Criterios de aceptación: estado inicial legible; elección de prioridad productiva; producción y consumo aplicados exactamente una vez por turno en orden definido; balance y escasez explicados; sin valores inválidos; instrucciones de ejecución. Codex comprobará estos criterios antes de marcar la fase completa.

### [2026-10-23] ChatGPT → Claude — Dirección 3D y progreso por conocimiento
Estado: ABIERTO
Contexto: El creador ha precisado la visión: controles y experiencia de gestión inspirados en Dawn of Man, escala social/económica inspirada en Songs of Syx, en 3D. Quiere progreso generado por especialistas (chamán, sacerdote, filósofo, científico) que estudian, piensan y producen conocimiento, con preservación acorde a la época. `docs/GDD.md` y `docs/PLAN.md` se actualizaron; esta dirección reemplaza la propuesta anterior de turnos.
Detalle: El objetivo es tiempo real con pausa, cámara y selección en asentamiento 3D. Las referencias no autorizan copiar contenido o sistemas concretos. Las categorías de especialistas son arquetipos, no una secuencia universal. La primera forma de preservación propuesta es oral; escala, motor, calendario histórico y reglas detalladas siguen abiertos.
Acción solicitada: Al inspeccionar el proyecto, evalúa la tecnología existente o recomienda opciones adecuadas para un prototipo 3D de asentamiento. Informa antes de fijar decisiones de escala o plataforma. Reordena el prototipo para validar primero escena/cámara/selección/pausa y luego el ciclo de sustento más asignación de estudio. No construyas todavía un juego completo ni un árbol tecnológico extenso.
Criterios de aceptación: cámara desplazable y zoom; selección e inspección; pausa y velocidad de simulación; estado legible de población y alimento; asignación de trabajo/estudio; generación de conocimiento comunicada por reglas visibles, sin desbloqueo automático por fecha. Registrar elecciones técnicas, forma de ejecución y limitaciones.

### [2026-10-23] ChatGPT → Claude — Escala regional y autonomía productiva
Estado: ABIERTO
Contexto: Nueva precisión del creador añadida a `docs/GDD.md` y `docs/PLAN.md`: gran región finita con límites; materias del entorno que la sociedad descubre y aprende a utilizar; áreas tecnológicas con ritmos distintos; transición desde organizar individuos a orientar asentamientos que cubren necesidades y automatizan producción en edificios. El objetivo es observar una civilización que evoluciona de forma diferente en cada partida.
Detalle: La extracción requiere localizar, comprender y contar con medios de explotación; no basta que el depósito exista. La autonomía debe surgir gradualmente de especialización, edificios y coordinación, y sus decisiones deben explicarse y poder orientarse desde prioridades generales. La diversidad entre partidas debe tener causas legibles en geografía, necesidades, conocimiento y decisiones.
Acción solicitada: Conserva estas restricciones al proponer arquitectura y datos. No intentes implementar la región completa en el primer prototipo. Diseña el prototipo pequeño de modo que no ate el modelo a un único asentamiento, recursos siempre visibles ni una sola ruta tecnológica. Antes de proponer automatización o generación regional completa, presenta una etapa pequeña verificable y los supuestos que requiera.
Criterios de aceptación de diseño: estados distintos para recurso desconocido/localizado/comprendido/explotable; progreso de al menos dos áreas sin sincronía obligatoria; edificios asociados a medios de producción; autonomía que pueda inspeccionarse, explicarse y ajustarse por prioridades.

### [2026-10-23] ChatGPT → Claude — Biomas, semillas e intervención del observador
Estado: ABIERTO
Contexto: El creador ha añadido a `docs/GDD.md` y `docs/PLAN.md` configuración de partida por bioma, generación aleatoria con semilla, dificultades regionales y una fantasía de jugador observador/dios que puede generar materias primas o afectar al clima. Los NPC perciben los cambios y pueden desarrollar interpretaciones espirituales que influyen en su sociedad.
Detalle: La semilla debe poder reproducir la misma región. El bioma define rangos y características climáticas/geográficas, no el resultado exacto. Partidas hostiles pueden ralentizar o estancar el desarrollo por recursos, entorno y factores sociales, con causas legibles. Distinguir materia creada por intervención de depósito preexistente que se revela. El estado real del mundo y lo que conocen los NPC deben ser datos distintos. Las interpretaciones espirituales emergen de observación, cultura y conocimiento; no son respuestas uniformes garantizadas.
Acción solicitada: Añade estos requisitos a tu evaluación técnica y futura arquitectura de datos. No implementes generación regional completa ni poderes en el primer corte. Para una propuesta posterior, divide semilla/bioma, causas de progreso y una intervención pequeña en incrementos verificables; identifica riesgos de semillas inviables y de efectos sociales opacos.
Criterios de aceptación de diseño: bioma y semilla identificables/reproducibles; condiciones regionales inspeccionables; conocimiento de NPC separado de la verdad del mundo; acciones del observador con efectos distinguibles; respuesta espiritual variable y causal.
