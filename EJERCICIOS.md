# EJERCICIOS — Neovim + LazyVim con foco en Java

Este archivo guarda SOLO lo VIVO (se lee entero al inicio de cada
sesión, así que se mantiene corto a propósito):
- prácticas [ ] pendientes y [~] en curso
- repasos programados todavía no cumplidos
- la lista CONCEPTOS DOMINADOS

Todo lo CERRADO (prácticas [x] completadas con su corrección, repasos
ya cumplidos) lo mueve Claude a EJERCICIOS-ARCHIVO.md, que viaja por
git y NO se lee al inicio: solo consulta puntual.

Dos orígenes de práctica: (A) DEL MATERIAL, las trae el libro y el
usuario las intenta a mano ANTES de mirar la solución; (B) DEL PROFE,
las crea Claude al cierre de un tema o combinando 2-3 conceptos.
Tres tipos (formato completo en CLAUDE.md, "Tipos de práctica"): KATA
`kNN-nombre/`, PRÁCTICA SOBRE JAVA `jNN-nombre/` (sobre `java-lab/`) y
PREGUNTAS DE CONCEPTO `libNN-nombre.md`.
Toda práctica tiene su ARCHIVO DE ARRANQUE en ejercicios/ (lo crea
Claude: enunciado + prompt de entrega adentro, nada de solución; en
una kata, `inicio.txt` y `objetivo.txt` son el enunciado, no la
solución).

Estados: [ ] pendiente  [~] en curso  [x] completada (fecha)
Corrección escrita en archivo: MÁXIMO 3 líneas. El detalle va al chat.

FORMATOS (referencia para Claude — copiar y llenar):

KATA kNN — [nombre] — [ ] pendiente
Arranque: ejercicios/kNN-nombre/ | Par: N teclas (si tiene) | Si te trabás: Sesión #Y de GUIA.md

PRÁCTICA jNN — [nombre] (java-lab) — [ ] pendiente
Arranque: ejercicios/jNN-nombre/ | Si te trabás: Sesión #Y de GUIA.md

CONCEPTO libNN — [nombre] (cap. N, Sesión #Y) — [ ] pendiente
Arranque: ejercicios/libNN-nombre.md | Si te trabás: Sesión #Y de GUIA.md

REPASO — kNN/jNN/libNN [nombre] (rX) — programado: AAAA-MM-DD — [ ] pendiente
Arranque: ejercicios/repasos/<nombre del original>-rX (desde cero, sin mirar el original)

# ============================================================
# PRÁCTICAS ABIERTAS
# ============================================================

KATA k04 — desplazar la pantalla y saltar con flash — [ ] pendiente
Arranque: ejercicios/k04-scroll-y-flash/ (`./kata k04`) | Par: no tiene | Si te trabás: Sesión #16 de GUIA.md
Ojo: Ctrl-f liberado en kitty el 2026-10-28. Si todavía abre la búsqueda de kitty, falta recargar kitty (Ctrl+Shift+F5 o cerrarla y abrirla).

# ============================================================
# REPASOS PROGRAMADOS (r1 ~3 días, r2 ~2 semanas, r3 ~1 mes)
# ============================================================

REPASO — k01 insertar en su lugar (r1) — programado: 2026-10-31 — [ ] pendiente
Arranque: ejercicios/repasos/k01-insertar-en-su-lugar-r1/ (desde cero, sin mirar el original)

REPASO — k02 abrir líneas (r1) — programado: 2026-11-01 — [ ] pendiente
Arranque: ejercicios/repasos/k02-abrir-lineas-r1/ (desde cero, sin mirar el original)

REPASO — lib01 modo Normal como base, `:wq` vs `:x` y portapapeles (flojos en el examen del cap. 2, 2026-10-28) — programado: 2026-11-02 — [ ] pendiente
Arranque: ejercicios/lib01-normal-x-portapapeles.md (ya creado) | Si te trabás: Sesiones #12-#14 de GUIA.md

REPASO — k03 saltar con flash (r1) — programado: 2026-11-03 (primer día libre después de los otros tres) — [ ] pendiente
Arranque: ejercicios/repasos/k03-saltar-con-flash-r1/ (`./kata k03-r1`; desde cero, sin mirar el original)

# ============================================================
# CONCEPTOS DOMINADOS (entran al graduarse una práctica con r3 bien)
# ============================================================

- (vacío por ahora)
