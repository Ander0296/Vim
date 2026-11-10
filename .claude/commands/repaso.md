---
description: Hacer un repaso vencido — desde cero, sin ver mi versión original
argument-hint: [qué repaso, ej "lib01"; o vacío para lo más antiguo vencido]
---

Voy a hacer un repaso. $ARGUMENTS

Si no te dije cuál, tomá lo más antiguo vencido de `EJERCICIOS.md`
(CONCEPTOS EN CICLO o REPASOS PROGRAMADOS). Máximo 1 repaso por día.

**NO me muestres ni me resumas mi versión anterior.** El repaso va
desde cero: verla arruina la prueba.

1. Armá el repaso según el tipo (formato completo en CLAUDE.md):
   - CONCEPTOS DE KATAS vencidos → una kata MIXTA `mNN` en
     `ejercicios/mNN-nombre/`: texto Java NUEVO que junte el concepto
     vencido con otros vencidos o por vencer (3-4 en total), sin decir
     cuál va en cada cambio; 3 a 6 cambios; par verificado (reproducí
     la ruta en un `nvim --clean --headless` antes de dármela); única
     regla: sin flechas ni mouse. Si ya hay una `mNN` armada, sin
     hacer, que cubre esos conceptos, usá esa.
   - `jNN` o `libNN` → archivo de arranque nuevo en `ejercicios/repasos/`
     con el nombre del original + `-rX`: enunciado completo en español,
     "Si te trabás: revisá la Sesión #Y de GUIA.md", el checklist de
     `ToDo/` si hay, y al final el prompt de entrega ya relleno. Nada de
     la solución ni esqueletos de la respuesta.
2. Dame el enunciado en el chat (2-3 líneas) y el comando, y esperá a
   que lo entregue.

Cuando lo entregue (con `/entrega`), comparalo contra lo anterior
(`EJERCICIOS-ARCHIVO.md`): qué mejoré, qué error repetí y POR QUÉ. En
una mixta el veredicto es POR CONCEPTO: bien si lo usé por mi cuenta
donde era la mejor herramienta; mal si elegí otra más larga o no lo
usé. Después actualizá `EJERCICIOS.md`: bien → siguiente etapa (r1 → r2
~2 semanas → r3 ~1 mes); mal → ~3 días; mal DOS veces seguidas =
RE-ESTUDIO. r3 bien → pasa a CONCEPTOS DOMINADOS.

Si algo se graduó, proponeme `/examen`: la graduación dice que la
práctica salió, el examen dice si el concepto se sostiene FUERA de esa
práctica.

Cerrá con el bloque `▶ SIGUE`.
