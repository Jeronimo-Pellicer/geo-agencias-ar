---
name: geo-agencias-ar
description: 'Complementa auditorías técnicas de GEO/AEO (geo-seo-claude, claude-seo u otras) con diagnóstico organizacional, verificación de evidencia y comunicación con clientes en español, para agencias que atienden pymes en Argentina y LatAm. Usar siempre que se mencione GEO, AEO, optimización para motores generativos, visibilidad en ChatGPT/Perplexity/AI Overviews, o se pida diagnosticar, auditar, reportar o vender GEO a un cliente. Cubre lo que las auditorías técnicas no hacen: (1) madurez de adopción de la organización, no solo del sitio; (2) traducción de hallazgos técnicos a reporte de negocio honesto sobre evidencia vs. proyección; (3) verificación de si un caso de éxito propio o de terceros tiene sustento real antes de mostrarlo a un cliente; (4) contenido citable en español.'
---

# GEO Agencias AR

## Por qué existe esta skill

Las herramientas de auditoría de GEO ya disponibles (geo-seo-claude, claude-seo y similares) hacen un trabajo sólido evaluando **sitios web**: citabilidad, datos estructurados, acceso de crawlers de IA, señales E-E-A-T. Producen un score y una lista de recomendaciones técnicas.

Lo que ninguna de ellas hace es:

- Evaluar la madurez de la **organización** que va a implementar esas recomendaciones (¿tiene presupuesto? ¿responsables? ¿un proceso, o son pruebas sueltas?). Auditan el sitio, no a quien lo gestiona.
- Traducir un resultado técnico a un reporte de negocio en **español**, escrito para que lo entienda el dueño de una pyme, no un desarrollador.
- Proteger a la agencia de reproducir el problema más extendido del propio mercado de GEO hoy: casos de éxito publicados sin verificación independiente, con cifras que no resisten una pregunta directa de un cliente exigente.

Esta skill **no reemplaza una auditoría técnica — la complementa**. Si detectás que el usuario tiene instalada geo-seo-claude, claude-seo, o corrió cualquier auditoría técnica de GEO, tomá ese resultado como insumo de entrada para los módulos 2 y 3. Si no la tiene, seguí igual: los módulos 1, 3 y 4 funcionan de forma independiente.

## Cuándo usar cada módulo

| El usuario dice algo como... | Módulo |
|---|---|
| "¿qué tan preparada está esta agencia/cliente para GEO?", "hacé un diagnóstico de madurez" | Módulo 1 |
| "tengo el resultado de una auditoría técnica, ayudame a explicárselo al cliente" | Módulo 2 |
| "quiero mostrarle este caso de éxito a un cliente", "¿este resultado se sostiene?" | Módulo 3 |
| "escribime contenido para la web que las IA puedan citar" | Módulo 4 |
| "armame el reporte final para el cliente" | Módulo 5 (integra 1-4) |

---

## Módulo 1 — Diagnóstico de madurez organizacional

No preguntes solo "¿la organización hace GEO, sí o no?". Adopción de GEO no es binaria: es un espectro. Usá la escala de cinco niveles en `references/escala-madurez.md` para clasificar a la organización.

Proceso:
1. Reuní información sobre la organización en estas dimensiones: conocimiento del concepto, actividades realizadas, presupuesto asignado, responsables/equipo dedicado, herramientas en uso, frecuencia de medición. Si estás hablando con el usuario directamente, preguntale por estas dimensiones una por una — no asumas.
2. Ubicá a la organización en el nivel que corresponda (Nulo / Inicial / Experimental / Operativo / Sistemático), citando qué evidencia concreta sostiene esa clasificación. Si la evidencia es mixta (ej: tiene herramientas pero no presupuesto), decilo explícitamente en vez de forzar un solo nivel.
3. Identificá el "próximo salto": qué es lo mínimo que la organización necesitaría resolver para subir un nivel — no todos los niveles a la vez.

No inventes datos sobre la organización que el usuario no te dio. Si falta información para clasificar con confianza, decilo y preguntá, en vez de completar el vacío con una suposición.

## Módulo 2 — Interpretación de auditoría técnica

Cuando el usuario te pase el resultado de una auditoría técnica (propia o de otra skill/herramienta):

