---
description: Explica la tanda de material que dejé en material/ (repetible, una vez por tanda)
argument-hint: [opcional: qué secciones, ej "cap. 2, secciones 2.1 a 2.4" o "2 pantallazos del cap. 9"]
---

Tanda nueva. $ARGUMENTS

El material está en `material/` como `capNN.md`: un capítulo entero del
libro, bajado con curl + pandoc (si vino como imágenes, en la raíz de
la carpeta). No entres a `material/visto/`: eso ya está explicado.

Una tanda acá es un RANGO de secciones numeradas de UN capítulo
(~250-400 líneas), no el capítulo entero. Si no te dije cuáles, seguí
desde el punto exacto del INICIO RÁPIDO y elegí vos el rango. NO leas
el capítulo completo: sacá el índice con Grep (`^#{2,3} ` sobre el
`capNN.md`) y leé con Read solo las líneas de esas secciones.

El libro está en INGLÉS y no lo domino: cada término o frase que cites
va con su traducción al lado, sin excepciones, y los términos nuevos
van a la tabla VOCABULARIO de `GUIA.md`. Y si un atajo o un
comportamiento del libro puede no coincidir con el LazyVim 16
instalado, verificalo antes de enseñarlo y marcalo como NOTA DEL PROFE
(regla "EL LIBRO PUEDE ESTAR DESFASADO" de CLAUDE.md).

Aplicá el **flujo por tanda** completo de CLAUDE.md (no lo leas con
Read: ya lo tenés cargado), respetando el presupuesto de contexto:

1. Leé el material de la tanda (solo su rango de secciones).
2. Explicámelo PIEZA POR PIEZA, anunciando siempre cuál ("SECCIÓN 2.3:",
   "PANTALLAZO 2:") para que lo pueda seguir con la vista. En español,
   con palabras propias, COMPRIMIENDO — no transcribiendo. Si algo no
   tiene base previa, frená y explicá la base primero.
3. Mostrame el contenido clave en el chat, comentado solo donde enseña
   algo nuevo. Si un comando se entiende mejor probándolo, decime qué
   tipear en mi nvim para verlo en el momento.
4. Si la tanda trae ejercicios del material, avisame cuáles son y
   creales su archivo de arranque. Si el tema pide práctica, creala
   con el tipo que corresponda (kata `kNN`, `jNN` sobre java-lab o
   preguntas `libNN`, con el formato de CLAUDE.md).
5. Verificá que entendí con 1-2 preguntas cortas antes de cerrar.

Cuando termines de explicar, en el mismo turno:
- si se explicó la ÚLTIMA sección del capítulo, mové `capNN.md` a
  `material/visto/`; si no, dejalo donde está y anotá el punto exacto
  ("cap. 2, hasta la 2.4 incluida") en el INICIO RÁPIDO;
- actualizá `GUIA.md` con la sesión en FORMATO CORTO (5-8 bullets,
  máx ~15 líneas) y el INICIO RÁPIDO, incluida la línea
  **PRÓXIMA SESIÓN**;
- agregá 1-2 líneas nuevas de COMANDOS a `MECANOGRAFIA.md` y volcá
  cada línea NUEVA a su propio archivo de ttyper, un token por línea
  (append-only);
- agregá las tarjetas 80/20 de esta tanda a `ANKI.txt`
  (autocontenidas, separadas por tab);
- revisá si hace falta crear o actualizar un checklist de `ToDo/`;
- guardá en Engram el punto exacto del material donde quedamos.

Cerrá con el bloque `▶ SIGUE` y **decidí vos si seguimos acá o
cortamos**, aplicando la regla "Cuándo cortar la sesión lo decide
Claude" de CLAUDE.md. Nunca me preguntes "¿seguimos?" a secas: decime
qué conviene y POR QUÉ en una línea (otra tanda acá, `/cambio` a sesión
limpia, o cerrar el día con `/cierre`). Yo puedo pedirte lo contrario,
pero la recomendación la ponés vos.

Si además se cumple alguno de los disparadores de `/examen` (regla
"Cuándo proponer /examen"), sumalo ahí en UNA línea.
