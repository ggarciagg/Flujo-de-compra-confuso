CASO DE EJEMPLO: El flujo de compra que confunde al usuario


Contexto
Formo parte de un equipo reducido de diseño y desarrollo a cargo de una aplicación híbrida centrada en el diseño de autor del Norte Argentino. El producto combina el comercio electrónico con la difusión cultural a través de historias audiovisuales y editoriales para aportar valor agregado a las piezas comercializadas. Debido a limitaciones presupuestarias, el modelo de negocio inicial debió excluir las pasarelas de pago y la logística de envío tradicional. En su lugar, se optó por un sistema de reserva digital a través de la app, donde el usuario finaliza la transacción retirando el producto en un punto de entrega físico cercano. 


Problema
El flujo actual de reserva mimetiza en exceso la estructura visual de un checkout tradicional (compra y envío). Esta similitud entra en conflicto con lo que esperan los usuarios: al no encontrar los pasos de pago ni solicitar datos de envío, asumen que el proceso está incompleto o que la plataforma presenta un error técnico. Esta confusión genera una fricción crítica, provocando que las personas abandonen la tarea antes de confirmar la reserva al creer que la página no funciona correctamente. 

Acciones — Paso 1: evidencia (post mortem constructivo)
Alta tasa de abandono en la reserva de productos y comentarios de usuarios informando un error en el proceso virtual de compra.


Acciones — Paso 2: timeline del incidente (post mortem constructivo)
1º Semana (lanzamiento)
Los procesos de reserva y retiro no evidencian un problema. El volumen de usuarios es bajo. 
2º Semana
Aumenta el volumen de usuarios notoriamente.Se detecta una tasa de abandono en ascenso en la fase de reserva del producto a través de datos de Firebase Analytics (de Google). Se decide esperar una semana más para tener una tendencia más sólida y se continúa con la priorización de tareas planteada antes del emergente. Postergando la comunicación del problema a todo el equipo.  
3º Semana (Lunes 9 am)
La tasa de abandono supera el 45% y los usuarios empiezan a realizar comentarios negativos sobre el proceso de compra en la app. El problema se comunica inmediatamente al coordinador.
3º Semana (Lunes 11 am)
Se llama a una reunión sincrónica con el área de UX/UI y desarrollo para comprender rápidamente el problema.
3º Semana (Miércoles)
Se realizan cambios en el flujo de compra solucionando el problema.

Acciones — Paso 3: hipótesis (post mortem constructivo)
Hipótesis
Probabilidad
Impacto
A — Falta de reevaluación en la priorización de tareas ante la urgencia, privilegiando el desarrollo de pantallas de producto individuales por sobre la corrección del flujo de reserva en problemas. 
Alta
Alto
B — Seguimiento deficiente de una alerta temprana que advertía que la evaluación heurística, durante la fase de prototipado, no contempló en detalle la naturaleza híbrida de la app dentro del flujo de confirmación y reserva de producto.     
Alta
Alto
C — Falta de prominencia y claridad en los textos explicativos dentro de la pantalla sobre la modalidad de reserva y retiro en punto físico.
Medio
Bajo





Acciones — Paso 4: priorización
Hipótesis prioritaria: Combinación de las hipótesis A y B. Bajo un enfoque de post-mortem constructivo (orientado a resolver fallas del sistema y no a buscar culpables individuales), se determinó que la causa raíz no se debió a un error humano aislado, sino a dos debilidades en el proceso:
Deficiencia en la gestión de alertas: No se realizó un seguimiento oportuno ni se escalaron los reportes iniciales que advertían sobre el problema.
Rigidez en la planificación: La respuesta ante el problema emergente fue tardía, omitiendo reajustar la priorización de las tareas del equipo de acuerdo con la nueva información disponible


Acciones — Paso 5: plan de acción (post mortem constructivo)
Acción
Responsable
Estado
Coordinar y ejecutar una reunión sincrónica entre los equipos de UX y Desarrollo para definir las acciones de mitigación inmediatas. 
Coordinador
Hecho
Realizar una nueva evaluación heurística enfocada específicamente en el flujo crítico de reserva de producto y análisis de los comentarios aportados por los usuarios. 
Evaluador UX/UI
Hecho
Comunicar el diagnóstico del problema y la hoja de ruta de los cambios a todo el equipo interdisciplinario. 
Coordinador
Hecho
Implementar las modificaciones de diseño y corregir el flujo afectado en la aplicación.
Desarrollador Senior
Hecho
Auditar y elaborar un informe técnico para verificar si el mapeo heurístico contempló las particularidades de la app en sus flujos principales (selección de productos y categorías). 
Evaluador UX/UI
Pendiente


