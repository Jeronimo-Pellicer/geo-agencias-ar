# geo-agencias-ar

Skill de Claude que le suma a las auditorías técnicas de GEO lo que a una agencia realmente le hace falta: saber si el cliente está listo, decir la verdad sobre los resultados y hacerlo en español.

No reemplaza a `geo-seo-claude`** ni a `claude-seo` — las complementa. Ellas auditan el sitio. Esta audita la organización, verifica la evidencia antes de mostrarla y genera el reporte que un cliente hispanohablante realmente entiende.

** https://github.com/zubair-trabzada/geo-seo-claude

## ¿Por qué existe?

Ya circulan varias skills de Claude para auditoría técnica de GEO — buenas, gratuitas y con miles de estrellas en GitHub. Todas comparten tres puntos ciegos:

* Auditan un **sitio web**, no la **organización** que tiene que sostener lo que la auditoría recomienda.
* Están construidas y documentadas en **inglés**.
* Ninguna te protege de mostrarle a un cliente un "caso de éxito" que en realidad no tiene sustento — un problema relevante en un mercado de GEO que todavía está definiendo sus estándares de medición y evidencia.

`geo-agencias-ar` se usa **después** de una auditoría técnica, no en lugar de ella.

|                               | Herramientas de auditoría técnica (`geo-seo-claude`, `claude-seo`) | `geo-agencias-ar`                                            |
| ----------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------ |
| **Qué audita**                | El sitio web                                                       | La organización que lo gestiona                              |
| **Idioma**                    | Inglés                                                             | Español (rioplatense)                                        |
| **Salida**                    | Score técnico (0–100)                                              | Diagnóstico de madurez + reporte de negocio                  |
| **Verificación de evidencia** | No incluida                                                        | Checklist dedicado antes de comunicar un resultado           |
| **Cuándo usarla**             | Primero — para auditar el sitio                                    | Después — para diagnosticar la organización y comunicar bien |

## Qué hace

| Módulo                           | Qué hace                                                                                                                                                    | Cuándo usarlo                                                      |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **1. Diagnóstico de madurez**    | Clasifica a la organización en 5 niveles (Nulo → Sistemático) según 6 dimensiones: conocimiento, prácticas, responsables, presupuesto, procesos y medición. | *"¿Qué tan preparada está esta agencia o este cliente?"*           |
| **2. Interpretación técnica**    | Traduce el resultado de una auditoría técnica (propia o de otra skill) a lenguaje de negocio en español.                                                    | *"Tengo un resultado técnico, ayudame a explicárselo al cliente."* |
| **3. Verificación de evidencia** | Clasifica cualquier caso de éxito — propio o de un proveedor — en 4 categorías según su sustento metodológico real.                                         | *"¿Este caso se sostiene si el cliente pregunta de dónde salió?"*  |
| **4. Contenido citable**         | Redacta contenido en español optimizado para ser recuperado y citado por motores generativos.                                                               | *"Escribime algo que las IA puedan citar."*                        |
| **5. Reporte de cliente**        | Integra los módulos anteriores en un reporte final estructurado.                                                                                            | *"Armame el reporte final para el cliente."*                       |

### Un vistazo al Módulo 1 — la escala de madurez

| Nivel            | Características                                              |
| ---------------- | ------------------------------------------------------------ |
| **Nulo**         | No conoce GEO ni realiza ninguna actividad relacionada.      |
| **Inicial**      | Conoce el concepto o probó algo aislado, sin regularidad.    |
| **Experimental** | Ejecuta pruebas ocasionales, sin responsable ni presupuesto. |
| **Operativo**    | Prácticas periódicas, con algún indicador monitoreado.       |
| **Sistemático**  | Responsables, presupuesto, procesos y medición integrada.    |

> La escala completa, operacionalizada en **6 dimensiones × 5 niveles**, vive en [`references/escala-madurez.md`](./references/escala-madurez.md).

## El módulo diferenciador — verificación de evidencia

Antes de que la agencia muestre un "antes y después" a un cliente, el checklist de [`references/checklist-verificacion-evidencia.md`](./references/checklist-verificacion-evidencia.md) lo clasifica en una de cuatro categorías:

| Categoría                                       | ¿Se puede mostrar?                   |
| ----------------------------------------------- | ------------------------------------ |
| **Demostrado con evidencia propia verificable** | Sí                                   |
| **Respaldado, con reservas**                    | Sí, aclarando qué falta              |
| **Hipótesis razonable, no validada**            | No como resultado — como expectativa |
| **Afirmación sin sustento**                     | No                                   |

El objetivo no es impedir la comunicación comercial, sino diferenciar entre **resultado observado**, **evidencia incompleta**, **hipótesis** y **afirmación sin sustento**.

## Instalación

### Si usás claude.ai

`Settings → Capabilities → Customize → Skills`

Subí el `.skill` empaquetado o esta carpeta comprimida.

### Si usás Claude Code

```bash
git clone https://github.com/<tu-usuario>/geo-agencias-ar.git ~/.claude/skills/geo-agencias-ar
```

La skill queda disponible en cualquier proyecto que abras después.

## Estructura del repo

```text
geo-agencias-ar/
├── SKILL.md                                  ← instrucciones principales (los 5 módulos)
├── LICENSE                                   ← licencia MIT
└── references/
    ├── escala-madurez.md                     ← Módulo 1, completo
    ├── marco-geo.md                          ← las 3 dimensiones de GEO (Módulo 2)
    ├── checklist-verificacion-evidencia.md  ← Módulo 3, completo
    └── plantilla-reporte-cliente.md         ← Módulo 5
```

## De dónde viene

Esta skill nació como parte del Trabajo Final de la Licenciatura en Administración de Negocios en Internet (UEAN), sobre adopción de GEO en agencias de marketing digital de la Ciudad Autónoma de Buenos Aires.

El público objetivo es, en consecuencia, agencias hispanohablantes — empezando por CABA, sin quedarse ahí.

## Licencia

Este proyecto está disponible bajo la **licencia MIT**.

Podés usarlo, copiarlo, modificarlo y redistribuirlo, respetando los términos establecidos en la licencia.

Ver [`LICENSE`](./LICENSE).
