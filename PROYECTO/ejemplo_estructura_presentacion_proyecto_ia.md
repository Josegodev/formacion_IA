# Estructura recomendada para preparar la presentación final

## Índice

1. Contexto
2. Datos básicos de la presentación
3. Estructura recomendada de diapositivas
4. Guion recomendado para exponer
5. Checklist antes de presentar
6. Plantilla de matriz de riesgos
7. Plantilla de coste operativo
8. Prompts útiles para preparar la presentación
9. Errores frecuentes en presentaciones de proyectos IA
10. Rúbrica de evaluación sugerida
11. Estructura final resumida
12. Recomendación final

---

## Contexto

Esta plantilla sirve para preparar la presentación del proyecto práctico del bloque de IA aplicada.  
El objetivo no es solo enseñar una herramienta, sino demostrar que el alumno sabe elegir, usar, integrar y evaluar herramientas de IA dentro de un flujo de trabajo realista.

La presentación debe responder a esta pregunta principal:

> ¿Qué problema resuelve el proyecto, cómo se ha usado la IA, qué parte ha sido revisada por humanos y qué riesgos operativos tiene?

---

# 1. Datos básicos de la presentación

## Nombre del proyecto

Escribir aquí el nombre del proyecto.

```text
Ejemplo: Sistema IA para clasificar solicitudes de información
```

## Equipo o alumno

```text
Nombre del alumno o grupo:
Fecha:
Curso:
```

## Duración recomendada

```text
Presentación: 7-10 minutos
Preguntas: 3-5 minutos
Demo: incluida dentro de la presentación
```

## Objetivo de la presentación

Explicar en una frase qué se quiere demostrar.

```text
Ejemplo: Demostrar un flujo donde una solicitud recibida por formulario es resumida, clasificada y preparada para revisión humana usando herramientas IA.
```

---

# 2. Estructura recomendada de diapositivas

## Diapositiva 1 — Portada

### Objetivo

Presentar el proyecto de forma clara y profesional.

### Contenido recomendado

- Nombre del proyecto.
- Nombre del equipo o alumno.
- Una frase resumen.
- Imagen, icono o gráfico sencillo relacionado con el proyecto.

### Ejemplo de frase

```text
Un prototipo para recibir, clasificar y preparar respuestas a solicitudes usando IA con revisión humana.
```

### Evitar

- Títulos demasiado genéricos como “Proyecto IA”.
- Portadas con mucho texto.
- Imágenes que no tengan relación con el problema.

---

## Diapositiva 2 — Problema

### Objetivo

Explicar qué problema real se quiere resolver.

### Preguntas que debe responder

- ¿Qué tarea consume tiempo actualmente?
- ¿Quién sufre ese problema?
- ¿Qué pasa si no se resuelve?
- ¿Por qué tiene sentido aplicar IA?

### Estructura sugerida

```text
Problema:
Actualmente, las solicitudes llegan de forma desordenada y requieren revisión manual.

Impacto:
Se pierde tiempo clasificando mensajes repetitivos y preparando respuestas iniciales.

Usuario afectado:
Equipos de atención, soporte, formación, ventas o administración.
```

### Evitar

- Decir simplemente “queremos usar IA”.
- Presentar una solución antes de explicar el problema.
- Usar problemas demasiado amplios o abstractos.

---

## Diapositiva 3 — Usuario objetivo y caso de uso

### Objetivo

Aterrizar el proyecto en un usuario concreto.

### Contenido recomendado

- Tipo de usuario.
- Situación de uso.
- Entrada del sistema.
- Resultado esperado.

### Ejemplo

```text
Usuario objetivo:
Una pequeña empresa o equipo docente que recibe consultas frecuentes.

Caso de uso:
Una persona envía una consulta mediante formulario.
El sistema resume el mensaje, lo clasifica y propone una respuesta inicial.
Un humano revisa antes de enviar.
```

### Evitar

- Decir que sirve “para todo el mundo”.
- No definir quién revisa el resultado.
- Omitir la intervención humana.

---

## Diapositiva 4 — Solución propuesta

### Objetivo

Explicar qué se ha construido.

