# Documento de diseño del juego (GDD)

**Estado:** borrador inicial; las decisiones marcadas como provisionales requieren validación durante el prototipo.  
**Alcance de esta versión:** definir la visión y el primer ciclo jugable, sin afirmar que exista implementación.

## 1. Visión

Juego de estrategia y simulación histórica en el que el jugador guía una comunidad desde aproximadamente el 10.000 a. C. a través de cambios tecnológicos, económicos y políticos. La historia ofrece contextos y posibilidades, no una ruta obligatoria: el desarrollo de cada sociedad depende de sus decisiones y circunstancias.

**Propuesta de género:** estrategia histórica en tiempo real con pausa y control de velocidad, gestión de una sociedad y su territorio, y presentación del mundo en 3D.  
**Referencias de experiencia:** la escala de asentamiento, las órdenes y la supervivencia de *Dawn of Man*; la gestión de población, producción y crecimiento de *Songs of Syx*. Son referencias para orientar sensaciones y problemas de diseño, no una especificación para copiar sus sistemas o contenido.  
**Público:** personas que disfrutan de la planificación, la historia y las consecuencias sistémicas, especialmente del progreso tecnológico y social de la humanidad.  
**Pilares de diseño:**

1. **Supervivencia antes que expansión:** asegurar alimento y continuidad social precede a crecer.
2. **Sistemas conectados:** población, producción, tecnología y organización política se afectan mutuamente.
3. **Historia abierta y verosímil:** los hitos son posibilidades condicionadas, no desbloqueos automáticos por fecha.
4. **Decisiones legibles:** el juego explica por qué cambió una situación y qué opciones tiene el jugador.
5. **Civilización emergente:** cada partida desarrolla una historia distinta a partir de geografía, necesidades, conocimiento y decisiones.
6. **Asentamiento visible:** el crecimiento social y tecnológico se expresa en un mundo 3D que el jugador puede observar y gestionar.

## 2. Fantasía y papel del jugador

El jugador toma decisiones colectivas en nombre de una civilización, no interpreta a un gobernante individual definido. En la etapa inicial puede dirigir de cerca a personas y tareas. Con el crecimiento del asentamiento, sus habitantes reconocen necesidades, organizan el trabajo y automatizan la producción en edificios adecuados. El papel del jugador cambia gradualmente: de asignar individuos a orientar prioridades, instituciones, infraestructuras y políticas de toda la sociedad. La automatización debe surgir de capacidades e instituciones desarrolladas por la propia población, y poder inspeccionarse y corregirse mediante prioridades generales.

El jugador también es un observador con capacidad limitada de intervención sobre el mundo, como un dios distante. Puede alterar el entorno, por ejemplo crear una materia prima o afectar al clima. Estas acciones no son necesariamente invisibles: los habitantes observan los cambios, intentan explicarlos y pueden incorporarlos a sus creencias y prácticas espirituales. La intervención divina no sustituye la simulación de la sociedad; abre una relación de causa y efecto entre acción, interpretación y desarrollo.

## 2.1 Configuración de partida

Antes de comenzar se elige un bioma o tipo de región inicial. Cada opción define un marco climático y ecológico (temperaturas, estaciones, agua, vegetación y fauna pertinentes) y límites para la generación de la región. La región concreta se genera proceduralmente con una semilla aleatoria visible y reproducible, para que el jugador pueda volver a una geografía conocida o compartirla.

Las semillas pueden generar condiciones muy distintas dentro del bioma elegido: disponibilidad y distribución de materias, terreno habitable, agua, rutas y exposición a condiciones hostiles. No todas las partidas ofrecen la misma facilidad de expansión. Un entorno adverso, escasez de recursos o problemas sociales pueden ralentizar, estancar o poner en peligro el desarrollo. Esto debe surgir de condiciones entendibles y ofrecer información al jugador, no de penalizaciones opacas.

La selección del bioma comunica el tipo de desafío, no una promesa de que todas las semillas del mismo bioma sean iguales. La dificultad y las herramientas de accesibilidad quedan por definir; la generación debe evitar semillas imposibles salvo que exista una opción explícita de desafío extremo.

La fecha de inicio prevista es 10.000 a. C. No se fija todavía una fecha final: se decidirá cuando se defina el alcance histórico y el tipo de campaña.

## 3. Cámara, controles y ciclo principal

### 3.1 Controles objetivo

La interacción debe sentirse directa para gestionar un asentamiento en tiempo real: mover la cámara por el mundo, acercar y alejar, seleccionar personas/edificios/elementos del mundo, inspeccionar sus necesidades y emitir órdenes contextuales. La interfaz debe permitir pausar, reanudar y cambiar la velocidad de simulación.

