---
description: Entrego una práctica terminada para que la corrijas
argument-hint: [número o nombre de la práctica, ruta, y qué pasó al probarla]
---

Terminé una práctica. $ARGUMENTS

Si no te dije la ruta o CÓMO la probé, pedímelos antes de corregir:
sin eso la corrección es a ciegas. En una kata alcanza el número
(`/entrega kNN`): la ruta sale de ahí.

Acá no hay compilador. "Probarla" en este proyecto es esto (regla
"Cómo se PRUEBA una práctica acá" de CLAUDE.md):
- KATA (`kNN`): corrí `./kata kNN` y terminó con ✅ (confirmalo
  comparando `trabajo` contra `objetivo`); mis teclas están en el
  `teclas.log` de su carpeta;
- PRÁCTICA SOBRE JAVA (`jNN`): el resultado que pedía la práctica (la
  salida de `mvn -q test`, lo que mostró el debugger...) + mi
  `teclas.log`;
- CONCEPTO (`libNN`): mi respuesta escrita en el archivo.
En todas, mi explicación de qué hice y por qué (acá en el chat, o en
el archivo). En una kata, si no te la di, pedímela antes de corregir.

Después, corregime así:

1. Leé lo que hice y corregilo EN DETALLE **en el chat**: qué está
   bien, qué está mal y POR QUÉ. Si la práctica es del material, dame
   primero pistas, no la solución completa de entrada.
   En una kata o una `jNN`, leé mis teclas con `bat -A <ruta>/teclas.log`
   (con Read no se ven el Esc ni el Enter) y corregí la EFICIENCIA:
   dónde usé más teclas de las necesarias y cuál era el comando
   ("usaste `xxxx`, era `dw`"), contra el par si la kata tiene uno.
   Flechas o Backspace en modo normal, rachas de `jjjj`/`llll` y
   entradas a inserción de más se marcan siempre.
2. Si pegué un error o un mensaje de nvim, del LSP o de Maven —que va a
   estar en inglés—, traducímelo y explicámelo con calma: entender esos
   mensajes es parte del aprendizaje.
3. En `EJERCICIOS.md`, corrección de **3 líneas como máximo** (qué
   estuvo bien, qué estuvo mal, por qué). El detalle largo va al chat.
4. Si quedó completada: movela con su corrección a
   `EJERCICIOS-ARCHIVO.md` y agendá sus repasos (r1 ~3-4 días).
5. Si el error que cometí ya lo había cometido antes, o si un
   checklist de `ToDo/` ya lo cubría, decímelo y actualizá el
   checklist según la regla de esa carpeta.

No edites mi archivo de arranque, ni `trabajo.txt`, ni `teclas.log`, ni
nada de `java-lab/`: ese es mi lugar de trabajo. Las correcciones van
al chat y a `EJERCICIOS.md`.

Cerrá con el bloque `▶ SIGUE`.
