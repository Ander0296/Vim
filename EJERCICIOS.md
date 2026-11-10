# EJERCICIOS — Neovim + LazyVim con foco en Java

Este archivo guarda SOLO lo VIVO (se lee entero al inicio de cada
sesión, así que se mantiene corto a propósito):
- prácticas [ ] pendientes y [~] en curso
- repasos programados todavía no cumplidos (`jNN` y `libNN`)
- la tabla CONCEPTOS EN CICLO (el repaso de las katas va por concepto)
- la lista CONCEPTOS DOMINADOS

Todo lo CERRADO (prácticas [x] completadas con su corrección, repasos
ya cumplidos) lo mueve Claude a EJERCICIOS-ARCHIVO.md, que viaja por
git y NO se lee al inicio: solo consulta puntual.

Dos orígenes de práctica: (A) DEL MATERIAL, las trae el libro y el
usuario las intenta a mano ANTES de mirar la solución; (B) DEL PROFE,
las crea Claude al cierre de un tema o combinando 2-3 conceptos.
Cuatro tipos (formato completo en CLAUDE.md, "Tipos de práctica"): KATA
DE ESTRENO `kNN-nombre/`, KATA MIXTA `mNN-nombre/` (el repaso de las
katas), PRÁCTICA SOBRE JAVA `jNN-nombre/` (sobre `java-lab/`) y
PREGUNTAS DE CONCEPTO `libNN-nombre.md`.
Toda práctica tiene su ARCHIVO DE ARRANQUE en ejercicios/ (lo crea
Claude: enunciado + prompt de entrega adentro, nada de solución; en
una kata, `inicio.txt` y `objetivo.txt` son el enunciado, no la
solución). Katas: UNA sola regla (sin flechas ni mouse), par siempre,
3-6 cambios; formato rediseñado el 2026-11-09 (las k01-k07 viejas se
borraron; quedan en git y en EJERCICIOS-ARCHIVO.md).

Estados: [ ] pendiente  [~] en curso  [x] completada (fecha)
Corrección escrita en archivo: MÁXIMO 3 líneas. El detalle va al chat.

FORMATOS (referencia para Claude — copiar y llenar):

KATA kNN — [nombre] (lo nuevo: [concepto]) — [ ] pendiente
Arranque: ejercicios/kNN-nombre/ (`./kata kNN`) | Par: N teclas | Si te trabás: Sesión #Y de GUIA.md

KATA MIXTA mNN — [nombre] (cubre: [3-4 conceptos]) — [ ] pendiente
Arranque: ejercicios/mNN-nombre/ (`./kata mNN`) | Par: N teclas | Si te trabás: Sesiones #Y de GUIA.md

PRÁCTICA jNN — [nombre] (java-lab) — [ ] pendiente
Arranque: ejercicios/jNN-nombre/ | Si te trabás: Sesión #Y de GUIA.md

CONCEPTO libNN — [nombre] (cap. N, Sesión #Y) — [ ] pendiente
Arranque: ejercicios/libNN-nombre.md | Si te trabás: Sesión #Y de GUIA.md

REPASO — jNN/libNN [nombre] (rX) — programado: AAAA-MM-DD — [ ] pendiente
Arranque: ejercicios/repasos/<nombre del original>-rX (desde cero, sin mirar el original)

# ============================================================
# PRÁCTICAS ABIERTAS
# ============================================================

Las tres mixtas cuentan como el r1 de los conceptos de las katas viejas
k01-k07 (todos vencidos entre el 2026-10-31 y el 2026-11-07). Una por
día, en este orden.

KATA MIXTA m01 — Entrar a escribir (cubre: `I`/`A`, `o`/`O`, `G`, conteos) — [ ] pendiente
Arranque: ejercicios/m01-entrar-a-escribir/ (`./kata m01`) | Par: 56 teclas | Si te trabás: Sesiones #12, #13, #17 y #19 de GUIA.md

KATA MIXTA m02 — Moverse dentro de la línea (cubre: `f`/`t`, `e`, `^`/`$`, `r`, conteos) — [ ] pendiente
Arranque: ejercicios/m02-moverse-en-la-linea/ (`./kata m02`) | Par: 31 teclas | Si te trabás: Sesiones #15, #17, #18 y #19 de GUIA.md

KATA MIXTA m03 — Moverse por el archivo (cubre: `NG`/`G`, conteos relativos, flash `s`, `f`/`F`; scroll y `zz` de apoyo) — [ ] pendiente
Arranque: ejercicios/m03-moverse-por-el-archivo/ (`./kata m03`) | Par: ~31 teclas | Si te trabás: Sesiones #15, #16, #17 y #19 de GUIA.md

# ============================================================
# REPASOS PROGRAMADOS — jNN y libNN (r1 ~3 días, r2 ~2 semanas, r3 ~1 mes)
# ============================================================

REPASO — lib01 modo Normal como base, `:wq` vs `:x` y portapapeles (flojos en el examen del cap. 2, 2026-10-28) — programado: 2026-11-02 — [ ] pendiente
Arranque: ejercicios/lib01-normal-x-portapapeles.md (ya creado) | Si te trabás: Sesiones #12-#14 de GUIA.md

# ============================================================
# CONCEPTOS EN CICLO — katas (el repaso va por concepto, en mixtas)
# ============================================================

Etapa = el próximo repaso que le toca. Bien → siguiente etapa; mal →
~3 días; mal dos veces seguidas → RE-ESTUDIO; r3 bien → DOMINADOS.

| Concepto | Visto en | Etapa | Próxima |
| --- | --- | --- | --- |
| `I` / `A` | Sesión #12 | r1 | vencido → m01 |
| `o` / `O` | Sesión #13 | r1 | vencido → m01 |
| `G` / `NG` / `gg` | Sesión #19 | r1 | vencido → m01 y m03 |
| conteos + números relativos | Sesión #17 | r1 | vencido → m01, m02 y m03 |
| `r` | Sesión #15 | r1 | vencido → m02 |
| `f` / `t` / `F` / `T` (+ `;` `,`) | Sesión #18 | r1 | vencido → m02 y m03 |
| `w` / `b` / `e` / `ge` | Sesión #18 | r1 | vencido → m02 |
| `0` / `^` / `$` | Sesión #19 | r1 | vencido → m02 |
| flash `s` | Sesión #15 | r1 | vencido → m03 |
| scroll (`Ctrl-d`/`u`/`f`/`b`/`e`/`y`) y `zz`/`zt`/`zb` | Sesión #16 | r1 | vencido → m03 (de apoyo) |
| `W` / `B` / `E` / `gE` | Sesión #19 | r1 | vencido → no entró en m01-m03: va en la próxima mixta |

# ============================================================
# CONCEPTOS DOMINADOS (entran al graduarse con r3 bien)
# ============================================================

- (vacío por ahora)
