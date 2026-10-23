# Plan de desarrollo

**Estado:** hoja de ruta inicial alineada con el borrador de [GDD.md](GDD.md).  
**Regla de estado:** “propuesto” no significa implementado. Cada hito se actualiza cuando Claude entrega el trabajo y Codex lo verifica.

## Principios de planificación

- Entregar incrementos pequeños que se puedan jugar o inspeccionar.
- Resolver primero las dependencias entre sistemas: escena y controles → tiempo real y pausa → trabajo/consumo → estudio y transmisión → expansión.
- No adelantar sistemas complejos sin una decisión de diseño y criterios de aceptación.
- Mantener la lógica de simulación separada de la presentación cuando la arquitectura lo permita.
- Registrar supuestos, resultados y errores conocidos en el handoff.

## Fases

| Fase | Estado | Objetivo | Dependencias |
|---|---|---|---|
| 0. Inspección técnica | Pendiente | Identificar tecnología, punto de entrada, forma de ejecución y convenciones del repositorio. | Ninguna. |
| 1. Fundamentos 3D y control | Propuesto | Escena pequeña, cámara, selección, pausa y velocidad de simulación. | Fase 0; tecnología identificada. |
| 2. Sustento del asentamiento | Propuesto | Población, alimento, consumo y una actividad productiva en tiempo real. | Fase 1; GDD. |
| 3. Estudio y memoria | Propuesto | Asignar una persona a estudiar y representar generación/transmisión de conocimiento oral. | Fase 2; reglas visibles de conocimiento. |
| 4. Crecimiento y preservación | No iniciado | Construcción y capacidades de preservación según medios disponibles; primeros cambios sociales. | Fases anteriores; revisión histórica. |
| 5. Sociedad y territorio | No iniciado | Ampliar producción, población y territorio; luego integrar cultura, diplomacia y conflicto por incrementos. | Decisiones de escala y mapa. |
| 6. Campaña y acabado | No iniciado | Definir objetivos, progresión, guardado/carga, presentación y rendimiento. | Decisión de alcance de campaña. |

## Tareas próximas

### P0 — Inspección e inicio de Claude

- [ ] Claude informa qué archivos y herramientas existen, cómo se ejecuta el proyecto y si hay decisiones técnicas previas.
- [ ] Si el repositorio carece de una aplicación jugable, propone la mínima estructura para probar la fase 1 y explica las opciones relevantes.
- [ ] No introduce un mapa, una escala temporal ni sistemas mayores sin especificación.

### P1 — Prototipo de control 3D

- [ ] Proponer motor/tecnología tras inspeccionar el repositorio y justificarlo considerando escena 3D y simulación de asentamiento.
- [ ] Crear una escena pequeña para validar cámara, zoom, selección e inspección.
- [ ] Implementar pausa y velocidades configurables sin fijar todavía escalas históricas largas.
- [ ] Entregar una forma de ejecutar y probar el prototipo.

### P2 — Ciclo mínimo de asentamiento y estudio

- [ ] Definir los datos de una sociedad inicial: población, alimento y producción por intervalo de simulación.
- [ ] Implementar actualización estable de producción y consumo en tiempo real.
- [ ] Mostrar existencias, producción, consumo y tendencia.
- [ ] Permitir asignar una persona a estudiar y mostrar su contribución y el conocimiento acumulado.
- [ ] Manejar reservas insuficientes sin valores negativos accidentales ni crecimiento silencioso.
- [ ] Entregar instrucciones para ejecutar y una lista de archivos modificados.

## Criterios de salida de las fases 1 y 2

1. Se puede iniciar la simulación con un estado conocido.
2. Pausar congela la simulación y reanudar no duplica ni pierde intervalos.
3. Producción y consumo responden consistentemente a población, asignaciones y velocidad.
4. El jugador puede ver cámara, selección, estado y tendencia de los recursos.
5. El estudio genera conocimiento por reglas visibles, sin desbloqueo automático por fecha.
6. La escasez se representa de forma coherente y no se oculta mediante ajustes silenciosos.
7. Claude informa limitaciones y cómo ejecutar la entrega.
8. Codex comprueba los criterios y comunica cualquier fallo antes de marcar las fases completas.

