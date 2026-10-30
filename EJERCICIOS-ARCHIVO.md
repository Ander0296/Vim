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

KATA k03 — Saltar con flash (`s` + `r` en una clase Java) — [x] completada (2026-10-28, 1er intento, 35 teclas)
Arranque: ejercicios/k03-saltar-con-flash/ | Sesión #15 de GUIA.md
Bien: los 4 saltos con `s` fueron 1 letra + etiqueta (3 teclas, el mínimo); `r` en los 5 reemplazos, `A;` para el `;`.
Mal: rompió 2 reglas de movimiento (`f(` y `3j`: buen instinto, pero no entrenan `s`), un `i`+Esc de más, y explicó la etiqueta `q` por exclusión cuando era por distancia.
Por qué: en LazyVim `f` es de flash y cruza líneas (en Vim puro no); flash etiqueta primero lo más cercano al cursor y saltea letras que continúan una coincidencia.

KATA k04 — Desplazar la pantalla y saltar con flash (scroll + `s` en una clase de 181 líneas) — [x] completada (2026-10-29, 2º intento, 44 teclas)
Arranque: ejercicios/k04-scroll-y-flash/ | Sesión #16 de GUIA.md
Bien: 2º intento dentro de las reglas: Ctrl-d para bajar, Ctrl-b para subir, `zt` para ver el objetivo, flash sobre la letra mala + `r`, `A;`.
Mal: 1er intento con `G 2k`, `/obtener 3j` y `a`+Backspace (✅ en el diff, ❌ en el método); en los dos salió con Ctrl-s + `<leader>qq` dos veces en vez de `:x`; un `zt` repetido.
Por qué: el ✅ mide el texto y la kata mide el camino; flash solo etiqueta lo visible, por eso primero se desplaza la pantalla.

KATA k05 — Contar con números relativos (número + `j`/`k` en una clase Java) — [x] completada (2026-10-29, 2º intento, 55 teclas, par ~54)
Arranque: ejercicios/k05-contar-con-relativos/ | Sesión #17 de GUIA.md
Bien: 2º intento con los 5 saltos por conteo leído de la columna relativa (`4j` `13j` `4j` `5j` `7j`), `O` con sangría correcta y `:x`.
Mal: 1er intento con flash (prohibido) en 4 de 5; en los dos usó `a;` creyendo que era `A;` (funcionó porque el cursor cayó en el último carácter), y `bbb` en vez de `F<`.
Por qué: `a` agrega a la derecha del cursor y `A` al final de la línea; `F` es `f` hacia atrás y cae en el carácter justo.

KATA k06 — Saltar con f/t y moverse por palabras (`f`/`F`/`t`/`T` con conteo y `w`/`e`/`b`/`ge` en una clase Java) — [x] completada (2026-10-30, 2º intento, 37 teclas, par ~38)
Arranque: ejercicios/k06-f-t-y-palabras/ | Sesión #18 de GUIA.md
Bien: 2º intento dentro de las reglas, con conteos en vez de repeticiones (`3fo`, `2fl`, `3Ft`) y `f2` saltando de línea directo. Mal: 1er intento con `h` (prohibida) y sin `w`/`e`/`b`; explicó `ge` como "ir al final de línea hacia atrás".
Por qué: `ge` va al final de la palabra ANTERIOR (el final de línea es `$`), y la puntuación (`;`, `=`) cuenta como una palabra aparte.
