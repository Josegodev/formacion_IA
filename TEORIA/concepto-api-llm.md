# Qué es una API en el mundo de los LLM

> Guía progresiva para personas sin conocimientos técnicos, equipos de negocio, docentes, perfiles creativos y usuarios avanzados que quieren entender qué significa “usar un LLM por API”.

---

## Índice

1. [Idea rápida, en lenguaje coloquial](#1-idea-rápida-en-lenguaje-coloquial)
2. [Analogía simple: restaurante y cocina](#2-analogía-simple-restaurante-y-cocina)
3. [Qué es exactamente una API](#3-qué-es-exactamente-una-api)
4. [Diferencia entre usar un chat y usar una API](#4-diferencia-entre-usar-un-chat-y-usar-una-api)
5. [Para qué sirve una API de LLM](#5-para-qué-sirve-una-api-de-llm)
6. [Qué NO es una API de LLM](#6-qué-no-es-una-api-de-llm)
7. [Qué puede hacer una API de LLM](#7-qué-puede-hacer-una-api-de-llm)
8. [Qué no puede hacer bien o no debería hacer sola](#8-qué-no-puede-hacer-bien-o-no-debería-hacer-sola)
9. [Componentes básicos de una llamada a una API de LLM](#9-componentes-básicos-de-una-llamada-a-una-api-de-llm)
10. [Ejemplo conceptual de petición y respuesta](#10-ejemplo-conceptual-de-petición-y-respuesta)
11. [Qué son los tokens en una API de LLM](#11-qué-son-los-tokens-en-una-api-de-llm)
12. [Qué es la ventana de contexto](#12-qué-es-la-ventana-de-contexto)
13. [API key: la llave de acceso](#13-api-key-la-llave-de-acceso)
14. [Endpoint: la dirección a la que se llama](#14-endpoint-la-dirección-a-la-que-se-llama)
15. [Request y response: pedir y recibir](#15-request-y-response-pedir-y-recibir)
16. [JSON: el formato habitual para hablar con APIs](#16-json-el-formato-habitual-para-hablar-con-apis)
17. [Qué significa integrar un LLM por API](#17-qué-significa-integrar-un-llm-por-api)
18. [Casos de uso habituales](#18-casos-de-uso-habituales)
19. [De “chatbot” a “sistema”](#19-de-chatbot-a-sistema)
20. [Conceptos técnicos mínimos](#20-conceptos-técnicos-mínimos)
21. [Ejemplo con `curl`](#21-ejemplo-con-curl)
22. [Ejemplo con pseudocódigo](#22-ejemplo-con-pseudocódigo)
23. [Parámetros frecuentes en APIs de LLM](#23-parámetros-frecuentes-en-apis-de-llm)
24. [Herramientas y function calling](#24-herramientas-y-function-calling)
25. [RAG: conectar el modelo con documentos](#25-rag-conectar-el-modelo-con-documentos)
26. [Embeddings: buscar por significado](#26-embeddings-buscar-por-significado)
27. [Coste y consumo](#27-coste-y-consumo)
28. [Latencia: cuánto tarda en responder](#28-latencia-cuánto-tarda-en-responder)
29. [Rate limits: límites de uso](#29-rate-limits-límites-de-uso)
30. [Errores habituales al usar APIs de LLM](#30-errores-habituales-al-usar-apis-de-llm)
31. [Seguridad y privacidad](#31-seguridad-y-privacidad)
32. [Evaluación: cómo saber si funciona bien](#32-evaluación-cómo-saber-si-funciona-bien)
33. [Arquitectura básica de una aplicación con API de LLM](#33-arquitectura-básica-de-una-aplicación-con-api-de-llm)
34. [Ejemplo completo de flujo: resumen automático de reuniones](#34-ejemplo-completo-de-flujo-resumen-automático-de-reuniones)
35. [Patrones útiles de diseño](#35-patrones-útiles-de-diseño)
36. [Mitos frecuentes](#36-mitos-frecuentes)
37. [Buenas prácticas para empezar](#37-buenas-prácticas-para-empezar)
38. [Checklist antes de usar una API de LLM en producción](#38-checklist-antes-de-usar-una-api-de-llm-en-producción)
39. [Glosario mínimo](#39-glosario-mínimo)
40. [Resumen final](#40-resumen-final)
41. [Lectura recomendada dentro del repo](#41-lectura-recomendada-dentro-del-repo)

---

## 1. Idea rápida, en lenguaje coloquial

Una **API** es una forma de pedirle algo a un sistema desde otro sistema.

Dicho de manera sencilla:

> Una API es como una ventanilla, un camarero o un enchufe estándar que permite que dos programas se entiendan.

Cuando usas ChatGPT desde una página web, tú escribes en una interfaz visual: una caja de texto, botones, historial, menús, etc.

Cuando una aplicación usa un LLM por API, no hay necesariamente una pantalla de chat. En su lugar, un programa envía una petición al modelo y recibe una respuesta.

Por ejemplo:

- Una web puede enviar una pregunta a un modelo de lenguaje.
- Un CRM puede pedir un resumen automático de una conversación con un cliente.
- Una app educativa puede pedir una explicación adaptada al nivel de un alumno.
- Un sistema interno puede clasificar correos, redactar respuestas o extraer datos de documentos.

La API es el puente entre la aplicación y el modelo.

---

## 2. Analogía simple: restaurante y cocina

Imagina un restaurante.

- Tú no entras directamente en la cocina.
- Le dices al camarero qué quieres.
- El camarero lleva tu pedido a la cocina.
- La cocina prepara algo.
- El camarero te trae el resultado.

En esta analogía:

| Elemento | En una API de LLM |
|---|---|
| Cliente del restaurante | Tu aplicación, web, app móvil o sistema interno |
| Camarero | La API |
| Pedido | La petición o `request` |
| Cocina | El modelo de lenguaje |
| Plato servido | La respuesta o `response` |
| Carta del restaurante | La documentación de la API |
| Precio del plato | Coste por uso, normalmente asociado a tokens |

La API no “piensa” por sí sola como si fuera una persona. La API es el canal que permite mandar instrucciones al modelo y recibir resultados.

---

## 3. Qué es exactamente una API

API significa **Application Programming Interface**.

En español podríamos traducirlo como:

> Interfaz de programación de aplicaciones.

Pero esa traducción suena más difícil de lo que realmente es.

Una API es un conjunto de reglas para que un programa pueda comunicarse con otro.

Esas reglas indican cosas como:

- Dónde hay que enviar la petición.
- Qué datos hay que mandar.
- En qué formato se mandan.
- Qué tipo de respuesta se recibirá.
- Qué errores pueden ocurrir.
- Cómo se controla el acceso.
- Cuánto se puede usar el servicio.

En el caso de los LLM, una API permite que una aplicación le diga a un modelo algo como:

> “Resume este texto en cinco líneas.”

O:

> “Clasifica este mensaje como urgente, normal o irrelevante.”

O:

> “Genera una respuesta amable para este cliente.”

La aplicación envía esa instrucción al modelo mediante la API y recibe una respuesta que puede usar dentro de su propio flujo.

---

## 4. Diferencia entre usar un chat y usar una API

Mucha gente conoce los LLM a través de una interfaz de chat. Eso es solo una forma de usarlos.

Una API permite integrar el modelo dentro de otros productos, procesos o automatizaciones.

| Uso mediante chat | Uso mediante API |
|---|---|
| Una persona escribe manualmente | Un programa envía la petición |
| Hay una interfaz visual | Puede no haber interfaz visible |
| Se usa caso por caso | Se puede automatizar a gran escala |
| El usuario copia y pega información | La aplicación puede enviar datos directamente |
| La conversación suele ser manual | El modelo forma parte de un flujo de trabajo |

Ejemplo práctico:

**Uso por chat:**

Una persona copia un correo largo, lo pega en ChatGPT y pide:

> “Resume este correo.”

**Uso por API:**

Un sistema recibe automáticamente un correo, lo envía a un LLM por API, obtiene un resumen y lo guarda en la ficha del cliente.

La segunda opción permite automatización.

---

## 5. Para qué sirve una API de LLM

Una API de LLM sirve para incorporar capacidades de lenguaje natural dentro de aplicaciones, productos o procesos.

Puede servir para tareas como:

- Resumir textos.
- Redactar borradores.
- Traducir.
- Reescribir con otro tono.
- Clasificar mensajes.
- Extraer información de documentos.
- Contestar preguntas sobre contenido proporcionado.
- Crear asistentes internos.
- Generar ideas.
- Explicar conceptos.
- Ayudar a programar.
- Analizar opiniones de clientes.
- Convertir lenguaje natural en estructuras de datos.
- Crear chatbots o copilotos.
- Automatizar partes de procesos administrativos.

La clave es esta:

> Una API de LLM permite que un programa use capacidades de lenguaje como si fueran una pieza más de software.

---

## 6. Qué NO es una API de LLM

Es importante evitar malentendidos.

Una API de LLM **no es magia**.

Tampoco es, por sí sola:

- Una base de datos.
- Un cerebro humano.
- Una garantía de verdad.
- Un sistema con criterio legal, médico o financiero propio.
- Un sustituto automático de expertos.
- Una solución completa de seguridad.
- Una memoria perfecta.
- Un buscador actualizado, salvo que se conecte explícitamente a fuentes externas.
- Una aplicación completa lista para usar.

Una API es un acceso a una capacidad. Pero para construir una solución fiable hace falta diseñar bien el sistema alrededor.

---

## 7. Qué puede hacer una API de LLM

Una API de LLM puede ayudar mucho cuando la tarea tiene que ver con lenguaje, patrones, contexto o generación de contenido.

### 7.1 Entender instrucciones en lenguaje natural

Puedes enviar instrucciones como:

> “Convierte este texto en una lista de tareas.”

O:

> “Explícalo para una persona sin conocimientos técnicos.”

El modelo interpreta la instrucción y genera una respuesta.

### 7.2 Generar texto

Puede redactar:

- Emails.
- Informes.
- Descripciones de productos.
- Resúmenes.
- Guiones.
- Preguntas frecuentes.
- Explicaciones.
- Borradores de documentación.

### 7.3 Transformar texto

Puede cambiar un texto sin empezar desde cero:

- Hacerlo más breve.
- Hacerlo más formal.
- Simplificarlo.
- Traducirlo.
- Convertirlo en tabla.
- Convertirlo en pasos.
- Adaptarlo a un público concreto.

### 7.4 Clasificar información

Puede etiquetar textos según categorías.

Ejemplos:

- Urgente / no urgente.
- Queja / consulta / felicitación.
- Riesgo alto / medio / bajo.
- Tema comercial / técnico / administrativo.
- Sentimiento positivo / neutro / negativo.

### 7.5 Extraer datos

Puede recibir texto no estructurado y devolver información organizada.

Por ejemplo, de este texto:

> “La reunión será el martes 12 de marzo a las 10:30 con Marta López.”

Puede extraer:

```json
{
  "fecha": "12 de marzo",
  "hora": "10:30",
  "persona": "Marta López",
  "tipo_evento": "reunión"
}
```

### 7.6 Responder sobre información proporcionada

Si le das un texto, puede contestar preguntas sobre ese texto.

Ejemplo:

> “Según este contrato, ¿cuándo vence el plazo de pago?”

El modelo puede buscar en el contenido proporcionado y generar una respuesta basada en él.

### 7.7 Ayudar a tomar decisiones, pero no decidir solo

Puede comparar opciones, resumir pros y contras, detectar riesgos o preparar escenarios.

Pero en decisiones importantes, la responsabilidad debe seguir siendo humana.

---

## 8. Qué no puede hacer bien o no debería hacer sola

### 8.1 No garantiza la verdad

Un LLM puede equivocarse.

Puede generar una respuesta que suene convincente pero sea incorrecta. A esto suele llamarse **alucinación**.

Por eso, cuando se necesita exactitud, conviene:

- Darle fuentes concretas.
- Verificar sus respuestas.
- Usar sistemas de recuperación de información.
- Pedir citas o referencias cuando proceda.
- Aplicar validaciones automáticas.
- Mantener revisión humana en procesos críticos.

### 8.2 No conoce automáticamente tus datos privados

El modelo no sabe lo que hay en tu empresa, tus documentos, tus clientes o tu base de datos a menos que se lo proporciones o lo conectes a esos sistemas.

Una API de LLM no accede por sí sola a:

- Tus archivos.
- Tu CRM.
- Tu correo.
- Tu ERP.
- Tus documentos internos.
- Internet.
- Bases de datos privadas.

Para eso hay que construir integraciones específicas.

### 8.3 No sustituye una base de datos

Una base de datos guarda información de forma estructurada y recuperable.

Un LLM genera respuestas a partir de patrones y contexto.

No conviene usar un LLM como si fuera el lugar principal donde guardar datos importantes.

### 8.4 No es ideal para cálculos exactos sin herramientas

Los modelos pueden hacer razonamientos matemáticos simples, pero no son calculadoras perfectas.

Para cálculos críticos conviene usar herramientas externas: código, hojas de cálculo, bases de datos o sistemas de cálculo.

### 8.5 No debería tomar decisiones sensibles sin supervisión

En contextos como salud, derecho, finanzas, recursos humanos o seguridad, el modelo puede ayudar, pero no debe ser la única autoridad.

Ejemplos de tareas delicadas:

- Diagnosticar enfermedades.
- Rechazar candidatos automáticamente.
- Aprobar créditos.
- Dar asesoramiento legal definitivo.
- Tomar decisiones disciplinarias.
- Evaluar riesgos de seguridad sin control humano.

### 8.6 No entiende el mundo como una persona

Aunque pueda escribir muy bien, no tiene conciencia, experiencia personal ni comprensión humana en sentido pleno.

Trabaja con patrones del lenguaje y relaciones aprendidas durante su entrenamiento, más la información que recibe en el contexto de la petición.

---

## 9. Componentes básicos de una llamada a una API de LLM

Una llamada típica a una API de LLM tiene varias piezas.

### 9.1 Modelo

El **modelo** es el sistema de IA que va a generar la respuesta.

Ejemplo conceptual:

```text
modelo = "modelo-de-lenguaje"
```

Diferentes modelos pueden tener diferentes capacidades, costes, velocidades y límites.

### 9.2 Mensaje o prompt

El **prompt** es la instrucción que se le da al modelo.

Ejemplo:

```text
Resume este texto en tres puntos.
```

En APIs modernas suele enviarse una lista de mensajes con roles.

Ejemplo simplificado:

```json
[
  {
    "role": "system",
    "content": "Eres un asistente claro y preciso."
  },
  {
    "role": "user",
    "content": "Resume este texto en tres puntos: ..."
  }
]
```

### 9.3 Parámetros

Los **parámetros** son ajustes que modifican cómo responde el modelo.

Algunos parámetros frecuentes son:

- Temperatura.
- Top-p.
- Máximo de tokens.
- Formato de salida.
- Penalizaciones de repetición.
- Herramientas disponibles.
- Streaming activado o desactivado.

No todos los proveedores usan exactamente los mismos nombres ni ofrecen las mismas opciones.

### 9.4 Petición o request

La **petición** es el paquete completo que se envía a la API.

Incluye normalmente:

- El modelo elegido.
- Los mensajes.
- Los parámetros.
- La identificación de acceso.
- Opcionalmente, herramientas, archivos, contexto o instrucciones adicionales.

### 9.5 Respuesta o response

La **respuesta** es lo que devuelve la API.

Puede incluir:

- El texto generado.
- Datos estructurados.
- Información de uso.
- Motivos de finalización.
- Mensajes de error.
- Identificadores técnicos.
- Consumo de tokens.

---

## 10. Ejemplo conceptual de petición y respuesta

### Petición

```json
{
  "model": "modelo-llm",
  "messages": [
    {
      "role": "system",
      "content": "Responde de forma clara y breve."
    },
    {
      "role": "user",
      "content": "Explica qué es una API en una frase."
    }
  ],
  "max_tokens": 100
}
```

### Respuesta

```json
{
  "content": "Una API es una forma estándar para que un programa le pida algo a otro programa y reciba una respuesta.",
  "usage": {
    "input_tokens": 32,
    "output_tokens": 21,
    "total_tokens": 53
  }
}
```

Este ejemplo está simplificado. Cada proveedor puede devolver una estructura distinta.

---

## 11. Qué son los tokens en una API de LLM

Los LLM no procesan exactamente palabras como las entendemos las personas. Procesan unidades llamadas **tokens**.

Un token puede ser:

- Una palabra corta.
- Parte de una palabra.
- Un signo de puntuación.
- Un fragmento de texto.

Ejemplo aproximado:

```text
"Hola, ¿cómo estás?"
```

Podría dividirse en varios tokens, no necesariamente uno por palabra.

En una API, los tokens importan porque suelen afectar a:

- El coste.
- La velocidad.
- La longitud máxima de entrada.
- La longitud máxima de salida.
- La cantidad de contexto que el modelo puede manejar.

### Tipos de tokens

| Tipo | Qué significa |
|---|---|
| Tokens de entrada | Lo que envías al modelo |
| Tokens de salida | Lo que el modelo genera |
| Tokens totales | Entrada + salida |
| Ventana de contexto | Máximo de tokens que el modelo puede considerar en una petición |

Ejemplo:

Si envías un documento largo y pides un resumen, pagas o consumes tanto por el documento enviado como por el resumen generado.

---

## 12. Qué es la ventana de contexto

La **ventana de contexto** es la cantidad máxima de información que el modelo puede tener en cuenta en una petición.

Incluye:

- Instrucciones del sistema.
- Mensajes anteriores.
- Texto del usuario.
- Documentos añadidos.
- Ejemplos.
- Respuestas previas.
- Información de herramientas.
- Tokens que se generarán en la salida.

Una forma sencilla de entenderlo:

> La ventana de contexto es la “mesa de trabajo” del modelo. Todo lo que cabe en la mesa puede usarlo; lo que no cabe, queda fuera.

Si la conversación o los documentos son demasiado largos, hay que:

- Resumir.
- Dividir en partes.
- Recuperar solo fragmentos relevantes.
- Usar una base documental con búsqueda.
- Diseñar bien el flujo de información.

---

## 13. API key: la llave de acceso

Muchas APIs se usan con una **API key**.

Una API key es una clave secreta que identifica quién está usando el servicio.

Funciona como una llave.

No se debe compartir públicamente.

No debe aparecer en:

- Repositorios públicos.
- Capturas de pantalla.
- Código subido a GitHub.
- Documentos compartidos.
- Frontends visibles por usuarios.
- Mensajes de error expuestos.

Buenas prácticas:

- Guardarla en variables de entorno.
- Rotarla si se sospecha que se ha filtrado.
- Usar permisos mínimos.
- Separar claves de desarrollo y producción.
- Monitorizar el consumo.
- No ponerla directamente en el código.

---

## 14. Endpoint: la dirección a la que se llama

Un **endpoint** es una dirección concreta de una API.

Es el lugar al que se envía la petición.

Podemos imaginarlo como una dirección postal o una ventanilla concreta.

Ejemplo conceptual:

```text
https://api.proveedor.com/v1/respuestas
```

No todas las peticiones van al mismo endpoint. Puede haber endpoints para:

- Generar texto.
- Crear embeddings.
- Subir archivos.
- Consultar modelos.
- Usar herramientas.
- Obtener información de uso.
- Gestionar lotes de peticiones.

---

## 15. Request y response: pedir y recibir

En una API hay dos momentos clave:

1. **Request**: lo que tu aplicación envía.
2. **Response**: lo que la API devuelve.

Ejemplo no técnico:

```text
Request:
"Resume este texto para un niño de 12 años."

Response:
"Este texto trata sobre..."
```

Ejemplo más técnico:

```json
{
  "input": "Resume este texto para un niño de 12 años: ..."
}
```

Y la respuesta podría ser:

```json
{
  "output": "El texto explica que..."
}
```

---

## 16. JSON: el formato habitual para hablar con APIs

Muchas APIs usan **JSON**, un formato de texto estructurado.

JSON permite representar información con pares de clave y valor.

Ejemplo:

```json
{
  "nombre": "Ana",
  "edad": 34,
  "idiomas": ["español", "inglés"]
}
```

En APIs de LLM, JSON es útil porque permite mandar instrucciones de forma ordenada y recibir resultados estructurados.

Ejemplo:

```json
{
  "tarea": "clasificar_email",
  "texto": "Necesito ayuda urgente con mi factura.",
  "categorias": ["urgente", "normal", "baja_prioridad"]
}
```

Respuesta esperada:

```json
{
  "categoria": "urgente",
  "motivo": "El mensaje contiene la palabra urgente y expresa necesidad inmediata."
}
```

---

## 17. Qué significa integrar un LLM por API

Integrar un LLM por API significa conectar el modelo con una aplicación real.

No es solo “hacer una pregunta”.

Es diseñar un flujo.

Por ejemplo, un sistema de atención al cliente podría hacer esto:

1. Recibe un mensaje de un cliente.
2. El sistema limpia o prepara el texto.
3. Envía el mensaje al LLM por API.
4. El LLM clasifica la intención.
5. El sistema busca información relevante en la base de conocimiento.
6. Envía esa información al LLM.
7. El LLM redacta una respuesta.
8. La respuesta se muestra a un agente humano.
9. El agente revisa, edita y envía.

La API es solo una parte de la solución.

---

## 18. Casos de uso habituales

### 18.1 Atención al cliente

- Resumir conversaciones.
- Sugerir respuestas.
- Clasificar tickets.
- Detectar urgencia.
- Identificar sentimiento.
- Buscar respuestas en una base de conocimiento.

### 18.2 Educación

- Explicar conceptos a distintos niveles.
- Generar ejercicios.
- Dar feedback sobre redacciones.
- Crear itinerarios de aprendizaje.
- Adaptar materiales.
- Convertir apuntes en preguntas de repaso.

### 18.3 Marketing y comunicación

- Crear borradores.
- Adaptar tono.
- Generar variantes.
- Resumir estudios de mercado.
- Clasificar comentarios.
- Preparar calendarios de contenido.

### 18.4 Recursos humanos

- Resumir CVs.
- Preparar preguntas de entrevista.
- Clasificar solicitudes.
- Redactar comunicaciones internas.
- Analizar encuestas de clima laboral.

En este ámbito conviene extremar precauciones para evitar sesgos y decisiones automatizadas injustas.

### 18.5 Legal y compliance

- Resumir contratos.
- Detectar cláusulas.
- Comparar versiones.
- Preparar borradores.
- Organizar documentación.

No debe sustituir la revisión profesional.

### 18.6 Operaciones internas

- Automatizar informes.
- Extraer datos de emails.
- Preparar actas.
- Convertir notas en tareas.
- Documentar procesos.
- Generar respuestas internas.

### 18.7 Desarrollo de software

- Generar fragmentos de código.
- Explicar errores.
- Crear documentación técnica.
- Revisar cambios.
- Escribir pruebas.
- Convertir requisitos en tareas técnicas.

---

## 19. De “chatbot” a “sistema”

Un error común es pensar que usar una API de LLM significa simplemente crear un chatbot.

Un chatbot es solo una posible interfaz.

Una API de LLM puede estar detrás de:

- Un botón de “resumir”.
- Un sistema de clasificación automática.
- Un generador de informes.
- Una herramienta de búsqueda semántica.
- Un asistente dentro de una intranet.
- Un evaluador de respuestas abiertas.
- Un extractor de datos.
- Un copiloto para empleados.
- Una automatización sin interfaz visible.

La pregunta importante no es:

> “¿Cómo meto IA aquí?”

La pregunta útil es:

> “¿Qué parte del proceso requiere entender, transformar o generar lenguaje?”

---

## 20. Conceptos técnicos mínimos

### 20.1 Cliente

El **cliente** es el programa que llama a la API.

Puede ser:

- Una web.
- Una app móvil.
- Un script.
- Un servidor.
- Una automatización.
- Una herramienta interna.

### 20.2 Servidor

El **servidor** es el sistema que recibe la petición, la procesa y devuelve una respuesta.

En este caso, el servidor del proveedor de IA recibe la petición y coordina la respuesta del modelo.

### 20.3 HTTP

Muchas APIs funcionan sobre **HTTP**, el mismo protocolo general que se usa para navegar por la web.

Cuando visitas una página, tu navegador hace una petición HTTP.

Cuando una app llama a una API, también suele hacer una petición HTTP.

### 20.4 Método

El método indica qué tipo de operación se quiere hacer.

El más típico para enviar datos a un modelo es `POST`.

Ejemplo conceptual:

```text
POST /v1/responses
```

Significa:

> “Voy a enviar información para que el servidor la procese.”

### 20.5 Cabeceras o headers

Las **cabeceras** contienen información adicional sobre la petición.

Por ejemplo:

- Tipo de contenido.
- Clave de autorización.
- Versión.
- Identificador del proyecto.

Ejemplo conceptual:

```text
Authorization: Bearer TU_API_KEY
Content-Type: application/json
```

### 20.6 Body

El **body** es el contenido principal de la petición.

Ahí suele ir:

- El modelo.
- Los mensajes.
- El texto.
- Los parámetros.
- Las herramientas disponibles.

Ejemplo:

```json
{
  "model": "modelo-llm",
  "input": "Resume este texto..."
}
```

---

## 21. Ejemplo con `curl`

`curl` es una herramienta de línea de comandos para hacer peticiones HTTP.

Este ejemplo es genérico y conceptual:

```bash
curl https://api.proveedor.com/v1/responses \
  -H "Authorization: Bearer TU_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "modelo-llm",
    "input": "Explica qué es una API en una frase."
  }'
```

Qué significa cada parte:

| Parte | Significado |
|---|---|
| `curl` | Herramienta para llamar a una URL |
| URL | Endpoint de la API |
| `Authorization` | Clave de acceso |
| `Content-Type` | Indica que enviamos JSON |
| `model` | Modelo que queremos usar |
| `input` | Instrucción o contenido enviado |

---

## 22. Ejemplo con pseudocódigo

No hace falta saber programar para entender la lógica:

```text
texto_usuario = "Resume este documento"

respuesta = llamar_api_llm(
    modelo = "modelo-llm",
    instrucciones = texto_usuario
)

mostrar(respuesta)
```

El flujo básico es:

1. Preparar la instrucción.
2. Enviarla a la API.
3. Recibir la respuesta.
4. Usarla en la aplicación.

---

## 23. Parámetros frecuentes en APIs de LLM

Los parámetros permiten controlar el comportamiento del modelo.

### 23.1 `max_tokens`

Indica cuántos tokens como máximo puede generar el modelo en la respuesta.

Si pones un límite bajo, la respuesta puede cortarse.

Si pones un límite alto, puede consumir más.

### 23.2 `temperature`

Controla el grado de variabilidad o creatividad.

- Temperatura baja: respuestas más predecibles.
- Temperatura alta: respuestas más variadas.

Para tareas de precisión suele convenir una temperatura baja.

Para ideación creativa puede tener sentido una temperatura más alta.

### 23.3 `top_p`

Controla la variedad de palabras candidatas que el modelo considera al generar.

Es otra forma de regular diversidad.

En muchos casos no hace falta tocar `temperature` y `top_p` a la vez.

### 23.4 Formato de salida

Algunas APIs permiten pedir una salida estructurada.

Por ejemplo:

```json
{
  "nombre": "string",
  "fecha": "string",
  "importe": "number"
}
```

Esto es útil cuando queremos que el resultado pueda ser procesado por otro sistema.

### 23.5 Streaming

El **streaming** permite recibir la respuesta poco a poco, en lugar de esperar a que esté completa.

Es útil en interfaces tipo chat, porque el usuario ve cómo la respuesta aparece progresivamente.

---

## 24. Herramientas y function calling

Algunos sistemas permiten que el modelo no solo genere texto, sino que también indique cuándo conviene usar una herramienta externa.

Esto suele llamarse:

- Tool use.
- Function calling.
- Llamada a funciones.
- Uso de herramientas.

Ejemplo:

El usuario pregunta:

> “¿Cuánto queda de stock del producto X?”

El modelo no debería inventar la respuesta.

Debería pedir consultar una herramienta conectada al inventario.

Flujo simplificado:

1. El usuario pregunta por el stock.
2. El modelo detecta que necesita datos externos.
3. El sistema llama a una función real, por ejemplo `consultar_stock`.
4. La función devuelve el dato.
5. El modelo redacta una respuesta comprensible.

Ejemplo conceptual:

```json
{
  "tool_name": "consultar_stock",
  "arguments": {
    "producto_id": "X123"
  }
}
```

La herramienta real no es el modelo. Es código o un servicio conectado a datos reales.

---

## 25. RAG: conectar el modelo con documentos

RAG significa **Retrieval-Augmented Generation**.

En español:

> Generación aumentada con recuperación de información.

La idea es simple:

1. El usuario hace una pregunta.
2. El sistema busca fragmentos relevantes en documentos o bases de conocimiento.
3. Esos fragmentos se envían al modelo.
4. El modelo responde usando esa información.

RAG se usa cuando queremos que el modelo responda sobre información específica que no necesariamente conoce de antemano.

Ejemplos:

- Manuales internos.
- Políticas de empresa.
- Documentación legal.
- Preguntas frecuentes.
- Catálogos.
- Procedimientos.
- Contratos.
- Material educativo.

RAG ayuda a reducir errores, pero no los elimina por completo. Hay que evaluar la calidad de la búsqueda, los documentos y las respuestas.

---

## 26. Embeddings: buscar por significado

Los **embeddings** son representaciones numéricas del significado de un texto.

Aunque suene técnico, la idea es sencilla:

> Sirven para comparar textos por parecido semántico, no solo por palabras exactas.

Ejemplo:

La frase:

> “No puedo entrar en mi cuenta.”

Es parecida en significado a:

> “Tengo problemas para iniciar sesión.”

Aunque no usen exactamente las mismas palabras.

Los embeddings permiten:

- Búsqueda semántica.
- Recomendaciones.
- Agrupación de documentos.
- Detección de similitud.
- Sistemas RAG.

Normalmente, el usuario final no ve los embeddings. Funcionan por detrás.

---

## 27. Coste y consumo

Las APIs de LLM suelen cobrar según uso.

Factores que pueden influir en el coste:

- Tokens de entrada.
- Tokens de salida.
- Modelo elegido.
- Número de peticiones.
- Uso de herramientas adicionales.
- Procesamiento de imágenes, audio o archivos.
- Almacenamiento o indexación, si aplica.
- Nivel de velocidad o prioridad.

Ejemplo conceptual:

```text
Coste ≈ tokens de entrada + tokens de salida + servicios adicionales
```

Para controlar costes:

- No enviar texto innecesario.
- Resumir contexto largo.
- Elegir el modelo adecuado para la tarea.
- Limitar la longitud de salida.
- Cachear respuestas repetidas.
- Monitorizar consumo.
- Poner límites por usuario o aplicación.
- Separar tareas simples y complejas.

No siempre conviene usar el modelo más potente para todo.

---

## 28. Latencia: cuánto tarda en responder

La **latencia** es el tiempo que pasa desde que haces una petición hasta que recibes respuesta.

Puede depender de:

- Tamaño del prompt.
- Longitud de la respuesta.
- Modelo elegido.
- Carga del servicio.
- Región geográfica.
- Uso de herramientas externas.
- Complejidad de la tarea.
- Procesamiento de archivos o imágenes.

Para mejorar la experiencia:

- Usar streaming.
- Reducir contexto innecesario.
- Dividir tareas largas.
- Precalcular información.
- Mostrar estados de progreso.
- Elegir modelos más rápidos cuando baste.

---

## 29. Rate limits: límites de uso

Las APIs suelen tener límites de uso, llamados **rate limits**.

Pueden limitar:

- Peticiones por minuto.
- Tokens por minuto.
- Peticiones por día.
- Concurrencia.
- Tamaño máximo de entrada.
- Tamaño máximo de salida.

Estos límites existen para proteger el servicio y repartir capacidad.

Si una aplicación crece, debe diseñarse para manejar esos límites:

- Reintentos controlados.
- Colas.
- Priorización.
- Mensajes de error comprensibles.
- Monitorización.
- Planes de capacidad.

---

## 30. Errores habituales al usar APIs de LLM

### 30.1 Pedir demasiado en una sola llamada

Ejemplo problemático:

> “Lee estos 200 documentos, encuentra todos los riesgos legales, redacta un informe ejecutivo, crea una tabla comparativa y sugiere acciones.”

Mejor dividir:

1. Extraer puntos clave por documento.
2. Consolidar hallazgos.
3. Clasificar riesgos.
4. Generar informe.
5. Revisar.

### 30.2 No dar contexto suficiente

El modelo responde mejor cuando sabe:

- Objetivo.
- Público.
- Formato esperado.
- Criterios de calidad.
- Restricciones.
- Ejemplos.
- Datos relevantes.

### 30.3 Confiar ciegamente en la respuesta

Las respuestas deben validarse, especialmente si se usan en procesos importantes.

### 30.4 No controlar el formato de salida

Si una aplicación necesita JSON, hay que pedir JSON y validar que el JSON sea correcto.

### 30.5 Exponer la API key

Nunca se debe poner una clave secreta en una página web pública o repositorio abierto.

### 30.6 No gestionar errores

Una API puede fallar.

Motivos frecuentes:

- Clave incorrecta.
- Límite de uso superado.
- Petición demasiado grande.
- Formato incorrecto.
- Servicio temporalmente no disponible.
- Parámetro no soportado.

Una aplicación seria debe tener gestión de errores.

---

## 31. Seguridad y privacidad

Usar una API de LLM implica enviar datos a un servicio externo o a una infraestructura concreta.

Antes de enviar información, conviene preguntarse:

- ¿Qué datos estoy enviando?
- ¿Son personales, confidenciales o sensibles?
- ¿Tengo permiso para procesarlos?
- ¿Dónde se procesan?
- ¿Quién puede acceder?
- ¿Se almacenan?
- ¿Durante cuánto tiempo?
- ¿Se usan para mejorar modelos?
- ¿Qué contrato o configuración aplica?
- ¿Qué normativa afecta?

Buenas prácticas:

- Minimizar datos enviados.
- Eliminar información innecesaria.
- Anonimizar cuando sea posible.
- Revisar condiciones del proveedor.
- Aplicar controles de acceso.
- Registrar usos relevantes.
- Cifrar datos en tránsito y en reposo.
- Evitar mandar secretos, contraseñas o credenciales.
- Separar entornos de prueba y producción.

---

## 32. Evaluación: cómo saber si funciona bien

No basta con probar tres ejemplos y concluir que el sistema funciona.

Una integración con LLM debe evaluarse.

Criterios posibles:

- Exactitud.
- Utilidad.
- Tono.
- Robustez.
- Seguridad.
- Consistencia.
- Coste.
- Latencia.
- Tasa de errores.
- Cumplimiento de formato.
- Satisfacción del usuario.
- Número de intervenciones humanas necesarias.

Conviene crear un conjunto de pruebas con casos reales o representativos.

Ejemplo:

| Caso | Entrada | Salida esperada | Criterio de aceptación |
|---|---|---|---|
| Resumir ticket | Mensaje largo de cliente | Resumen breve | Incluye problema, producto y urgencia |
| Clasificar email | Email de reclamación | `queja` | Categoría correcta |
| Extraer datos | Factura en texto | JSON con importe y fecha | Campos completos y válidos |

---

## 33. Arquitectura básica de una aplicación con API de LLM

Un flujo simple podría ser:

```text
Usuario
  ↓
Aplicación
  ↓
Servidor propio
  ↓
API del LLM
  ↓
Respuesta del modelo
  ↓
Servidor propio
  ↓
Aplicación
  ↓
Usuario
```

¿Por qué suele haber un servidor propio entre la aplicación y la API?

Porque ahí puedes:

- Proteger la API key.
- Controlar permisos.
- Registrar uso.
- Aplicar filtros.
- Añadir contexto.
- Validar respuestas.
- Gestionar errores.
- Controlar costes.
- Conectar bases de datos.
- Aplicar reglas de negocio.

No es recomendable llamar a una API de LLM directamente desde un frontend público si eso expone claves o datos sensibles.

---

## 34. Ejemplo completo de flujo: resumen automático de reuniones

Supongamos que una empresa quiere resumir reuniones.

### Objetivo

Convertir transcripciones largas en:

- Resumen ejecutivo.
- Decisiones tomadas.
- Tareas pendientes.
- Responsables.
- Fechas.

### Flujo

1. Se graba o transcribe la reunión.
2. El sistema recibe la transcripción.
3. Se limpia el texto.
4. Si es muy largo, se divide en partes.
5. Cada parte se resume.
6. Los resúmenes parciales se consolidan.
7. El LLM genera una salida estructurada.
8. La aplicación valida el formato.
9. El resultado se muestra a una persona.
10. La persona revisa y aprueba.

### Salida deseada

```json
{
  "resumen_ejecutivo": "...",
  "decisiones": [
    "..."
  ],
  "tareas": [
    {
      "tarea": "...",
      "responsable": "...",
      "fecha": "..."
    }
  ],
  "riesgos": [
    "..."
  ]
}
```

Este ejemplo muestra que la API no es el producto completo. Es una pieza dentro de un sistema.

---

## 35. Patrones útiles de diseño

### 35.1 Human-in-the-loop

Significa mantener una persona en el proceso.

Útil cuando:

- Hay riesgo.
- Hay impacto en clientes.
- Hay decisiones sensibles.
- La calidad debe ser alta.
- La respuesta puede tener consecuencias legales o económicas.

### 35.2 Validación automática

Después de recibir una respuesta, el sistema la revisa.

Ejemplos:

- ¿Es JSON válido?
- ¿Tiene todos los campos?
- ¿La fecha tiene formato correcto?
- ¿La categoría pertenece a la lista permitida?
- ¿La respuesta es demasiado larga?
- ¿Contiene información prohibida?

### 35.3 Separar tareas

En vez de pedir todo de golpe, se divide el trabajo.

Ejemplo:

1. Clasificar.
2. Extraer datos.
3. Redactar.
4. Validar.
5. Mostrar.

### 35.4 Usar modelos diferentes para tareas diferentes

No todas las tareas requieren el modelo más avanzado.

Ejemplo:

| Tarea | Tipo de modelo recomendable |
|---|---|
| Clasificación simple | Modelo rápido y barato |
| Redacción compleja | Modelo más capaz |
| Análisis largo | Modelo con más contexto |
| Extracción estructurada | Modelo fiable con formato controlado |
| Búsqueda semántica | Modelo de embeddings |

### 35.5 Registrar y medir

Es importante guardar métricas como:

- Número de peticiones.
- Tokens consumidos.
- Coste aproximado.
- Tiempo de respuesta.
- Errores.
- Calidad percibida.
- Casos revisados por humanos.

Sin medición, no se puede mejorar.

---

## 36. Mitos frecuentes

### Mito 1: “Una API de LLM lo sabe todo”

No. Puede responder con información aprendida o proporcionada, pero no garantiza estar actualizada ni conocer tus datos privados.

### Mito 2: “Si lo conecto por API, ya tengo una solución inteligente”

No. Tienes una capacidad integrada. La solución requiere diseño, datos, seguridad, pruebas y mantenimiento.

### Mito 3: “La API siempre devuelve lo mismo”

No necesariamente. Muchos modelos pueden generar respuestas variables según configuración, contexto y parámetros.

### Mito 4: “Cuanto más contexto mande, mejor”

No siempre. Mandar demasiado contexto puede aumentar coste, latencia y ruido.

### Mito 5: “El modelo puede reemplazar todas las reglas de negocio”

No conviene. Las reglas importantes deben estar definidas y controladas por el sistema.

### Mito 6: “Si responde en JSON, ya es fiable”

No basta. Hay que validar el JSON, comprobar campos y manejar excepciones.

---

## 37. Buenas prácticas para empezar

1. Empezar con un caso de uso concreto.
2. Definir qué problema resuelve.
3. Medir cómo se hace hoy sin IA.
4. Preparar ejemplos reales.
5. Diseñar prompts claros.
6. Limitar la salida esperada.
7. Validar resultados.
8. Medir coste y latencia.
9. Añadir revisión humana si hay riesgo.
10. Iterar antes de automatizar por completo.

---

## 38. Checklist antes de usar una API de LLM en producción

### Objetivo

- [ ] El caso de uso está claramente definido.
- [ ] Se sabe quién usará la solución.
- [ ] Hay criterios de éxito.
- [ ] Hay ejemplos de entradas y salidas esperadas.

### Datos

- [ ] Se sabe qué datos se envían al modelo.
- [ ] Se han eliminado datos innecesarios.
- [ ] Se han revisado datos sensibles.
- [ ] Hay base legal o permiso para el tratamiento de datos.
- [ ] Se entiende la política del proveedor.

### Calidad

- [ ] Hay pruebas con casos reales.
- [ ] Se mide la exactitud.
- [ ] Se revisan errores frecuentes.
- [ ] Hay validación de formato.
- [ ] Hay mecanismos de corrección.

### Seguridad

- [ ] La API key no está expuesta.
- [ ] Hay control de permisos.
- [ ] Hay límites de uso.
- [ ] Hay registro de actividad.
- [ ] Hay gestión de errores.

### Coste

- [ ] Se estima consumo de tokens.
- [ ] Se controla longitud de entrada.
- [ ] Se controla longitud de salida.
- [ ] Se monitorizan costes.
- [ ] Se elige el modelo adecuado.

### Operación

- [ ] Hay mensajes de error comprensibles.
- [ ] Hay fallback si falla la API.
- [ ] Hay revisión humana cuando procede.
- [ ] Hay métricas.
- [ ] Hay mantenimiento previsto.

---

## 39. Glosario mínimo

| Término | Explicación sencilla |
|---|---|
| API | Canal estándar para que un programa hable con otro |
| LLM | Modelo de lenguaje grande capaz de procesar y generar texto |
| Prompt | Instrucción que se envía al modelo |
| Request | Petición enviada a la API |
| Response | Respuesta devuelta por la API |
| Endpoint | Dirección concreta de una función de la API |
| API key | Clave secreta para acceder al servicio |
| Token | Unidad de texto que procesa el modelo |
| Context window | Cantidad máxima de información que el modelo puede considerar |
| JSON | Formato de texto estructurado usado en muchas APIs |
| Latencia | Tiempo que tarda en llegar la respuesta |
| Rate limit | Límite de uso de una API |
| Streaming | Respuesta recibida poco a poco |
| Embedding | Representación numérica del significado de un texto |
| RAG | Sistema que busca información relevante y se la da al modelo |
| Tool calling | Capacidad de pedir el uso de herramientas externas |
| Hallucination | Respuesta incorrecta que parece convincente |
| SDK | Librería que facilita usar una API desde un lenguaje de programación |

---

## 40. Resumen final

Una API de LLM es una forma de conectar una aplicación con un modelo de lenguaje.

Permite que sistemas reales usen capacidades como resumir, redactar, clasificar, extraer información, responder preguntas y transformar texto.

Pero una API no es una solución completa por sí sola. Es una pieza dentro de una arquitectura.

Para usarla bien hay que entender:

- Qué problema se quiere resolver.
- Qué datos se enviarán.
- Qué respuesta se espera.
- Cómo validar resultados.
- Cómo controlar costes.
- Cómo proteger claves y datos.
- Cuándo debe intervenir una persona.
- Qué límites tiene el modelo.

La idea esencial es:

> Una API de LLM no reemplaza automáticamente un proceso. Permite añadir capacidades de lenguaje a un proceso bien diseñado.

---

## 41. Lectura recomendada dentro del repo

Este documento puede complementarse con guías sobre:

- Tokens y costes.
- Prompting básico.
- Hiperparámetros como temperatura, top-p y top-k.
- RAG y búsqueda semántica.
- Seguridad y privacidad en IA generativa.
- Evaluación de respuestas de LLM.
- Diseño de asistentes con revisión humana.