### Contenido recomendado

- Descripción breve del prototipo.
- Qué recibe como entrada.
- Qué procesamiento hace.
- Qué entrega como salida.
- Qué herramientas intervienen.

### Ejemplo

```text
La solución es un prototipo que recibe solicitudes, usa IA para resumirlas y clasificarlas, guarda los resultados en una tabla o sistema de gestión y genera un borrador de respuesta para revisión humana.
```

### Diagrama simple recomendado

```text
Formulario / entrada
        ↓
Resumen con IA
        ↓
Clasificación
        ↓
Registro en Notion / Sheet / base de datos
        ↓
Respuesta propuesta
        ↓
Revisión humana
```

---

## Diapositiva 5 — Flujo de trabajo con IA

### Objetivo

Mostrar el proceso completo de forma visual.

### Contenido recomendado

Representar el flujo como una cadena de pasos:

```text
1. Entrada de datos
2. Procesamiento con IA
3. Clasificación
4. Registro
5. Generación de respuesta
6. Revisión humana
7. Salida final
```

### Preguntas que debe responder

- ¿Dónde entra la IA?
- ¿Qué tarea concreta realiza?
- ¿Qué datos usa?
- ¿Dónde se guarda el resultado?
- ¿Quién revisa?

### Evitar

- Poner “IA” como una caja mágica.
- No explicar qué prompt o instrucción se ha usado.
- No separar automatización de revisión humana.

---

## Diapositiva 6 — Herramientas utilizadas

### Objetivo

Justificar las herramientas elegidas.

### Tabla recomendada

| Necesidad | Herramienta usada | Motivo |
|---|---|---|
| Código / prototipo | VS Code, Codex, Cursor, Replit o Lovable | Crear o modificar el proyecto |
| Control de versiones | GitHub | Guardar cambios y documentar evolución |
| Investigación | NotebookLM o Perplexity | Analizar fuentes y comparar opciones |
| Diseño | Canva, Freepik o generación de imagen | Preparar material visual |
| Automatización | n8n, Make o Zapier | Conectar entrada, IA y salida |
| Documentación | README, RUNBOOK, docs | Explicar uso, riesgos y mantenimiento |

### Preguntas que debe responder

- ¿Por qué se eligió cada herramienta?
- ¿Qué alternativa se descartó?
- ¿Qué dependencia genera?
- ¿Qué coste o limitación tiene?

### Evitar

- Listar herramientas sin explicar su función.
- Decir que una herramienta es “la mejor” sin justificar.
- Ocultar limitaciones.

---

## Diapositiva 7 — Demo del proyecto

### Objetivo

Demostrar el funcionamiento del prototipo.

### Estructura recomendada para la demo

```text
1. Mostrar la entrada: formulario, mensaje o solicitud.
2. Ejecutar el flujo o mostrar el resultado generado.
3. Enseñar el resumen de IA.
4. Enseñar la clasificación.
5. Mostrar dónde queda registrado.
6. Mostrar la respuesta propuesta.
7. Indicar qué revisaría un humano antes de usarlo.
```

### Reglas para una buena demo

- Usar datos de prueba, no datos personales reales.
- Tener una demo alternativa grabada o capturas por si falla la conexión.
- No improvisar prompts en directo si no es necesario.
- Enseñar un caso normal y, si da tiempo, un caso problemático.

### Datos de prueba sugeridos

```text
Nombre: Laura Gómez
Consulta: Necesito información sobre precios y una demo para mi empresa.
Tipo esperado: Comercial
Prioridad esperada: Media
Respuesta esperada: Propuesta inicial con enlace o contacto.
```

---

## Diapositiva 8 — Qué hizo la IA y qué revisó el humano

### Objetivo

Demostrar criterio crítico.

### Tabla recomendada

| Parte del flujo | Hecho por IA | Revisado por humano |
|---|---|---|
| Resumen de solicitud | Sí | Sí |
| Clasificación | Sí | Sí |
| Respuesta propuesta | Sí | Sí, antes de enviar |
| Código generado | Parcialmente | Sí, mediante revisión de cambios |
| Diseño visual | Parcialmente | Sí |
| Decisiones técnicas | No completamente | Sí |

