# GUÍA: Neovim + LazyVim con foco en Java — "LazyVim for Ambitious Developers" (Dusty Phillips); en F2, "Practical Vim" (Drew Neil)

No asume conocimiento previo — la mantiene Claude Code sesión a
sesión. Cada sesión cubre una tanda del material (acá: un rango de
secciones de un capítulo, ~250-400 líneas de texto; 3-5 imágenes si
vino como pantallazos), explicada en español y conectada con práctica
hecha a mano.
Prácticas: ver EJERCICIOS.md.

## INICIO RÁPIDO

- Último punto estudiado: cap. 1, 1.6 "Install Neovim" completa (1.6.1 a 1.6.4, hasta "…you should be good to go.") → la próxima tanda se copia desde lo que sigue (instalar LazyVim: ahí se hace la mudanza a `nvim-ia`, ver Engram vim/config-estudio)
- Última tanda: Sesión #05 (2026-10-27, en la sesión de Claude vim-s02)
- PRÓXIMA SESIÓN: `/rename vim-s03`
  (el nombre de la sesión de Claude sale SIEMPRE de esta línea, no se
  calcula: es un contador distinto al de las tandas, porque una sesión
  de Claude puede cubrir 2-3 tandas. Claude la actualiza al cerrar.)
- Prácticas pendientes: ninguna todavía — esta línea lista SOLO lo
  pendiente (nombres, sin historial); estados completos, fechas y
  repasos viven en EJERCICIOS.md (fuente de verdad)
- Último triage (`/pendientes`): nunca todavía
- Último examen (`/examen`): nunca todavía
- Entorno verificado: 2026-10-27 — NVIM v0.12.5, LazyVim 16.0.0, jdtls + java-debug-adapter + java-test (Mason), openjdk 26, Maven 3.9.16, pandoc 3.10.2, ttyper 1.6.0

## VOCABULARIO (solo si el material está en otro idioma; una fila por término nuevo)

| Original (inglés)                    | Español | En una frase |
| ------------------------------------ | ------- | ------------ |
| modal editing | edición modal | editar con modos: en uno las teclas son comandos, en otro escriben texto |
| line editor | editor de líneas | editor sin pantalla: se le dan órdenes sobre líneas que no ves (ed, ex) |
| stream editor (sed) | editor de flujo | edita el texto que pasa por una tubería de la terminal |
| keystroke | pulsación de tecla | cada tecla que se aprieta |
| RSI (Repetitive Strain Injury) | lesión por esfuerzo repetitivo | lesión de manos y muñecas por repetir el mismo movimiento |
| vi emulation | emulación de vi | capa o plugin que imita las teclas de Vim dentro de otro editor |
| lock-in | encierro, quedar atado | depender de lo que decide la empresa dueña de la herramienta |
| fork (to fork) | bifurcación (bifurcar) | copiar el código de un proyecto y seguirlo por separado |
| killer feature | característica decisiva | la función que por sí sola justifica elegir algo |
| plugin | complemento | pieza que se enchufa al editor para agregarle funciones |
| out-of-the-box | de fábrica, listo al instalar | cómo funciona algo sin configurar nada |
| distribution | distribución | Neovim + plugins elegidos + config que los hace convivir (ej. LazyVim) |
| keybinding | atajo, asignación de tecla | qué hace una tecla o combinación |
| muscle memory | memoria muscular | lo que los dedos hacen solos, sin pensar |
| terminal emulator | emulador de terminal | la ventana (kitty) que imita a las viejas terminales y dibuja el texto |
| GPU accelerated | acelerada por GPU | dibuja con el chip gráfico en vez de la CPU: más fluido |
| GUI (Graphical User Interface) | interfaz gráfica | programa con ventana propia, no dentro de una terminal |
| featureful | con muchas funciones | que trae muchas características |
| choppy | entrecortado | que se traba o va a los saltos |
| glyph | glifo | el dibujo concreto de un carácter o de un ícono dentro de una fuente |
| Nerd Fonts | (nombre propio) | proyecto que les agrega miles de íconos a las fuentes de programación |
| patched font | fuente parchada | fuente normal a la que se le "cosieron" glifos extra (íconos) |
| monospace font | fuente monoespaciada | todos los caracteres miden lo mismo de ancho, como casilleros de una grilla |
| look and feel | aspecto y sensación | cómo se ve un programa y cómo se siente usarlo |
| stable release | versión estable | versión publicada y probada: la recomendada para el día a día |
| nightly build | compilación nocturna | versión que se arma sola cada noche con lo último del código: nueva, pero sin garantía |
| master branch | rama principal | la línea principal del código en GitHub, donde entran los cambios nuevos |
| pre-release | versión previa | versión anterior al lanzamiento oficial (acá, la nightly) |
| live on the edge | vivir al límite | usar lo más nuevo aunque pueda fallar |
| WSL (Windows Subsystem for Linux) | subsistema de Windows para Linux | un Linux que corre dentro de Windows |
| tarball | archivo tar | archivo comprimido `.tar.gz` con un programa adentro |
| system path (PATH) | ruta del sistema | lista de carpetas donde la shell busca los programas que tipeás |
| C compiler | compilador de C | programa que convierte código C en un ejecutable (ej. `gcc`) |
| parser | analizador sintáctico | programa que lee código y entiende su estructura |
| treesitter | (nombre propio) | parser que arma el árbol de sintaxis del código: colorea y navega por estructura |