## Protocolo de cambios de alcance

Las fases posteriores son una dirección, no aprobación automática para añadir todo su contenido. Un cambio que altere la fantasía central, escala de campaña, simulación o prioridades debe registrarse en el GDD y consultarse con el creador antes de implementarse. Las decisiones pequeñas necesarias para un prototipo deben quedar anotadas como supuestos reversibles.

## Registro de progreso

## Ampliación de dirección: región y autonomía

La siguiente planificación de sistemas de mediano plazo queda añadida a las fases existentes; no implica implementarlos en el prototipo inicial:

1. **Modelo de región:** definir un escenario finito grande con límites geográficos legibles, varios biomas/entornos y espacio para múltiples asentamientos.
2. **Descubrimiento de materias:** separar existencia física, localización, comprensión de propiedades y capacidad actual de extracción/transformación.
3. **Progreso desigual:** modelar áreas de conocimiento que evolucionan independientemente y abren capacidades según contexto, necesidades y trabajo intelectual.
4. **Producción en edificios:** vincular edificios, trabajadores, materias, demanda y métodos productivos; hacer visibles los cuellos de botella.
5. **Autonomía gradual:** empezar con asignación directa; habilitar después prioridades automáticas por asentamiento según necesidades y medios productivos. Permitir inspeccionar causas, ajustar políticas y retomar el control ante excepciones.
6. **Variedad entre partidas:** probar cómo geografía, recursos descubiertos, problemas y decisiones generan trayectorias distintas sin depender de eventos aleatorios opacos.

**Criterios de diseño previos a implementación regional:** mapa y bordes legibles; depósitos no explotables antes de ser comprendidos; tecnologías no sincronizadas por una sola ruta; automatización explicable y configurable; varias estrategias viables para sostener cada asentamiento.

## Ampliación de dirección: biomas, semillas e intervención

Planificar después de establecer los fundamentos 3D y el ciclo de sustento:

1. **Selección de partida:** presentar biomas con una descripción clara de clima, geografía, recursos esperables y desafíos, sin revelar exactamente la semilla.
2. **Generación reproducible:** producir región a partir de bioma y semilla; permitir repetir la semilla y mostrarla en la interfaz.
3. **Validación de condiciones:** identificar semillas inviables o desequilibradas; conservar desafíos severos intencionales como opción reconocible.
4. **Causas del desarrollo:** exponer cómo clima, acceso a recursos, geografía y factores sociales causan crecimiento, ralentización o estancamiento.
5. **Poderes del observador:** prototipar una intervención climática y una intervención sobre materias primas. Separar crear una materia de revelar una existencia oculta.
6. **Respuesta espiritual:** registrar lo que los NPC observan y cómo cultura/conocimiento/experiencia influyen en interpretaciones, prácticas y consecuencias sociales. Evitar una respuesta automática uniforme.

**Criterios previos a integrar:** semilla reproducible; efectos del bioma legibles; posibilidad de partidas hostiles sin causalidad opaca; poderes con efectos observables; percepción de los NPC separada del estado real del mundo; espiritualidad causada por experiencia y con consecuencias descritas.

| Fecha | Fase/tarea | Estado | Nota |
|---|---|---|---|
| 2026-10-23 | Documentación inicial | En curso | GDD, fases y primer encargo preparados; repositorio sin código en `src`. |
| 2026-10-23 | Dirección actualizada | En curso | Referencias de experiencia, presentación 3D, RTS con pausa y progreso mediante especialistas/conocimiento añadidos. |
| 2026-10-23 | Región y autonomía | En curso | Se amplía diseño con recursos descubribles, progreso desigual y transferencia gradual de microgestión a asentamientos autónomos. |
| 2026-10-23 | Biomas y observador | En curso | Selección de bioma/semilla, clima y geografía variables, estancamiento contextual y poderes con respuesta espiritual añadidos al GDD. |