### Mensaje clave

```text
La IA acelera tareas, pero no elimina la responsabilidad de revisar, validar y corregir.
```

### Evitar

- Presentar la IA como completamente autónoma.
- No explicar los errores encontrados.
- No decir qué se corrigió manualmente.

---

## Diapositiva 9 — Riesgos, límites y errores conocidos

### Objetivo

Explicar la superficie de fallo del sistema.

### Riesgos recomendados para analizar

| Riesgo | Ejemplo | Mitigación |
|---|---|---|
| Alucinación | La IA inventa información | Revisar antes de enviar |
| Clasificación incorrecta | Una consulta urgente se marca como normal | Reglas de prioridad y revisión humana |
| Datos sensibles | Se envía información privada a una herramienta externa | Usar datos ficticios o anonimizar |
| Coste variable | Cada ejecución consume créditos | Medir número de ejecuciones |
| Dependencia cloud | La herramienta deja de estar disponible | Documentar alternativa |
| Falta de logs | No se sabe qué falló | Registrar entrada, salida y error |
| Prompt débil | Respuestas inconsistentes | Versionar prompts |

### Preguntas que debe responder

- ¿Qué puede fallar?
- ¿Cómo se detecta?
- ¿Cómo se recupera?
- ¿Qué parte no debería automatizarse totalmente?

---

## Diapositiva 10 — Coste operativo, seguridad y dependencia

### Objetivo

Evaluar el proyecto como si tuviera que mantenerse.

### Coste operativo

Analizar:

- Coste por uso de herramientas IA.
- Coste por automatizaciones.
- Coste por almacenamiento.
- Coste por mantenimiento humano.
- Coste de debugging cuando falla.

### Seguridad

Analizar:

- Qué datos entran al sistema.
- Dónde se guardan.
- Qué herramientas externas los procesan.
- Quién tiene acceso.
- Qué datos no deberían enviarse a la IA.

### Vendor lock-in

Analizar:

- ¿Se puede exportar el proyecto?
- ¿El código está en GitHub?
- ¿El workflow puede replicarse en otra herramienta?
- ¿Qué pasa si la herramienta cambia precios o desaparece?

### Equivalente on-premise

```text
Make/Zapier → orquestador cloud de procesos.
n8n self-hosted → orquestador de workflows propio.
GitHub → repositorio remoto; equivalente on-premise: GitLab self-hosted o servidor Git.
IA cloud → modelo externo vía API; equivalente local: modelo open-source desplegado internamente, con más mantenimiento.
```

---

## Diapositiva 11 — Documentación y operación mínima

### Objetivo

Mostrar que el proyecto no es solo una demo.

### Documentos recomendados

```text
README.md
RUNBOOK.md
/docs/research.md
/docs/requirements.md
/docs/decision-log.md
/automations/workflow.md
/prompts/prompt-versionado.md
```

### README debe incluir

```text
- Qué hace el proyecto.
- Cómo ejecutarlo o probarlo.
- Herramientas usadas.
- Capturas o demo.
- Limitaciones.
```

### RUNBOOK debe incluir

```text
- Cómo arrancar el sistema.
- Cómo probarlo.
- Qué puede fallar.
- Dónde revisar logs.
- Cómo detenerlo.
- Cómo recuperar una versión anterior.
- Coste estimado.
- Riesgos de seguridad.
```

---

## Diapositiva 12 — Conclusiones y próximos pasos

### Objetivo

Cerrar la presentación con una visión realista.

### Contenido recomendado

- Qué se ha conseguido.
- Qué queda pendiente.
- Qué se mejoraría en una segunda versión.
- Qué herramienta fue más útil.
- Qué parte fue más difícil.
- Qué decisión técnica se cambiaría.

### Ejemplo

```text
Conclusión:
El prototipo demuestra que la IA puede reducir el tiempo de clasificación inicial de solicitudes, pero requiere revisión humana, control de datos, documentación de prompts y trazabilidad de errores.

Próximos pasos:
1. Añadir autenticación.
2. Mejorar logs.
3. Medir precisión de clasificación.
4. Añadir métricas de coste por ejecución.
5. Preparar una versión desplegable.
```