============================================================
(ACÁ VAN LAS SESIONES — Claude agrega la SESIÓN #01 en la primera
clase y sigue numerando hacia abajo, una sección por sesión, usando
el formato CORTO de referencia del final del archivo. Cuando este
archivo supere ~500 líneas, Claude mueve las sesiones viejas a
GUIA-ARCHIVO.md — ver la regla en CLAUDE.md.)
============================================================

SESIÓN #01 — 2026-10-27 — Por qué Vim (cap. 1, intro + 1.1 hasta "Open Ecosystem")
- Edición modal: el mismo teclado hace dos trabajos según el modo (normal = control remoto de comandos; inserción = máquina de escribir).
- Árbol: ed (1971, editor de líneas) → ex → vi ("Visual") → Vim ("Vi IMproved") → Neovim; sed es el primo que edita en tuberías.
- ex sigue vivo como submodo de Vim: todo lo que va después de `:` (`:w`, `:q`, `:s`) es un comando ex; sed comparte la sintaxis `s/viejo/nuevo/`.
- Las 4 razones del autor: salud (sin acordes con la misma mano → menos RSI), rendimiento (arranque en ms), velocidad (subjetiva) y ecosistema abierto.
- En dvorak la ventaja de `hjkl` no aplica, pero la de "sin acordes" sí: es la que importa.
- Ejercicios de la tanda: ninguno (el cap. 1 es contexto). PRÁCTICAS CREADAS: ninguna.
- Nota del profe: ninguna. La línea "⚡ Neovim loaded … ms" del dashboard sigue en LazyVim 16 (verificado en snacks.nvim) y `:Lazy profile` existe.
- Dudas: creyó que "ex" venía de *extensively* → corregido: viene de *extended* (ed extendido); `:` abre el submodo ex. Qué es ed → explicado (editor de líneas de 1971 para teletipos; de ahí salen `w`, `q`, `s`).
- PRÓXIMO PASO: seguir el cap. 1 desde lo que viene después de "Open Ecosystem".

SESIÓN #02 — 2026-10-27 — Por qué Neovim y qué es LazyVim (cap. 1, 1.2 y 1.3)
- Neovim es un fork de Vim (2014) para modernizar el código; su ventaja decisiva es Lua (plugins y config) además de VimScript.
- Casi todo plugin de Vim corre en Neovim, pero no al revés: los mejores plugins en Lua son solo de Neovim, y LazyVim solo anda en Neovim.
- VimScript es, en el fondo, comandos ex en un archivo + lógica; Lua se prueba con `:lua print("hola")` (`:echo "hola"` es lo mismo en VimScript).
- Neovim pelado es "bland" (soso): mantiene la compatibilidad con vi; configurarlo a mano le llevó al autor semanas.
- LazyVim es una DISTRIBUCIÓN, no otra versión del editor: Neovim + plugins elegidos + config que evita choques de atajos. Capas: Vim → Neovim → LazyVim → tu config.
- Ejercicios de la tanda: ninguno (contexto). PRÁCTICAS CREADAS: ninguna. Nota del profe: ninguna.
- Dudas: LazyVim vs Neovim → bien, con precisión (LazyVim no toca el código del editor; VimScript sigue andando). ¿Empezar LazyVim de cero? → no: la config propia es una capa fina, sin remapeos del núcleo; avisar `scrolloff=999` en el cap. 3 y `<leader>e`→yazi en el cap. 4.
- PRÓXIMO PASO: terminar el cap. 1 (lo que sigue a la 1.3).

SESIÓN #03 — 2026-10-27 — Elegir terminal (cap. 1, 1.4 completa)
- Neovim corre en muchos lados (hasta dentro de VS Code: LazyVim tiene un extra `vscode`) y hay GUIs, pero el autor recomienda la terminal.
- Capas: emulador de terminal (kitty, dibuja) → shell (fish, interpreta) → nvim (programa). Una tecla pasa por la terminal ANTES de llegar a nvim, y la terminal puede quedársela (ej. `<C-_>` en kitty).
- Conviene una terminal acelerada por GPU. Recomendación del autor: Kitty; Alacritty (la más rápida, config incómoda); WezTerm (falta documentación); Windows Terminal y Warp (con problemas).
- El usuario ya usa kitty 0.48.2: no hay nada que cambiar. Se comprueba con `:echo $TERM` → `xterm-kitty`.
- Ejercicios de la tanda: ninguno. PRÁCTICAS CREADAS: ninguna. Nota del profe: ninguna.
- Dudas: ninguna.
- PRÓXIMO PASO: instalación (resto del cap. 1) + mudanza de la config de la IA a `nvim-ia`, en sesión limpia.