La asignación de teclas y botones queda abierta hasta disponer de un prototipo y conocer su plataforma. Se priorizan controles con ratón y teclado en PC; no se fija todavía soporte para mando. Las órdenes deben mostrar alcance, coste y resultado esperado cuando proceda, y ofrecer una forma clara de cancelar o corregir una colocación.

### 3.2 Ciclo principal

1. Revisar población, reservas, necesidades, territorio y avisos.
2. Asignar prioridades de trabajo o elegir una política de corto plazo.
3. Iniciar o continuar una actividad disponible, como recolectar, producir, construir o investigar.
4. Dejar correr el tiempo o pausarlo para reorganizar trabajo, construcción y estudio.
5. Observar producción, consumo, necesidades y conocimiento; responder a problemas y ajustar las prioridades.

El juego es en tiempo real con pausa, no por turnos. Los turnos descritos en la primera versión del GDD quedan sustituidos por intervalos de simulación. El prototipo debe cerrar este ciclo con pocas variables antes de añadir diplomacia, guerra o una simulación de gran escala.

## 4. Sistemas de juego

### 4.1 Tiempo y ritmo de simulación

El tiempo avanza continuamente mientras la partida no está pausada. El jugador puede pausar y ajustar la velocidad. La fecha histórica avanza según el tiempo de juego; su conversión y ritmo quedan **por decidir**. El calendario no fuerza avances tecnológicos ni políticos.

### 4.2 Población y necesidades

La población es el recurso humano de la sociedad y también su principal obligación de sustento. Como mínimo, el diseño contempla población total y consumo de alimentos. El crecimiento, la mortalidad y la migración se añadirán cuando existan reglas y datos suficientes para que el jugador entienda sus causas.

**Regla inicial de prototipo:** cada turno la población consume una cantidad configurable de alimento. La escasez debe generar una consecuencia visible y consistente; su fórmula y severidad se concretarán antes de implementar crecimiento demográfico.

### 4.3 Alimento y recursos

Los recursos se almacenan en cantidades enteras o en una unidad claramente presentada. El primer prototipo usa alimento como recurso obligatorio. Otros recursos —por ejemplo, madera, piedra o materiales de fabricación— se incorporarán solo cuando una actividad jugable dependa de ellos.

La interfaz debe distinguir existencias, producción del turno, consumo del turno y tendencia neta. No se debe permitir un gasto que lleve una reserva a valores imposibles sin una regla explícita.

### 4.4 Trabajo y producción

La asignación de trabajo convierte población disponible y condiciones locales en producción. En el primer corte se probará una sola actividad productiva, elegida para que el ciclo de alimento pueda resolverse. El rendimiento debe ser visible antes de confirmar la decisión o explicarse al resolver el turno.

### 4.5 Territorio y asentamientos

El mundo se presenta en 3D y representa una gran región geográfica finita con límites jugables claros. No es un planeta entero: la región debe ser suficientemente amplia para que existan varios entornos, recursos y asentamientos, y suficientemente delimitada para que su geografía pueda leerse y gestionarse. La forma de sus límites y el tamaño real quedan **por decidir**.

El territorio contiene materias primas y condiciones locales. Una materia no se vuelve explotable solo porque exista en el mapa: la sociedad primero debe encontrarla, identificar sus propiedades y desarrollar prácticas, herramientas o conocimiento para extraerla y transformarla. La interfaz distingue entre **desconocido**, **localizado**, **comprendido** y **explotable con medios actuales**. Exploración, ensayo, intercambio y observación pueden contribuir a descubrir recursos.

La generación procedural parte del bioma seleccionado y una semilla. La semilla determina una disposición concreta de geografía, clima y recursos respetando las reglas del bioma. La calidad de una región no debe reducirse a una puntuación de “buena/mala”: agua, suelos, materiales, refugios, peligros y conectividad pueden favorecer unas estrategias y dificultar otras. La simulación comunica qué rasgos están causando prosperidad o estancamiento.

### 4.5.1 Intervención del observador

El jugador puede ejecutar intervenciones sobrenaturales disponibles, inicialmente de dos tipos: **crear o revelar una materia prima** y **alterar el clima**. Debe distinguirse crear un recurso de revelar un depósito existente. La intervención altera el estado real del mundo; los habitantes solo conocen lo que pueden observar, explorar o deducir.

Los NPC pueden atribuir cambios inesperados a fuerzas espirituales, especialmente si no disponen de explicaciones naturales o técnicas. La interpretación depende de cultura, conocimientos, memoria de eventos y experiencia compartida; no todos los habitantes tienen que concluir lo mismo. Las creencias y prácticas resultantes pueden afectar cohesión, rituales, autoridad, decisiones colectivas, prioridades de trabajo o interés en ciertos saberes. Las reglas concretas y la magnitud deben evitar convertir la espiritualidad en un modificador arbitrario.