---

# 3. Guion recomendado para exponer

## Apertura

```text
Nuestro proyecto aborda el problema de [problema].
Actualmente, este proceso requiere [tiempo/esfuerzo/revisión manual].
Hemos construido un prototipo que usa IA para [tarea concreta], manteniendo revisión humana en [punto crítico].
```

## Explicación de la solución

```text
El flujo empieza cuando [entrada].
Después, la IA realiza [resumen/clasificación/respuesta].
El resultado se registra en [herramienta].
Antes de usar la respuesta final, una persona revisa [criterios].
```

## Demo

```text
Vamos a probarlo con una solicitud ficticia.
Primero introducimos el mensaje.
Después vemos cómo se resume y clasifica.
Finalmente, revisamos la respuesta generada y el registro del caso.
```

## Cierre

```text
El principal valor del sistema es [beneficio].
El principal riesgo es [riesgo].
La siguiente mejora sería [próximo paso].
```

---

# 4. Checklist antes de presentar

## Contenido

- [ ] El problema está explicado claramente.
- [ ] El usuario objetivo está definido.
- [ ] La solución se entiende sin demasiada explicación.
- [ ] El flujo de IA está representado visualmente.
- [ ] Las herramientas están justificadas.
- [ ] La demo está preparada.
- [ ] Los riesgos están explicados.
- [ ] El coste operativo está estimado.
- [ ] Hay próximos pasos realistas.

## Demo

- [ ] Hay datos de prueba preparados.
- [ ] El flujo se ha probado antes.
- [ ] Hay capturas por si falla la demo.
- [ ] No se usan datos personales reales.
- [ ] Se sabe qué hacer si una herramienta falla.

## Documentación

- [ ] README actualizado.
- [ ] RUNBOOK actualizado.
- [ ] Prompts guardados.
- [ ] Workflow documentado.
- [ ] Decisiones técnicas registradas.
- [ ] Repositorio GitHub actualizado.

## Presentación visual

- [ ] Máximo una idea principal por diapositiva.
- [ ] Texto breve.
- [ ] Capturas legibles.
- [ ] Flujo visual claro.
- [ ] Sin exceso de efectos.
- [ ] Diseño consistente.

---

# 5. Plantilla de matriz de riesgos

| Riesgo | Probabilidad | Impacto | Cómo detectarlo | Mitigación |
|---|---:|---:|---|---|
| Respuesta incorrecta de IA | Media | Alta | Revisión humana | No enviar automáticamente |
| Clasificación errónea | Media | Media | Comparar con etiqueta esperada | Reglas y ejemplos en prompt |
| Fallo de automatización | Media | Media | Logs o prueba manual | Reintentos y alerta |
| Exposición de datos sensibles | Baja/Media | Alta | Revisión de datos enviados | Anonimización |
| Coste inesperado | Media | Media | Medición de ejecuciones | Límite de uso |
| Dependencia de proveedor | Media | Media | Revisión de herramientas externas | Alternativa documentada |

---

# 6. Plantilla de coste operativo

| Recurso | Uso estimado | Coste aproximado | Observaciones |
|---|---:|---:|---|
| Herramienta IA | X consultas/día | € / mes | Depende del plan |
| Automatización | X ejecuciones/día | € / mes | Make/Zapier/n8n |
| Hosting | Bajo/medio | € / mes | Replit/Vercel/otro |
| Almacenamiento | Bajo | € / mes | Notion/Sheet/base de datos |
| Mantenimiento humano | X horas/mes | € / mes | Revisión, errores, mejoras |

## Pregunta clave

```text
¿Cuánto cuesta que este flujo funcione 100 veces?
```

---

# 7. Prompts útiles para preparar la presentación

## Prompt para estructurar la presentación

```text
Actúa como consultor de producto y profesor de IA aplicada.
Ayúdame a preparar una presentación de 10 minutos sobre este proyecto:
[descripción del proyecto]

Quiero una estructura con:
1. problema,
2. usuario objetivo,
3. solución,
4. flujo con IA,
5. herramientas usadas,
6. demo,
7. riesgos,
8. coste operativo,
9. próximos pasos.

La presentación debe ser clara, práctica y sin vender humo.
```