SESIÓN #04 — 2026-10-27 — La fuente de la terminal (cap. 1, 1.5 completa)
- Los íconos y marcos de LazyVim no los dibuja nvim: nvim manda un carácter y la TERMINAL lo dibuja con su fuente. Sin la fuente adecuada se ven cuadraditos.
- Nerd Font = fuente de programación monoespaciada "patched" (parchada) con miles de glifos extra: íconos de tipo de archivo, git, flechas, marcos.
- Kitty usa una fuente de respaldo: si a la fuente principal le falta un glifo, lo toma de otra. Por eso al libro le alcanza con la "Symbols Only" (solo símbolos).
- Nota del profe: el libro manda instalar NerdFontsSymbolsOnly para kitty; hoy kitty ya la trae adentro (verificado: `SymbolsNerdFontMono-Regular.ttf` en `/usr/lib/kitty/fonts/`, kitty 0.48.2). No hay que instalar nada.
- El usuario ya tiene JetBrainsMono Nerd Font instalada y puesta en `font_family` de `~/.config/kitty/kitty.conf`: nada que cambiar. Prueba: `:echo ""` muestra un ícono.
- Ejercicios de la tanda: ninguno (contexto). PRÁCTICAS CREADAS: ninguna.
- Dudas: ninguna.
- PRÓXIMO PASO: lo que sigue a la 1.5 (instalación) + mudanza de la config de la IA a `nvim-ia`.

SESIÓN #05 — 2026-10-27 — Instalar Neovim (cap. 1, 1.6 completa: 1.6.1 a 1.6.4)
- Estable (stable release: publicada y probada) vs nightly (se compila cada noche desde la rama master: lo más nuevo, sin garantía). Para aprender, la estable; a nightly solo si un plugin lo pide.
- Windows: WSL (o instalador MSI, Winget, Chocolatey, Scoop). MacOS: Homebrew (`brew install neovim`; `--HEAD` = nightly). Linux: el gestor de la distro (`sudo pacman -S neovim`); hay distros con versiones muy viejas.
- Treesitter = parser que arma el árbol de sintaxis del código (coloreado preciso, navegar por estructura). Cada parser es código C que se compila en la máquina → hace falta un compilador de C.
- Nota del profe 1: el libro da 0.11.0 como última estable; LazyVim 16 exige Neovim >= 0.11.2 (`health.lua`). El usuario tiene 0.12.5 por pacman.
- Nota del profe 2: el libro pide solo un compilador de C; LazyVim 16 usa la rama `main` de nvim-treesitter y pide CLI `tree-sitter`, compilador de C, `tar` y `curl` (si falta la CLI, intenta instalarla con Mason). En la máquina, todo OK. Se verifica con `:checkhealth lazyvim`; `:version` muestra la versión desde adentro.
- Ejercicios de la tanda: ninguno (contexto). PRÁCTICAS CREADAS: ninguna. Mudanza a `nvim-ia`: todavía no, va cuando el libro instale LazyVim.
- Dudas: qué es un parser → explicado (análisis sintáctico escolar aplicado al código; `javac` también parsea). Creyó que treesitter compila sus clases → corregido: se compila el PARSER (C); el código solo se lee. Para verlo: `:InspectTree`.
- PRÓXIMO PASO: lo que sigue a la 1.6 (instalar LazyVim + mudanza a `nvim-ia`), en sesión limpia.

# ============================================================
# FORMATO DE CADA SESIÓN (referencia para Claude — copiar y llenar)
# Formato CORTO obligatorio: 5-8 bullets, SIN bloques de código ni
# contenido repetido del chat (eso ya vive en el chat, el material y
# los archivos de práctica). Sin narrar las dudas (tema + veredicto
# en una línea). Máximo ~15 líneas por sesión.
# ============================================================

SESIÓN #NN — [fecha] — [tema] (cap. N, secciones N.M-N.P, % avance)
- [idea clave 1, una línea]
- [idea clave 2...]
- Ejercicios de la tanda: [nombre + pendiente/completado, o "ninguno"]
- Nota del profe: [solo si la hubo, una línea — ej. libro vs LazyVim 16]
- Config tocada: [solo si la hubo: archivo de ~/.config/nvim y qué se cambió]
- Dudas: [tema + bien/corregido en una línea, o "ninguna"]
- PRÁCTICAS CREADAS: [kNN/jNN/libNN o "ninguna"]
- PRÓXIMO PASO: [una línea]