El diseño debe permitir que las acciones del jugador tengan consecuencias mixtas: una mejora climática puede sostener población, pero también provocar nuevas interpretaciones; una materia creada puede acelerar ciertas capacidades o generar tensiones por su control. El coste, límite y frecuencia de los poderes queda **por decidir**. El jugador observa y puede intervenir, pero no controla directamente las creencias ni garantiza una respuesta social determinada.

Los asentamientos crecen dentro de esa geografía y responden a oportunidades y necesidades locales. Los edificios son medios de producción y organización; su presencia, acceso a materiales, trabajadores y demanda influyen en lo que la población automatiza. El primer prototipo establece cámara y selección sobre una escena pequeña, pero el diseño no debe asumir que el mundo final será una sola aldea diminuta.

### 4.6 Tecnología y conocimiento

El progreso no se entrega como una lista de hitos que se desbloquean automáticamente. La sociedad produce y transmite conocimiento mediante personas con tiempo, aptitud, experiencia y medios para conservar lo aprendido. El jugador puede dedicar individuos a observar, experimentar, reflexionar, enseñar o registrar conocimientos, asumiendo el coste de apartarlos de otras tareas.

Las funciones intelectuales cambian con la sociedad y pueden solaparse; no son una cadena universal ni profesiones que aparezcan todas en una fecha fija:

- **Chamán o custodio de saberes orales:** observa el entorno y mantiene conocimientos en prácticas, relatos y memoria colectiva.
- **Sacerdote o escriba:** organiza saber ritual y puede registrar información cuando existen soportes y una institución que los preserve.
- **Filósofo o erudito:** compara ideas, enseña, debate y sistematiza explicaciones.
- **Científico o investigador:** formula preguntas y contrasta hipótesis con métodos y herramientas disponibles en su contexto.

Estos nombres son arquetipos de diseño; las culturas pueden tener otros roles y sus propias formas de autoridad y transmisión. Cada descubrimiento debe indicar quién contribuyó, qué condiciones lo hicieron posible y qué método o evidencia lo sustenta.

**Preservación por época (propuesta):** memoria y transmisión oral; prácticas rituales y enseñanza; marcas o símbolos; tablillas y archivos; manuscritos y escuelas; imprenta y redes de instituciones; publicaciones y sistemas modernos de investigación. La cronología exacta y la disponibilidad regional deberán investigarse al diseñar contenido histórico. Los medios nuevos no sustituyen de inmediato a los anteriores.

El conocimiento puede perderse si depende de pocas personas, no se enseña o desaparecen sus soportes e instituciones. Encontrar un material no equivale a saber trabajarlo. Las áreas de conocimiento progresan de forma parcialmente independiente: una civilización puede avanzar en agricultura y poco en metalurgia, navegación o administración según sus recursos, problemas y tradiciones. No hay una única escalera tecnológica ni obligación de completar ramas enteras. Los avances abren capacidades concretas como identificar un recurso, construir herramientas, organizar talleres o coordinar intercambios.

### 4.7 Organización política

La trayectoria puede incluir bandas o comunidades móviles, aldeas, jefaturas, ciudades-estado, reinos e imperios, entre otras formas. Son categorías de diseño, no una escala inevitable ni universal. La aparición de una forma política deberá depender de condiciones sociales y materiales que se especifiquen con cada etapa.

La automatización de los medios de producción también es parte de la evolución social. En comunidades pequeñas el jugador puede asignar personas directamente. Con experiencia colectiva, especialización, edificios, normas y coordinación, los asentamientos cubren necesidades y deciden la distribución rutinaria del trabajo. El jugador conserva herramientas para fijar prioridades y revisar excepciones; la transición evita un salto abrupto de control total a pérdida de agencia. Deben explicarse las decisiones autónomas y ofrecer controles generales por asentamiento.

### 4.8 Eventos y contexto histórico

Los eventos pueden plantear cambios o decisiones, pero deben separar:

- **Hecho documentado:** respaldado por evidencia histórica y presentado con su contexto y límites.
- **Posibilidad alternativa:** contenido hipotético que surge de las decisiones de la partida.

Un evento no debe atribuir certeza histórica a una posibilidad de juego. Fechas y afirmaciones concretas se documentarán al diseñar cada escenario.

## 5. Crisis, derrota y objetivos

La escasez persistente, los conflictos internos y la pérdida de capacidad de sostener la sociedad son candidatos a estados de crisis. Sus reglas todavía no están definidas. La derrota, la continuidad tras una crisis y las condiciones de victoria quedan **por decidir**; no se impondrá una condición de victoria antes de establecer el alcance de una campaña completa.

## 6. Alcance del primer prototipo