## Prompt para mejorar una diapositiva

```text
Revisa esta diapositiva:
[pegar contenido]

Dime:
1. si se entiende,
2. qué sobra,
3. qué falta,
4. cómo la resumirías,
5. qué imagen o diagrama usarías.
```

## Prompt para generar un diagrama

```text
Convierte este flujo en un diagrama simple para una presentación:
[pegar flujo]

Quiero que tenga máximo 6 pasos, nombres cortos y separación clara entre tarea automática y revisión humana.
```

## Prompt para Canva o herramienta visual

```text
Crea una presentación profesional sobre un prototipo de IA que recibe solicitudes, las resume, las clasifica y prepara una respuesta para revisión humana.
Estilo limpio, tecnológico y sobrio.
Usa diapositivas con poco texto, diagramas simples y enfoque práctico.
```

## Prompt para preparar defensa oral

```text
Hazme 10 preguntas difíciles que podrían hacerme sobre este proyecto.
Incluye preguntas sobre errores de IA, seguridad, coste, dependencia de herramientas, datos sensibles y mantenimiento.
Después dame una respuesta breve y honesta para cada una.
```

---

# 8. Errores frecuentes en presentaciones de proyectos IA

## Error 1 — Presentar herramientas en lugar de problema

Incorrecto:

```text
Hemos usado ChatGPT, Canva, n8n y GitHub.
```

Mejor:

```text
Hemos creado un flujo para reducir el tiempo de clasificación de solicitudes. Para ello usamos IA en el resumen, automatización en el registro y GitHub para documentar el prototipo.
```

## Error 2 — Ocultar fallos

Incorrecto:

```text
El sistema funciona automáticamente.
```

Mejor:

```text
El sistema funciona para casos simples, pero necesita revisión humana porque puede clasificar mal o generar respuestas imprecisas.
```

## Error 3 — No explicar la revisión humana

Incorrecto:

```text
La IA responde al usuario.
```

Mejor:

```text
La IA propone una respuesta, pero el humano la revisa antes de enviarla.
```

## Error 4 — No hablar de costes

Incorrecto:

```text
Es gratis porque usamos herramientas online.
```

Mejor:

```text
El prototipo puede ser gratuito en pruebas, pero en uso real tendría coste por consultas, automatizaciones, almacenamiento y mantenimiento.
```

## Error 5 — Confundir demo con producción

Incorrecto:

```text
Ya está listo para usarse en una empresa.
```

Mejor:

```text
Es un prototipo funcional. Para producción habría que añadir seguridad, logs, pruebas, control de datos y monitorización.
```

---

# 9. Rúbrica de evaluación sugerida

| Criterio | Peso |
|---|---:|
| Claridad del problema y usuario objetivo | 15% |
| Solución y flujo IA bien explicados | 20% |
| Demo funcional o correctamente documentada | 20% |
| Uso razonado de herramientas | 15% |
| Riesgos, costes y límites | 15% |
| Documentación técnica mínima | 10% |
| Calidad visual y comunicación | 5% |

---

# 10. Estructura final resumida

La presentación debería poder resumirse así:

```text
1. Qué problema resolvemos.
2. Para quién lo resolvemos.
3. Qué hemos construido.
4. Dónde entra la IA.
5. Qué herramientas usamos y por qué.
6. Cómo funciona la demo.
7. Qué riesgos tiene.
8. Cuánto podría costar operarlo.
9. Qué documentación existe.
10. Qué haríamos después.
```

---

# 11. Recomendación final

Una buena presentación de IA aplicada no debe intentar convencer diciendo que la IA lo hace todo.  
Debe demostrar que el alumno entiende el proceso completo:

```text
problema → herramienta → flujo → revisión → documentación → riesgos → operación
```

El punto fuerte no es solo el resultado visual o técnico, sino la capacidad de explicar con criterio qué se ha automatizado, qué se ha revisado y qué todavía no está preparado para producción.
