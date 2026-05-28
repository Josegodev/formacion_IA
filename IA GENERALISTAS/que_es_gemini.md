# Qué es Gemini de Google.

## Índice

1. [Idea rápida](#1-idea-rápida)
2. [Explicación coloquial](#2-explicación-coloquial)
3. [Qué NO es Gemini](#3-qué-no-es-gemini)
4. [Gemini como aplicación, no como único modelo](#4-gemini-como-aplicación-no-como-único-modelo)
5. [Qué puede hacer Gemini](#5-qué-puede-hacer-gemini)
6. [Qué no puede hacer Gemini](#6-qué-no-puede-hacer-gemini)
7. [Diferencia entre Gemini, Google Search y Google Assistant](#7-diferencia-entre-gemini-google-search-y-google-assistant)
8. [Conceptos técnicos mínimos](#8-conceptos-técnicos-mínimos)
9. [Cómo usar Gemini bien](#9-cómo-usar-gemini-bien)
10. [Gemini para usuarios no técnicos](#10-gemini-para-usuarios-no-técnicos)
11. [Gemini para docentes](#11-gemini-para-docentes)
12. [Gemini para empresas](#12-gemini-para-empresas)
13. [Gemini para perfiles técnicos](#13-gemini-para-perfiles-técnicos)
14. [Gemini API](#14-gemini-api)
15. [Diferencia entre usar Gemini en la web y usar Gemini API](#15-diferencia-entre-usar-gemini-en-la-web-y-usar-gemini-api)
16. [Prototipo vs producción](#16-prototipo-vs-producción)
17. [Observabilidad mínima en sistemas con Gemini API](#17-observabilidad-mínima-en-sistemas-con-gemini-api)
18. [Coste operacional](#18-coste-operacional)
19. [Riesgo de dependencia de Google](#19-riesgo-de-dependencia-de-google)
20. [Equivalente on-premise](#20-equivalente-on-premise)
21. [Seguridad](#21-seguridad)
22. [Debugging](#22-debugging)
23. [Ejemplos de buenos prompts para Gemini](#23-ejemplos-de-buenos-prompts-para-gemini)
24. [Buenas prácticas](#24-buenas-prácticas)
25. [Malas prácticas](#25-malas-prácticas)
26. [Comparación rápida: Gemini frente a ChatGPT](#26-comparación-rápida-gemini-frente-a-chatgpt)
27. [Resumen final](#27-resumen-final)

---

## 1. Idea rápida

Gemini es el asistente de inteligencia artificial de Google.

Dicho de forma sencilla: es una herramienta con la que puedes conversar para pedir ayuda con textos, ideas, resúmenes, búsquedas, documentos, imágenes, programación, estudio, organización de tareas y análisis de información.

Se parece a ChatGPT en el sentido de que puedes escribirle preguntas o instrucciones y recibir respuestas generadas por IA. Pero pertenece al ecosistema de Google y puede integrarse con herramientas como Gmail, Documentos, Drive, Hojas de cálculo, Presentaciones, YouTube, Google Search y otros servicios, dependiendo del país, la cuenta, el plan y los permisos disponibles.

Gemini no es “una persona”, no “entiende” como un humano y no garantiza que todo lo que diga sea cierto. Es una aplicación basada en modelos de IA generativa.

---

## 2. Explicación coloquial

Imagina que tienes un ayudante digital al que puedes decirle:

* “Resúmeme este texto.”
* “Explícame esto como si tuviera 12 años.”
* “Ayúdame a escribir un correo profesional.”
* “Dame ideas para una presentación.”
* “Analiza este documento.”
* “Ayúdame a organizar una clase.”
* “Hazme una tabla comparativa.”
* “Explícame este error de código.”
* “Convierte estas notas en un plan de trabajo.”

Eso es Gemini en su uso más básico: una herramienta de ayuda para pensar, escribir, ordenar información y producir borradores.

No sustituye tu criterio. Te ayuda a trabajar más rápido, pero tú tienes que revisar.

---

## 3. Qué NO es Gemini

Gemini no es exactamente “Google Search”.

Google Search busca páginas web y te muestra enlaces, fragmentos y resultados. Gemini genera una respuesta en lenguaje natural. Puede apoyarse en información disponible, herramientas o contexto, pero su salida es una generación, no una garantía absoluta.

Gemini tampoco es simplemente “un chatbot”. Un chatbot tradicional suele seguir reglas cerradas: si preguntas A, responde B. Gemini usa modelos de lenguaje avanzados capaces de generar respuestas nuevas según el contexto.

Gemini tampoco es “un cerebro”. No piensa como una persona, no tiene experiencia propia, no tiene sentido común humano y puede equivocarse.

---

## 4. Gemini como aplicación, no como único modelo

Conviene distinguir varias cosas:

| Concepto                    | Explicación sencilla                                                               |
| --------------------------- | ---------------------------------------------------------------------------------- |
| Gemini                      | Nombre comercial del asistente de IA de Google y también de una familia de modelos |
| Aplicación Gemini           | La interfaz donde el usuario conversa con la IA                                    |
| Modelo Gemini               | El sistema de IA que genera texto, analiza contenido o responde                    |
| Google Workspace con Gemini | Gemini integrado en Gmail, Docs, Sheets, Slides, Meet, etc.                        |
| Gemini API                  | Forma de usar modelos Gemini desde código o aplicaciones propias                   |
| Google AI Studio            | Entorno para probar modelos Gemini y crear prototipos                              |

La idea importante es esta:

> Gemini puede referirse tanto al producto que usa una persona como a la familia de modelos de IA de Google. En formación conviene separar “la app” del “modelo”.

---

## 5. Qué puede hacer Gemini

## 5.1 Escribir y mejorar textos

Gemini puede ayudarte a redactar:

* Correos electrónicos.
* Publicaciones para redes sociales.
* Guiones.
* Resúmenes.
* Descripciones de productos.
* Textos comerciales.
* Documentos internos.
* Instrucciones.
* Preguntas frecuentes.
* Material formativo.

Ejemplo:

```text
Convierte estas notas en un correo profesional, claro y breve.
```

También puede adaptar el tono:

```text
Reescribe este texto para que suene más cercano, pero manteniendo un tono profesional.
```

---

## 5.2 Resumir información

Puede resumir textos largos, documentos, apuntes o conversaciones.

Ejemplo:

```text
Resume este documento en 10 puntos clave y separa conclusiones, riesgos y tareas pendientes.
```

Esto es útil para alumnos, profesores, autónomos, personal administrativo, equipos comerciales y perfiles técnicos.

---

## 5.3 Explicar conceptos difíciles

Gemini puede bajar el nivel de una explicación.

Ejemplo:

```text
Explícame qué es una API como si no supiera nada de informática.
```

O puede subir el nivel:

```text
Ahora explícalo desde el punto de vista de un desarrollador backend.
```

Este uso es muy potente en formación porque permite adaptar una explicación al nivel del alumno.

---

## 5.4 Ayudar con presentaciones

Gemini puede ayudarte a:

* Crear un índice.
* Proponer títulos de diapositivas.
* Resumir un tema.
* Convertir un documento largo en una presentación.
* Preparar notas del ponente.
* Generar preguntas para debate.
* Crear actividades para clase.

Ejemplo:

```text
Crea una estructura de 12 diapositivas para explicar IA generativa a personas sin conocimientos técnicos.
```

---

## 5.5 Trabajar con documentos

Dependiendo de la versión, el plan y el entorno, Gemini puede ayudar a analizar archivos, resumir documentos, extraer información y responder preguntas sobre contenido aportado por el usuario.

Ejemplo:

```text
Analiza este PDF y dime:
1. Qué problema intenta resolver.
2. Qué conceptos clave aparecen.
3. Qué partes son confusas para un alumno principiante.
```

Precaución: si el documento es importante, legal, médico, contractual o financiero, no debe confiarse ciegamente en la respuesta. Hay que verificar.

---

## 5.6 Ayudar en Google Workspace

Gemini puede estar integrado en herramientas de Google como:

* Gmail.
* Google Docs.
* Google Sheets.
* Google Slides.
* Google Drive.
* Google Meet.
* Google Chat.

Esto permite pedir ayuda dentro del entorno donde ya se trabaja.

Ejemplos:

```text
Resume este hilo de correos.
```

```text
Ayúdame a mejorar el tono de este documento.
```

```text
Crea una tabla con los puntos principales de este texto.
```

```text
Propón una estructura para esta presentación.
```

Este es uno de los puntos fuertes de Gemini: su cercanía al ecosistema Google.

---

## 5.7 Ayudar a estudiar

Gemini puede servir como apoyo educativo:

* Explicar temas.
* Crear tests.
* Generar ejemplos.
* Proponer ejercicios.
* Corregir respuestas.
* Preparar esquemas.
* Crear tarjetas de estudio.
* Comparar conceptos.

Ejemplo:

```text
Hazme 10 preguntas tipo test sobre este tema y dame la respuesta correcta con explicación.
```

---

## 5.8 Ayudar con programación

Gemini puede ayudar a perfiles técnicos con:

* Explicar código.
* Generar funciones.
* Detectar errores.
* Proponer estructuras.
* Crear ejemplos.
* Escribir documentación.
* Generar tests.
* Explicar conceptos de desarrollo.

Ejemplo:

```text
Explícame este error de Python y propón una solución sencilla.
```

Pero no debe usarse como sustituto de pruebas reales. El código generado puede fallar, ser inseguro o no encajar con tu proyecto.

---

## 5.9 Analizar imágenes y contenido multimodal

Gemini está diseñado como una IA multimodal.

“Multimodal” significa que puede trabajar no solo con texto, sino también con otros tipos de información, como imágenes, documentos, audio o vídeo, según la versión y las funciones disponibles.

Ejemplo:

```text
Describe esta imagen y dime qué elementos principales aparecen.
```

O:

```text
Analiza esta captura de pantalla y dime qué error parece estar ocurriendo.
```

Esto es útil para soporte, formación, análisis visual, explicación de interfaces y revisión de contenido.

---

## 5.10 Ayudar a investigar

Gemini puede ayudar a explorar un tema, crear mapas conceptuales, plantear preguntas, comparar enfoques y preparar búsquedas.

Ejemplo:

```text
Estoy investigando herramientas de IA para educación. Dame un mapa de temas, riesgos, oportunidades y preguntas clave.
```

Precaución: investigar con IA no significa aceptar la primera respuesta. Hay que contrastar fuentes.

---

# 6. Qué no puede hacer Gemini

## 6.1 No garantiza verdad absoluta

Gemini puede equivocarse.

Puede producir respuestas que parecen correctas pero contienen errores. A esto se le suele llamar “alucinación”, aunque una forma más clara de decirlo sería:

> La IA puede inventar información plausible.

Ejemplo de riesgo:

```text
Dame una normativa española actual sobre protección de datos en centros educativos.
```

Puede responder con una norma real, una norma desactualizada o mezclar información correcta con errores. En temas legales, médicos, financieros o técnicos críticos, siempre hay que verificar.

---

## 6.2 No sustituye a un profesional

Gemini puede ayudar a preparar un borrador, pero no sustituye a:

* Un abogado.
* Un médico.
* Un ingeniero responsable de firma.
* Un asesor financiero.
* Un técnico de prevención.
* Un docente que evalúa oficialmente.
* Un responsable de seguridad.
* Un especialista de cumplimiento normativo.

Puede apoyar, pero no asumir responsabilidad profesional.

---

## 6.3 No sabe automáticamente todo sobre tu empresa

Gemini no conoce los documentos internos de una empresa salvo que:

* Se le proporcionen.
* Tenga permisos para acceder a ellos.
* Esté integrado en un entorno autorizado.
* Se haya configurado una solución específica.

Si le preguntas por un procedimiento interno que no conoce, puede inventar o responder de forma genérica.

---

## 6.4 No siempre entiende bien el contexto

Si el usuario da poca información, Gemini puede interpretar mal la tarea.

Mal prompt:

```text
Hazme esto mejor.
```

Mejor prompt:

```text
Reescribe este correo para enviarlo a un cliente. Quiero un tono profesional, breve y conciliador. No inventes información y conserva las fechas.
```

La calidad de la respuesta depende mucho de la calidad de la instrucción.

---

## 6.5 No siempre respeta formato o restricciones

Puedes pedirle una tabla, JSON, una lista o un texto con cierto número de palabras, pero no siempre lo cumplirá perfectamente.

Ejemplo:

```text
Dame exactamente 100 palabras.
```

Puede dar 94 o 112. Por eso, en usos técnicos o automatizados, hay que validar la salida.

---

## 6.6 No debe usarse sin revisar datos sensibles

Hay que tener cuidado con:

* Datos personales.
* Información médica.
* Contratos.
* Nóminas.
* Documentación confidencial.
* Datos de clientes.
* Información estratégica.
* Código privado.
* Credenciales.
* Tokens.
* Contraseñas.
* Información interna de una empresa.

Regla práctica:

> No pegues en una IA nada que no estarías autorizado a compartir con una herramienta externa.

En empresas, además, hay que revisar la política interna de uso de IA.

---

## 6.7 No convierte automáticamente un proceso en producción

Usar Gemini en una conversación no es lo mismo que tener un sistema de IA en producción.

Una cosa es:

```text
Le pregunto algo a Gemini y me ayuda.
```

Otra cosa es:

```text
Integro Gemini API en una aplicación que atiende usuarios reales, registra trazas, controla errores, mide coste, valida salidas y cumple requisitos de seguridad.
```

La segunda requiere ingeniería.

---

# 7. Diferencia entre Gemini, Google Search y Google Assistant

| Herramienta         | Para qué sirve principalmente                                                |
| ------------------- | ---------------------------------------------------------------------------- |
| Google Search       | Buscar información en la web                                                 |
| Gemini              | Generar, explicar, resumir, razonar y ayudar con tareas usando IA generativa |
| Google Assistant    | Ejecutar acciones sencillas por voz o comandos                               |
| Gemini en Workspace | Ayudar dentro de Gmail, Docs, Sheets, Slides, Drive, etc.                    |
| Gemini API          | Integrar modelos Gemini en aplicaciones propias                              |

Gemini puede usar información y herramientas, pero su salida principal es una respuesta generada.

---

# 8. Conceptos técnicos mínimos

## 8.1 IA

IA significa inteligencia artificial.

Es un campo de la informática que intenta crear sistemas capaces de realizar tareas que normalmente asociamos con capacidades humanas: reconocer patrones, clasificar información, generar texto, detectar anomalías, recomendar opciones o tomar decisiones automatizadas.

---

## 8.2 IA generativa

La IA generativa es un tipo de IA que crea contenido nuevo.

Puede generar:

* Texto.
* Imágenes.
* Código.
* Resúmenes.
* Ideas.
* Estructuras.
* Audio o vídeo, según la herramienta.

Gemini entra dentro de la IA generativa.

---

## 8.3 Modelo de lenguaje

Un modelo de lenguaje es un sistema entrenado para trabajar con texto.

Aprende patrones a partir de grandes cantidades de datos y luego predice qué respuesta es probable o útil según la entrada del usuario.

Simplificando mucho:

> No busca una respuesta en una carpeta. Genera una respuesta calculando patrones lingüísticos y contextuales.

---

## 8.4 LLM

LLM significa Large Language Model, o modelo de lenguaje grande.

Es un modelo entrenado con enormes cantidades de texto y otros datos. Puede responder preguntas, resumir, traducir, clasificar, razonar de forma limitada y generar contenido.

Gemini usa modelos de este tipo, aunque Google también los diseña para trabajar con más modalidades que texto.

---

## 8.5 Modelo multimodal

Un modelo multimodal puede trabajar con varios tipos de entrada.

Por ejemplo:

* Texto.
* Imagen.
* Audio.
* Vídeo.
* Documentos.
* Código.

Esto es importante porque muchas tareas reales no están solo en texto. Una captura de pantalla, una factura, una presentación o una imagen también contienen información.

---

## 8.6 Prompt

Un prompt es la instrucción que le damos a la IA.

Ejemplo simple:

```text
Resume este texto.
```

Ejemplo mejor:

```text
Resume este texto para un público no técnico. Usa máximo 8 viñetas, no inventes datos y separa ideas principales de dudas pendientes.
```

Un buen prompt suele incluir:

* Objetivo.
* Contexto.
* Público.
* Formato de salida.
* Restricciones.
* Criterios de calidad.

---

## 8.7 Contexto

El contexto es la información que el modelo tiene disponible durante una conversación o tarea.

Puede incluir:

* Tu pregunta.
* Mensajes anteriores.
* Documentos adjuntos.
* Archivos.
* Instrucciones.
* Datos de una aplicación conectada.
* Resultado de herramientas externas.

Cuanto mejor sea el contexto, mejor puede ser la respuesta. Pero más contexto no siempre significa mejor resultado: también puede introducir ruido.

---

## 8.8 Ventana de contexto

La ventana de contexto es la cantidad de información que el modelo puede tener en cuenta en una interacción.

Si un documento es demasiado grande, puede que el modelo no use todo con la misma precisión. En tareas serias, conviene pedirle que cite fragmentos, separe evidencia de interpretación y avise cuando no encuentre información.

---

## 8.9 Alucinación

Una alucinación ocurre cuando la IA genera información falsa, inventada o no verificada, pero la presenta de forma convincente.

Ejemplo:

```text
Según el Real Decreto X de 2024...
```

Puede que ese decreto no exista o no diga eso.

Por eso hay que pedir:

```text
No inventes. Si no estás seguro, dilo. Separa hechos confirmados de suposiciones.
```

---

# 9. Cómo usar Gemini bien

## 9.1 Fórmula básica de buen prompt

Una fórmula práctica:

```text
Actúa como [rol].
Necesito [objetivo].
Contexto: [información relevante].
Público: [a quién va dirigido].
Formato: [tabla, lista, resumen, correo, presentación].
Restricciones: [no inventes, máximo X palabras, tono, idioma].
Antes de responder, indica si falta información crítica.
```

Ejemplo:

```text
Actúa como profesor de IA para alumnos sin conocimientos técnicos.
Necesito explicar qué es Gemini.
Público: trabajadores de pymes.
Formato: explicación progresiva con ejemplos.
Restricciones: no uses tecnicismos sin explicarlos y separa qué puede hacer de qué no puede hacer.
```

---

## 9.2 Pedir verificación

Cuando la precisión importa:

```text
Dime qué afirmaciones de tu respuesta deberían verificarse antes de usarlas profesionalmente.
```

O:

```text
Separa la respuesta en:
1. Hechos seguros.
2. Suposiciones.
3. Información que debo comprobar.
```

---

## 9.3 Pedir que no invente

```text
No inventes datos. Si no encuentras evidencia suficiente, responde “no tengo información suficiente”.
```

Esto no elimina todos los errores, pero mejora el control.

---

## 9.4 Pedir formato reutilizable

```text
Devuélvelo en Markdown listo para pegar en un repositorio.
```

```text
Devuélvelo como tabla con columnas: concepto, explicación sencilla, ejemplo y riesgo.
```

```text
Devuélvelo como checklist operativo.
```

---

## 9.5 Iterar

No hay que esperar que la primera respuesta sea perfecta.

Flujo recomendado:

1. Pedir una primera versión.
2. Revisar.
3. Pedir mejoras.
4. Corregir tono.
5. Validar datos.
6. Usar solo lo que tenga sentido.

Ejemplo:

```text
Está demasiado técnico. Reescríbelo para alumnos de FP.
```

```text
Ahora añade una versión para perfiles avanzados.
```

```text
Convierte esto en una actividad de clase de 30 minutos.
```

---

# 10. Gemini para usuarios no técnicos

Para una persona sin conocimientos de informática, Gemini puede servir para:

* Escribir mejor.
* Entender textos difíciles.
* Preparar correos.
* Organizar ideas.
* Resumir documentos.
* Crear esquemas.
* Preparar una presentación.
* Aprender conceptos.
* Ahorrar tiempo en tareas repetitivas de redacción.

Ejemplo práctico:

```text
Tengo que contestar a este cliente. Hazme una respuesta educada, breve y profesional. No prometas nada que no esté en mi texto.
```

---

# 11. Gemini para docentes

Gemini puede ayudar a:

* Preparar clases.
* Crear actividades.
* Adaptar explicaciones a distintos niveles.
* Generar ejemplos.
* Crear cuestionarios.
* Resumir temarios.
* Convertir documentos en guías.
* Preparar rúbricas de evaluación.

Ejemplo:

```text
Crea una actividad de 45 minutos para explicar IA generativa a alumnos sin base técnica. Incluye objetivo, dinámica, materiales y evaluación.
```

Riesgo: puede generar actividades bonitas pero poco realistas. El docente debe adaptar al grupo real.

---

# 12. Gemini para empresas

En una pyme, Gemini puede aportar valor en:

* Atención al cliente.
* Redacción comercial.
* Resumen de reuniones.
* Gestión documental.
* Preparación de propuestas.
* Análisis de correos.
* Generación de ideas.
* Automatización parcial de tareas.
* Soporte interno.

Pero hay que tener cuidado con:

* Privacidad.
* Datos de clientes.
* Información confidencial.
* Cumplimiento normativo.
* Calidad de respuestas.
* Dependencia del proveedor.
* Coste de licencias.
* Límites de uso.

---

# 13. Gemini para perfiles técnicos

Para usuarios avanzados, Gemini puede utilizarse en:

* Prototipado.
* Generación de código.
* Explicación de errores.
* Documentación técnica.
* Análisis de logs.
* Diseño de APIs.
* Creación de tests.
* Generación de scripts.
* Integración mediante API.
* Análisis de datos.
* Sistemas RAG.
* Agentes con herramientas.

Pero en producción hay que controlar:

* Latencia.
* Coste por llamada.
* Límite de tokens.
* Validación de salidas.
* Seguridad.
* Trazabilidad.
* Manejo de errores.
* Versionado de prompts.
* Evaluación de calidad.
* Dependencia cloud.

---

# 14. Gemini API

Gemini API permite usar modelos Gemini desde una aplicación propia.

Ejemplo conceptual:

```text
Usuario -> Mi aplicación -> Gemini API -> Respuesta -> Mi aplicación -> Usuario
```

Esto permite crear:

* Chatbots.
* Asistentes internos.
* Resumidores de documentos.
* Clasificadores de texto.
* Herramientas de soporte.
* Sistemas de búsqueda con IA.
* Automatizaciones.
* Agentes conectados a herramientas.

Pero usar la API no significa automáticamente tener un sistema serio. Hay que construir alrededor del modelo.

---

# 15. Diferencia entre usar Gemini en la web y usar Gemini API

| Uso                                | Nivel         | Ejemplo                                                   |
| ---------------------------------- | ------------- | --------------------------------------------------------- |
| Gemini en navegador                | Usuario final | Preguntar, resumir, escribir, estudiar                    |
| Gemini en Workspace                | Productividad | Ayuda en Gmail, Docs, Sheets, Slides                      |
| Gemini API                         | Desarrollo    | Integrar IA en una aplicación propia                      |
| Gemini en arquitectura empresarial | Producción    | Sistema con logs, seguridad, evaluación, costes y control |

---

# 16. Prototipo vs producción

## Prototipo

Un prototipo es una prueba rápida.

Ejemplo:

```text
Hago una demo que resume PDFs usando Gemini.
```

Características:

* Rápido.
* Útil para validar ideas.
* Poco control de errores.
* Poca seguridad.
* Coste no optimizado.
* Evaluación limitada.
* Difícil de mantener.

## Producción

Un sistema en producción atiende usuarios reales y debe ser fiable.

Necesita:

* Autenticación.
* Logs.
* Métricas.
* Control de errores.
* Validación de respuestas.
* Trazabilidad.
* Gestión de coste.
* Protección de datos.
* Monitorización.
* Pruebas.
* Control de versiones.
* Plan de fallback.

Ejemplo:

```text
Una aplicación interna de empresa que usa Gemini API para responder preguntas sobre documentación corporativa.
```

Aquí no basta con “llamar a Gemini”. Hay que diseñar el sistema.

---

# 17. Observabilidad mínima en sistemas con Gemini API

Si se usa Gemini en una aplicación real, conviene registrar:

* `trace_id`
* `timestamp`
* `user_id` o `session_id`
* `provider`
* `model_id`
* `prompt_version`
* `input_tokens`
* `output_tokens`
* `latency_ms`
* `estimated_cost`
* `status`
* `error_type`
* `tool_called`
* `retrieval_status`
* `document_ids`
* `chunk_ids`
* `fallback_used`
* `schema_validation_ok`

Pregunta operativa clave:

> ¿Quién pidió qué, con qué modelo, con qué prompt, usando qué evidencia, cuánto costó, cuánto tardó y qué falló?

Sin trazabilidad, un sistema de IA es difícil de depurar.

---

# 18. Coste operacional

Gemini puede tener costes directos e indirectos.

## Costes directos

* Licencias de Google AI.
* Planes de Google Workspace.
* Uso de Gemini API.
* Coste por tokens.
* Coste por funciones avanzadas.

## Costes indirectos

* Tiempo de revisión humana.
* Formación de usuarios.
* Integración técnica.
* Seguridad.
* Monitorización.
* Mantenimiento.
* Evaluación de calidad.
* Corrección de errores.

Un error común es pensar que la IA “automatiza gratis”. En realidad, cambia el tipo de trabajo: reduce algunas tareas, pero introduce supervisión, control y mantenimiento.

---

# 19. Riesgo de dependencia de Google

Usar Gemini tiene ventajas:

* Integración con Google.
* Modelos avanzados.
* Multimodalidad.
* Workspace.
* API.
* Ecosistema amplio.

Pero también implica dependencia:

* Cambios de precio.
* Cambios de límites.
* Cambios de modelos.
* Cambios de interfaz.
* Cambios de condiciones.
* Disponibilidad regional.
* Dependencia de cuentas Google.
* Dependencia de permisos y políticas del proveedor.

En arquitectura, esto se llama vendor lock-in.

Una forma de reducirlo es diseñar la aplicación con una capa intermedia:

```text
Mi aplicación -> Adaptador de proveedor -> Gemini / OpenAI / modelo local / otro proveedor
```

Así el modelo puede cambiarse con menos impacto.

---

# 20. Equivalente on-premise

Si Gemini es una solución cloud gestionada por Google, el equivalente on-premise sería ejecutar modelos en infraestructura propia.

Ejemplo:

```text
Servidor propio -> Modelo local -> API interna -> Aplicación
```

Herramientas típicas en entornos locales:

* Ollama.
* vLLM.
* llama.cpp.
* Servidores con GPU.
* Bases vectoriales locales.
* Logs propios.
* Monitorización propia.

Ventajas del enfoque local:

* Más control.
* Menor dependencia cloud.
* Posible mayor privacidad.
* Observabilidad más cercana al runtime.
* Control sobre datos.

Desventajas:

* Más mantenimiento.
* Necesidad de hardware.
* Gestión de GPUs.
* Actualizaciones manuales.
* Menor comodidad.
* Más responsabilidad técnica.

---

# 21. Seguridad

Con Gemini hay que revisar:

* Qué datos se introducen.
* Qué permisos tiene la cuenta.
* Qué aplicaciones están conectadas.
* Qué documentos puede leer.
* Qué usuarios tienen acceso.
* Qué política de empresa aplica.
* Qué retención de datos existe.
* Qué controles administrativos hay.
* Qué información sale del entorno corporativo.

Regla práctica:

> Antes de conectar IA a datos internos, hay que definir permisos, trazabilidad y límites de uso.

---

# 22. Debugging

Cuando Gemini da una mala respuesta, hay que preguntarse:

* ¿El prompt era claro?
* ¿Faltaba contexto?
* ¿Había documentos contradictorios?
* ¿El modelo inventó?
* ¿El usuario pidió algo ambiguo?
* ¿Se usó el modelo correcto?
* ¿Hubo límite de contexto?
* ¿La herramienta tenía acceso a los datos?
* ¿La respuesta fue validada?
* ¿Se registró la ejecución?

En sistemas técnicos, conviene guardar el prompt, el modelo, los documentos usados, la latencia, los tokens y el resultado.

---

# 23. Ejemplos de buenos prompts para Gemini

## 23.1 Para resumir

```text
Resume el siguiente texto para una persona sin conocimientos técnicos.
Usa máximo 8 puntos.
Separa:
1. Ideas principales.
2. Conceptos difíciles.
3. Dudas que habría que aclarar.
No inventes información.
```

## 23.2 Para escribir un correo

```text
Redacta un correo profesional a partir de estas notas.
Tono: claro, cordial y directo.
No añadas promesas ni fechas que no estén en las notas.
Máximo 180 palabras.
```

## 23.3 Para preparar una clase

```text
Actúa como docente de IA aplicada.
Diseña una sesión de 4 horas sobre Gemini para alumnos sin conocimientos técnicos.
Incluye bloques de 45 minutos, ejercicios prácticos y criterios de evaluación.
```

## 23.4 Para revisar un documento

```text
Analiza este documento.
Devuelve:
1. Resumen ejecutivo.
2. Puntos confusos.
3. Riesgos.
4. Preguntas pendientes.
5. Recomendaciones de mejora.
No inventes información que no esté en el documento.
```

## 23.5 Para programación

```text
Actúa como desarrollador backend.
Explica este error paso a paso.
Propón una solución mínima.
Indica riesgos de seguridad, pruebas necesarias y cómo verificar que funciona.
```

---

# 24. Buenas prácticas

* No usar Gemini como fuente única de verdad.
* Revisar siempre las respuestas importantes.
* No introducir datos sensibles sin autorización.
* Dar contexto suficiente.
* Pedir formato claro.
* Pedir que separe hechos de suposiciones.
* Guardar prompts útiles.
* Comparar respuestas cuando el tema sea crítico.
* Validar código antes de usarlo.
* No confundir una demo con un sistema en producción.

---

# 25. Malas prácticas

* Copiar y pegar datos confidenciales sin control.
* Creer todo lo que responde.
* Usarlo para decisiones legales o médicas sin profesional.
* Usarlo sin revisar en comunicación externa.
* Pedir tareas ambiguas.
* No comprobar fuentes.
* No medir coste en integraciones API.
* No registrar errores.
* No validar salidas automáticas.
* Conectar IA a documentos internos sin permisos claros.

---

# 26. Comparación rápida: Gemini frente a ChatGPT

| Aspecto               | Gemini                                                         | ChatGPT                                                                    |
| --------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Empresa               | Google                                                         | OpenAI                                                                     |
| Punto fuerte          | Integración con ecosistema Google                              | Ecosistema ChatGPT, GPTs, herramientas OpenAI                              |
| Uso común             | Productividad, Workspace, búsqueda, documentos, multimodalidad | Conversación, escritura, análisis, programación, asistentes personalizados |
| API                   | Gemini API                                                     | OpenAI API                                                                 |
| Integración ofimática | Muy fuerte en Google Workspace                                 | Depende de integraciones externas o conectores                             |
| Riesgo común          | Dependencia del ecosistema Google                              | Dependencia del ecosistema OpenAI                                          |
| Revisión humana       | Necesaria                                                      | Necesaria                                                                  |

No se trata de cuál es “mejor” de forma absoluta. Depende del caso de uso, coste, integración, seguridad y control.

---

# 27. Resumen final

Gemini es el asistente de IA de Google y una familia de modelos de IA generativa.

Puede ayudar a escribir, resumir, explicar, analizar documentos, estudiar, programar, generar ideas y trabajar dentro del ecosistema Google.

Su valor principal está en aumentar la productividad y facilitar el acceso a tareas complejas mediante lenguaje natural.

Pero tiene límites importantes:

* Puede equivocarse.
* Puede inventar.
* No sustituye a profesionales.
* No debe usarse sin revisar en temas críticos.
* Requiere cuidado con datos sensibles.
* En producción necesita ingeniería, trazabilidad, seguridad y evaluación.

La mejor forma de entender Gemini es esta:

> Gemini no es una verdad automática. Es una herramienta potente de apoyo al pensamiento, la escritura, el análisis y la productividad. Su utilidad depende de cómo se use, qué contexto se le dé y cómo se revise su resultado.
