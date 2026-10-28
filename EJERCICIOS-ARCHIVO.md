# EJERCICIOS — ARCHIVO (lo cerrado)

Prácticas completadas con su corrección y repasos ya cumplidos. NO se
lee al inicio de sesión: solo consulta puntual (comparar contra un
repaso, o un RE-ESTUDIO). Lo vivo está en EJERCICIOS.md.

# ============================================================
# PRÁCTICAS COMPLETADAS
# ============================================================

KATA k01 — Insertar en su lugar (`private` y `;` en una clase Java) — [x] completada (2026-10-28)
Arranque: ejercicios/k01-insertar-en-su-lugar/ | Sesión #12 de GUIA.md
Bien: resultado idéntico al objetivo; los `;` con `A;` + `j.` fueron la solución justa.
Mal: `private` con `llll` + `i` en vez de `I`, y cada `.` necesitó reubicarse con 6-8 `h`.
Por qué: `.` repite también DÓNDE inserta; con `I` el `.` cae solo al principio del texto de la línea.

KATA k02 — Abrir líneas (`o`/`O` en una clase Java) — [x] completada (2026-10-28, 2º intento)
Arranque: ejercicios/k02-abrir-lineas/ | Sesión #13 de GUIA.md
Bien: 2º intento casi óptimo — una apertura por línea, conteos justos (`2j` `5j` `2j`), `O` desde el método, `:wq`.
Mal: 1er intento abrió los comentarios con `o` desde la línea vacía → quedaron sin sangría (❌).
Por qué: la línea nueva copia la sangría de la línea de origen; explicación oral salteada a pedido del usuario.