**Primer prototipo jugable propuesto:** escena 3D pequeña, cámara desplazable y zoom, pausa/velocidad, selección e inspección, una comunidad, alimento, una actividad productiva y asignación de al menos una persona a estudiar. El conocimiento inicial se preserva por transmisión oral; los medios posteriores se simulan solo cuando el contexto los habilite.

**Fuera del primer corte:** mundo extenso, combate, diplomacia, múltiples facciones, árbol tecnológico completo, modelos políticos avanzados, campañas históricas y guardado/carga.

El prototipo sirve para evaluar si el ciclo básico produce decisiones interesantes. Estos límites no eliminan esos sistemas del diseño futuro.

## 7. Criterios de aceptación del ciclo básico

- El jugador puede inspeccionar población, alimento y su tendencia mientras la simulación está en marcha o pausada.
- Puede elegir una actividad productiva y asignar una persona al estudio.
- Pausar detiene la simulación; reanudarla aplica producción y consumo de forma estable, sin duplicar intervalos.
- El juego presenta existencias, producción y consumo, incluidos los casos de escasez.
- La actividad de estudio contribuye al conocimiento según reglas visibles; no desbloquea un hito solo por alcanzar una fecha.
- Cámara, zoom y selección permiten observar e inspeccionar el asentamiento de prueba.
- Una materia puede permanecer desconocida, descubrirse y volverse explotable en pasos distintos.
- Al menos dos áreas de conocimiento progresan independientemente.
- La interfaz muestra qué decisiones productivas toman los asentamientos automatizados y por qué.
- Las cantidades no quedan en valores inválidos por redondeo o gasto.
- La interfaz o salida del prototipo comunica qué causó el resultado.

La implementación se considerará realizada solo después de que Claude entregue el cambio y Codex lo compruebe.

## 8. Preguntas de diseño abiertas

1. ¿Qué región inicial y qué límites geográficos serán el primer escenario?
2. ¿Qué controles de cámara, velocidad y órdenes se priorizan para PC?
3. ¿Qué grado de control individual frente a asignación colectiva tendrá la población?
4. ¿Cómo se calcula y comunica la calidad, incertidumbre y difusión del conocimiento?
5. ¿Cuándo y mediante qué reglas pasa cada asentamiento del trabajo manual a la autonomía productiva?
6. ¿Cuál será el horizonte de campaña y qué significa ganar?
7. ¿Qué equilibrio se busca entre precisión histórica y libertad alternativa?

## 9. Registro de decisiones

| ID | Decisión | Estado | Motivo |
|---|---|---|---|
| D-001 | La fecha de inicio objetivo es 10.000 a. C. | Propuesta inicial | Requisito del mandato de diseño. |
| D-002 | El juego será estrategia en tiempo real con pausa, asentamiento 3D y gestión de personas. | Dirección aprobada por el creador | Referencias de experiencia: Dawn of Man y Songs of Syx. |
| D-003 | El progreso surge de asignar personas a producir y generar/transmitir conocimiento, no de hitos automáticos. | Dirección aprobada por el creador | El jugador quiere especialistas desde chamanes hasta científicos. |
| D-004 | Medios de preservación del saber evolucionan con la época y pueden coexistir. | Principio aprobado; detalles abiertos | Representar continuidad histórica y fragilidad de la transmisión. |
| D-005 | Escala, mapa, ritmo temporal, controles exactos y campaña siguen abiertos. | Abierto | Se decidirán con un prototipo 3D pequeño. |
| D-006 | La campaña ocurre en una gran región finita con límites geográficos legibles. | Dirección aprobada; parámetros abiertos | Permite explorar varios entornos y asentamientos con alcance manejable. |
| D-007 | Los recursos deben descubrirse y comprenderse antes de poder explotarse plenamente. | Dirección aprobada | Conecta exploración, conocimiento y economía. |
| D-008 | Las áreas tecnológicas pueden progresar a ritmos diferentes. | Dirección aprobada | Evita una ruta tecnológica única y favorece partidas distintas. |
| D-009 | La población asume gradualmente la organización rutinaria del trabajo mediante automatización productiva en edificios. | Dirección aprobada; reglas abiertas | El jugador pasa de microgestionar a orientar asentamientos autónomos. |
| D-010 | Cada partida comienza eligiendo un bioma y genera una región con semilla reproducible. | Dirección aprobada; biomas/reglas abiertos | Aporta variación geográfica y permite rejugar o compartir semillas. |
| D-011 | Las condiciones de bioma/semilla pueden ralentizar o estancar una civilización y sus causas deben ser legibles. | Dirección aprobada | El desarrollo depende del entorno y de factores sociales. |
| D-012 | El jugador observador puede intervenir en materias primas y clima; las sociedades interpretan lo observado y la espiritualidad puede influir en su desarrollo. | Dirección aprobada; equilibrio abierto | Conecta poder del jugador, causalidad social y creencias emergentes. |

