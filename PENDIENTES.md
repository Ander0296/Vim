# PENDIENTES — la deuda del proyecto

**Este archivo NO se lee al inicio de sesión.** Lo lee `/pendientes`, una vez
por semana. Acá vive lo que quedó colgando y NO es una práctica (las
prácticas viven en `EJERCICIOS.md`).

## La regla que hace que esto sirva

**Una referencia suelta no es accionable.** "Falta la página 213" no se puede
triagear nunca: nadie sabe si eso era una figura decorativa, medio capítulo o
un chiste. Toda entrada de este archivo dice **QUÉ** falta, no solo dónde.

Cuando un pedazo del material no llega en una tanda (no se pudo copiar, la
imagen salió ilegible, el audio se cortó), Claude lo clasifica **en el
momento**, en una de estas tres, y lo dice en una línea:

| Clase | Qué es | Qué se hace |
| --- | --- | --- |
| **Hueco de formato** | el material no se pudo pasar (figura, tabla dibujada, notación que el texto plano no transmite) y el concepto NO quedó cubierto por lo de alrededor | entra acá; Claude pide ESE pedazo puntual en la próxima tanda |
| **Diferido a propósito** | contenido salteado con criterio (una solución que sería spoiler, algo que necesita una base que todavía no está) | entra acá, con la condición de rescate |
| **Cubierto igual** | repetía, o el concepto ya quedó explicado con lo de alrededor | **NO entra**: se descarta y se dice en una línea |

La tercera es la más importante. Muchos "salteos" son problemas de formato,
no contenido faltante — meterlos todos en una lista los convierte en una
deuda falsa que se relee para siempre y no se salda nunca.

# ============================================================
# HUECOS DE FORMATO — falta el contenido, hay que recuperarlo
# ============================================================

(vacío)

# ============================================================
# DIFERIDO A PROPÓSITO
# ============================================================

- **`java-lab/` — el proyecto Maven de práctica** (diferido en el setup,
  2026-10-27). Qué es: un proyecto Java chico (`pom.xml`, `src/main/java`
  y `src/test/java` con tests) cuyo código escribe Claude como MATERIAL —
  el usuario no lo programa: trabaja SOBRE él en las prácticas `jNN`
  (ir a la definición, referencias, rename, code actions, debugger,
  tests). Por qué se difiere: antes del cap. 10 (Programming Language
  Support) no hay con qué usarlo, y crearlo antes es ruido.
  CONDICIÓN DE RESCATE: la tanda que arranque el cap. 10 → Claude crea
  `java-lab/` (bajo el candado desde el primer archivo), el usuario
  verifica que `mvn -q test` pasa y que jdtls lo levanta en nvim, y se
  fijan el formato fino de las `jNN` y cómo vuelve java-lab a su estado
  limpio entre prácticas.

- **`ToDo/practical-vim-vs-lazyvim.md` — choques entre Vim puro y
  LazyVim** (diferido en el setup, 2026-10-27). Qué es: el checklist de
  cada comando de Practical Vim que en LazyVim hace otra cosa o está
  tomado, con la alternativa a usar. Ya conocidos (verificados en el
  código de LazyVim 16 en el setup): `s`/`S` → flash.nvim; `gs` →
  prefijo de mini.surround (`gsa`, `gsd`, `gsr`...); `f`/`F`/`t`/`T`/`;`/`,`
  → modo carácter de flash, que CRUZA LÍNEAS (en Vim puro `f` no sale de
  la línea; verificado en `flash.nvim/lua/flash/config.lua` el 2026-10-28:
  `modes.char.enabled = true`, `multi_line = true`). Cada entrada se
  verifica en la config instalada (`:verbose map`, código de LazyVim)
  antes de escribirse. Por qué se difiere: en F1 el material ES LazyVim;
  el choque aparece recién con el libro de Vim puro.
  CONDICIÓN DE RESCATE: la primera tanda de F2 → Claude lo crea antes de
  explicar nada y lo suma al índice de `ToDo/README.md`.

# ============================================================
# DADAS DE BAJA (decisión tomada, no vuelven)
# ============================================================

(vacío)