Acciones — Paso 6: cómo se avisó al equipo
Contexto del hallazgo: Se confirmó que la confusión del usuario se originaba en un flujo de reserva diseñado de manera idéntica al de una compra tradicional: Presionar botón de compra > Seleccionar punto de retiro > Elegir forma de pago. El propósito original de solicitar el medio de pago era puramente informativo (para que el punto físico supiera cómo cobraría al cliente), pero las personas asumían que estaban pagando directamente dentro de la aplicación. Aunque esta falla se identificó en una etapa temprana, pasó desapercibida debido a la falta de constancia en el seguimiento y actualización de los reportes dentro de GitHub.
Acciones inmediatas:
Cultura de revisión continua: Se sensibilizó al equipo sobre la importancia de monitorear activamente los reportes en GitHub para evitar que las alertas tempranas queden en el olvido.
Estandarización de reportes: Se optimizará la estructura y la redacción de los reportes técnicos para eliminar ambigüedades y asegurar que cualquier rol del equipo (diseño o desarrollo) pueda comprenderlos rápidamente.
Protocolo de emergencia: Se diseñó un nuevo protocolo de priorización para clasificar y atender de manera ágil los problemas emergentes según su impacto en el usuario.
Deadline: Estas medidas y el nuevo protocolo de trabajo entrarán en vigencia de forma obligatoria este jueves, antes del próximo despliegue de actualización de la aplicación.


Aprendizajes
El análisis profundo de este incidente nos permitió identificar fallas sistémicas y transformarlas en mejoras concretas para nuestro flujo de trabajo. A partir de esta experiencia, consolidamos las siguientes lecciones:
¿Qué cambiaríamos la próxima vez?
Cuestionar los patrones estándar prematuramente: No daremos por sentado que los flujos de interacción tradicionales (como un checkout clásico) se adaptan a modelos de negocio particulares (como la reserva y retiro físico). En el futuro, validaremos los flujos no convencionales con usuarios reales en etapas de prototipado mucho más tempranas.
Evitar el aislamiento de las alertas: No dependeremos exclusivamente de notificaciones automatizadas en plataformas asincrónicas para problemas de alta complejidad. Ante el menor indicio de un error crítico de UX, activaremos una comunicación directa e interdisciplinaria de inmediato para evitar el "ruido" y acelerar los tiempos de resolución.
¿Qué se ajustó en el proceso para que no vuelva a pasar?
Protocolo de Priorización de Emergentes: Implementamos un nuevo sistema de clasificación obligatoria que obliga al equipo a reajustar la agenda de tareas activas de inmediato cuando ingresa un reporte de alto impacto para el usuario, rompiendo con la rigidez de la planificación previa.
Estandarización y Auditoría en GitHub: Modificamos la estructura con la que se redactan y revisan los reportes en el repositorio. A partir de ahora, se exige un lenguaje accesible para todos los roles del equipo y se fijó una rutina de revisión activa diaria para asegurar que ninguna alerta temprana sea pasada por alto antes de cada actualización de la aplicación.

Reflexión sobre feedback radicalmente sincero
De la subjetividad a la acción protocolar: Al detectarse el problema, mi impulso inicial fue posponer la comunicación hasta contar con métricas más contundentes, priorizando la continuidad del plan de trabajo original. Al carecer de un sistema de alertas tempranas, la decisión de notificar el fallo dependía enteramente de un criterio subjetivo. Esta experiencia evidenció la necesidad de implementar el actual Protocolo de Priorización de Emergentes, el cual desvincula estas decisiones de la intuición personal y nos obliga a reajustar la agenda del equipo de forma objetiva según el nivel de impacto.
Fricción en la comunicación interna: Por otro lado, la falta de claridad en la descripción y fundamentación del reporte inicial provocó que el equipo lo pasara por alto. Para corregir esta deficiencia, la Estandarización y Auditoría en GitHub establece ahora una rutina de revisión activa. Esto garantiza que ningún reporte quede archivado en el olvido o resulte incomprensible para los diferentes roles del proyecto.
Enfoque sin culpables: A medida que las complicaciones se intensificaban, mi primera reacción fue buscar responsables individuales. Sin embargo, aplicando los principios de feedback radicalmente sincero y gestión de equipos vistos en el curso, decidí reconducir la conversación enfocándome en las fallas del proceso y no en las personas. Formular preguntas libres de culpa evitó una actitud defensiva en el equipo, transformando lo que pudo ser una acusación en un espacio colaborativo donde surgieron soluciones inmediatas y transparentes.
El peligro de la deuda técnica: Finalmente, este proceso me permitió reconocer un sesgo crítico en nuestra gestión: la urgencia por reducir la deuda técnica acumulada por el reciente lanzamiento provocó que nos enfocáramos obsesivamente en entregar lo que faltaba, descuidando por completo el monitoreo y mantenimiento de los flujos que ya estaban en producción. Esta lección redefine cómo balancearemos nuestras prioridades en los próximos despliegues. Lado a  