1. Agrupá los hallazgos técnicos en las tres dimensiones del marco GEO: contenido citable, autoridad externa, aspectos técnicos (ver `references/marco-geo.md`).
2. Por cada hallazgo, traducilo a impacto de negocio en una frase, sin tecnicismo innecesario: no "falta schema markup tipo Product", sino "los sistemas de IA tienen que adivinar qué vendés en vez de leerlo directamente en el código de la página — eso reduce las chances de aparecer en una recomendación."
3. Priorizá 3 a 5 acciones, no una lista completa de 20 ítems. Un cliente que recibe 20 tareas no hace ninguna.
4. Nunca conviertas un score técnico (0-100, o el que use la herramienta de origen) en una promesa de resultado de negocio. Un score de citabilidad alto no es lo mismo que "vas a vender más" — separá siempre visibilidad de resultado comercial.

## Módulo 3 — Verificación de evidencia antes de comunicar resultados

Este es el módulo que más diferencia a esta skill de lo que ya existe. Antes de que el usuario le muestre un "antes y después" a un cliente o prospecto —sea un caso propio o uno de un proveedor externo—, corré el checklist de `references/checklist-verificacion-evidencia.md`.

El checklist evalúa:
- ¿Hay una línea de base documentada (métrica antes de la intervención), o el "antes" es un recuerdo aproximado?
- ¿Se descartaron explicaciones alternativas (estacionalidad, otras campañas corriendo en simultáneo, cambios del propio motor de búsqueda)?
- ¿Quién midió el resultado — una parte independiente, o la misma agencia que hizo la intervención?
- ¿La cifra que se quiere mostrar es de visibilidad/citación, o ya salta directo a "resultado de negocio" sin mostrar los pasos intermedios (visibilidad → tráfico → conversión)?

Con esas respuestas, clasificá el caso en una de cuatro categorías y decíselo así de directo al usuario:
- **Demostrado con evidencia propia verificable**: línea de base clara, medición propia, explicaciones alternativas consideradas.
- **Respaldado, con reservas**: hay datos, pero sin línea de base sólida o sin descartar causas alternativas — se puede mostrar, pero con el matiz explícito.
- **Hipótesis razonable, no validada**: es plausible pero no hay medición real detrás — no se debería presentar como resultado.
- **Afirmación sin sustento**: es una cifra de marketing (propia o de terceros) sin ninguna documentación verificable — no usar frente a un cliente.

No ablandes esta clasificación para hacer sentir mejor al usuario. El valor de este módulo es exactamente no hacer lo que hace el resto del mercado.

## Módulo 4 — Contenido citable en español

Cuando el usuario pida contenido optimizado para GEO:

- Escribí bloques autocontenidos de 130-170 palabras que respondan una pregunta concreta desde la primera oración, sin necesitar el párrafo anterior para tener sentido. Los sistemas de recuperación de los motores generativos indexan fragmentos, no páginas enteras.
- Incluí datos verificables (cifras, fechas, fuentes) cuando existan. Si el usuario no te dio una fuente para un dato, no lo inventes — dejá el espacio marcado o pedí la fuente.
- Preferí formato pregunta-respuesta cuando el contenido se preste a eso (FAQ), porque calza naturalmente con cómo un motor generativo fragmenta y recupera contenido.
- Recordá al usuario que la efectividad de prácticas específicas —como llms.txt— es un tema en discusión activa dentro del propio ecosistema de herramientas GEO (algunas fuentes lo tratan como estándar emergente, otras cuestionan que sea hoy una palanca real de citación). No lo presentes como garantía.

## Módulo 5 — Reporte final para el cliente

Integra los módulos anteriores en el formato de `references/plantilla-reporte-cliente.md`. Estructura: diagnóstico de madurez (Módulo 1) → hallazgos técnicos traducidos a negocio (Módulo 2) → qué se puede afirmar con qué nivel de confianza (Módulo 3) → próximos pasos priorizados. Nunca mezcles categorías de evidencia distintas en la misma frase sin aclarar cuál es cuál.

## Principio transversal

En cada módulo, el default es la honestidad sobre la certeza, no la persuasión. Si no hay evidencia suficiente para afirmar algo, decí exactamente eso — es lo que hace que esta skill le sirva a una agencia frente a un cliente que después vuelve a preguntar.
