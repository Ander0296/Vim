---
description: Entrego una práctica terminada para que la corrijas
argument-hint: [número o nombre de la práctica, ruta, y qué pasó al probarla]
---

Terminé una práctica. $ARGUMENTS

Si no te dije la ruta o CÓMO la probé, pedímelos antes de corregir:
sin eso la corrección es a ciegas. En una kata alcanza el número
(`/entrega k08`, `/entrega m01`): la ruta sale de ahí.

Acá no hay compilador. "Probarla" en este proyecto es esto (regla
"Cómo se PRUEBA una práctica acá" de CLAUDE.md):
- KATA (`kNN` o `mNN`): corrí `./kata kNN`, terminó con ✅ y me dijo
  cuántas teclas usé contra el par (confirmalo comparando `trabajo`
  contra `objetivo`); mis teclas están en el `teclas.log` de su carpeta;
- PRÁCTICA SOBRE JAVA (`jNN`): el resultado que pedía la práctica (la
  salida de `mvn -q test`, lo que mostró el debugger...) + mi
  `teclas.log` + mi explicación de qué hice y por qué;
- CONCEPTO (`libNN`): mi respuesta escrita en el archivo.

Después, corregime así:

1. En una KATA, primero leé mis teclas con `bat -A <ruta>/teclas.log`
   (con Read no se ven el Esc ni el Enter) y haceme 2-3 PREGUNTAS sobre
   decisiones concretas que veas ahí ("¿por qué `fa` acá y no `e`?").
   No me pidas que explique cada comando. Esperá mis respuestas antes
   de seguir.
2. Corregime EN DETALLE **en el chat**: qué está bien, qué está mal y
   POR QUÉ. Si la práctica es del material, dame primero pistas, no la
   solución completa de entrada. En una kata o una `jNN`, corregí la
   EFICIENCIA: dónde usé más teclas de las necesarias y cuál era el
   comando ("usaste `xxxx`, era `dw`"). Flechas o Backspace en modo
   normal, rachas de `jjjj`/`llll` y entradas a inserción de más se
   marcan siempre. En una kata, cerrá mostrándome la RUTA DEL PAR tecla
   por tecla, con qué hace cada una; si quiero, la vuelvo a correr para
   bajar mi marca.
3. Si pegué un error o un mensaje de nvim, del LSP o de Maven —que va a
   estar en inglés—, traducímelo y explicámelo con calma: entender esos
   mensajes es parte del aprendizaje.
4. En `EJERCICIOS.md`, corrección de **3 líneas como máximo** (qué
   estuvo bien, qué estuvo mal, por qué). El detalle largo va al chat.
5. Si quedó completada: movela con su corrección a
   `EJERCICIOS-ARCHIVO.md` y agendá. En una kata, sus conceptos entran
   (o avanzan) en CONCEPTOS EN CICLO, con el veredicto por concepto; en
   una `jNN`/`libNN`, su r1 (~3-4 días) en REPASOS PROGRAMADOS.
6. Si el error que cometí ya lo había cometido antes, o si un
   checklist de `ToDo/` ya lo cubría, decímelo y actualizá el
   checklist según la regla de esa carpeta.

No edites mi archivo de arranque, ni `trabajo.txt`, ni `teclas.log`, ni
nada de `java-lab/`: ese es mi lugar de trabajo. Las correcciones van
al chat y a `EJERCICIOS.md`.

Cerrá con el bloque `▶ SIGUE`.
