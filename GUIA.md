# GUÍA: Neovim + LazyVim con foco en Java — "LazyVim for Ambitious Developers" (Dusty Phillips); en F2, "Practical Vim" (Drew Neil)

No asume conocimiento previo — la mantiene Claude Code sesión a
sesión. Cada sesión cubre una tanda del material (acá: un rango de
secciones de un capítulo, ~250-400 líneas de texto; 3-5 imágenes si
vino como pantallazos), explicada en español y conectada con práctica
hecha a mano.
Prácticas: ver EJERCICIOS.md.

## INICIO RÁPIDO

- Último punto estudiado: cap. 2 COMPLETO (2.2-2.4, termina en "…ways to move the cursor around inside a document.") → la próxima tanda es el cap. 3 desde el principio: https://lazyvim-ambitious-devs.phillips.codes/course/chapter-3/
- Última tanda: Sesión #14 (2026-10-28, en la sesión de Claude vim-s09)
- PRÓXIMA SESIÓN: `/rename vim-s10` (sale SIEMPRE de esta línea, no se calcula: es otro contador que el de las tandas; Claude la actualiza al cerrar)
- QUEDÓ PENDIENTE de vim-s09 (el usuario tuvo que salir): el lab en vivo de 2 min y las 2 preguntas de cierre de la Sesión #14 (están en sus bullets) → hacerlos al arrancar, antes que nada; después, `/examen` del cap. 2 (propuesto).
- Otro PC: todavía tiene la config de la IA como `nvim` → antes de la primera kata o tanda ahí, ToDo/mudanza-a-lazyvim-limpio.md, sección B (se hace desde `~/.config`, con su flujo; ahí no queda config con Java hasta el cap. 10).
- Prácticas pendientes: ninguna (repasos: k01-r1 el 2026-10-31, k02-r1 el 2026-11-01; arranques listos, se corren con `./kata k01-r1`) — solo nombres; el detalle vive en EJERCICIOS.md (fuente de verdad)
- Último triage (`/pendientes`): nunca todavía
- Último examen (`/examen`): nunca todavía
- Entorno verificado: 2026-10-27 — NVIM v0.12.5, LazyVim 16.0.1 en `nvim` (limpio, 2026-10-28) y 16.0.0 en `nvim-ia`, jdtls + java-debug-adapter + java-test (Mason), openjdk 26, Maven 3.9.16, pandoc 3.10.2, ttyper 1.6.0

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
| raw (Neovim raw) | crudo, pelado | Neovim sin config ni plugins, como viene de fábrica (`nvim --clean`) |
| if you dare | si te animás | invitación medio en broma a probar algo difícil |
| visually unappealing | feo a la vista | poco atractivo visualmente |
| trapped | atrapado | sin saber cómo salir (el chiste clásico de Vim) |
| incantation | conjuro | secuencia de teclas que se repite sin entender por qué funciona |
| mental model | modelo mental | la idea interna de cómo funciona algo: permite deducir en vez de memorizar |
| command mode | modo comando | el modo que abre `:` para escribir un comando ex abajo de la pantalla |
| override (to override) | forzar, pasar por encima | ignorar una protección del editor (el `!` de `:q!`) |
| tutor (`:Tutor`) | tutorial | archivo interactivo de Neovim que enseña lo básico editándolo |
| clean slate | borrón y cuenta nueva | empezar de cero, sin nada de antes |
| back up (to back up) | respaldar | guardar una copia antes de tocar algo (acá, con `mv` en vez de `rm -rf`) |
| environment variable | variable de entorno | valor que la shell le pasa a un programa al arrancarlo (ej. `NVIM_APPNAME`) |
| shell startup file | archivo de arranque de la shell | archivo que la shell lee al abrirse (en fish, `config.fish`) |
| state | estado | lo que un programa recuerda entre usos: historial, undo, sesiones |
| cache | caché | archivos que se guardan para ir más rápido; se pueden regenerar |
| dependency | dependencia | programa externo que otro necesita para funcionar completo |
| starter template | plantilla de arranque | repo mínimo que se copia para empezar una config (LazyVim/starter) |
| clone (to clone) | clonar | descargar una copia completa de un repo git |
| flurry of activity | ráfaga de actividad | muchas cosas pasando rápido en pantalla |
| grammar (treesitter grammar) | gramática | el parser de un lenguaje para treesitter |
| plugin manager | gestor de plugins | programa que descarga, actualiza y carga los plugins (lazy.nvim) |
| dashboard | tablero, pantalla de inicio | lo que muestra LazyVim al abrir sin archivo: accesos de una sola tecla |
| self-explanatory | que se explica solo | obvio por su nombre |
| lazy loading | carga perezosa | cargar un plugin recién cuando se lo necesita, para arrancar rápido |
| barebones | pelado, lo mínimo | sin nada más que lo básico |
| out of date | desactualizado | hay una versión más nueva disponible |
| notification | notificación, aviso | mensaje emergente en una esquina de la pantalla |
| floating window | ventana flotante | ventana que aparece encima de las demás, con atajos propios (la de Lazy) |
| sync | sincronizar | en lazy.nvim (`S`): install + clean + update de una vez |
| lockfile | archivo de bloqueo | fija el commit exacto de cada plugin (`lazy-lock.json`) |
| Space mode | "modo Espacio" (nombre del libro) | apretar Espacio (`<leader>`) y elegir en el menú; en Vim no es un modo real |
| dot files | dotfiles, "archivos punto" | la config personal de Linux; el punto inicial del nombre los oculta (`.bashrc`, `.config/`) |
| settings sync | sincronización de ajustes | VS Code guarda tu config en la nube y la baja en otra PC; LazyVim no lo trae |
| bare repository | repositorio pelado | solo los datos de git, sin carpeta de trabajo propia; truco para versionar dotfiles de `$HOME` |
| GitHub Codespaces | entornos de desarrollo en la nube de GitHub | pueden instalarte tus dotfiles al crear el entorno |
| keyboard-centric | centrado en el teclado | todo se hace con el teclado; el mouse es opcional |
| modal (dialog) | ventana modal, diálogo emergente | ventanita que pide respuesta antes de seguir; NO tiene que ver con "modal editing" |
| discoverability | descubribilidad | poder descubrir qué teclas existen mirando la pantalla (dashboard, which-key) |
| leader key | tecla líder | prefijo de los atajos de la config; en LazyVim es Espacio (`<leader>`) |
| group (which-key) | grupo, submenú | entrada con `+` en el menú de which-key: abre otro nivel de teclas |
| pane | panel | cada división de la pantalla del editor (en Vim se llama ventana) |
| Insert mode | modo Inserción | las teclas escriben texto; indicador INSERT, cursor de barra |
| Normal mode | modo Normal | las teclas son comandos; indicador NORMAL, cursor de bloque |
| put | poner (pegar) | lo que significa `p`: pone el último texto copiado o borrado |
| register | registro | "cajón" con nombre donde Vim guarda texto copiado o borrado (`+` = portapapeles) |
| clipboard | portapapeles | el copiar/pegar del sistema, compartido con las otras apps |
| undo / redo | deshacer / rehacer | `u` deshace; `Ctrl-r` (en Normal) deshace el deshacer |
| append | agregar (al final) | lo que significa `a`: escribir DESPUÉS del carácter del cursor |
| home row | fila de inicio | la fila del medio del teclado, donde descansan los dedos |
| touch type | tipear sin mirar | escribir con los diez dedos sin mirar el teclado |
| remap | reasignar (una tecla) | hacer que una tecla haga lo de otra (ej. Capslock → Esc) |
| mnemonic | mnemotecnia, regla para recordar | `o` = open (abrir) una línea; minúscula hace, mayúscula agranda o invierte |
| Go To mode | "modo Ir a" (nombre del libro) | el prefijo `g` + el menú `+goto` de which-key; en Vim no es un modo real |
| afresh | desde cero, de nuevo | el código se edita mucho más de lo que se escribe desde cero |
| Visual mode | modo Visual | el modo para seleccionar texto moviendo el cursor (cap. 8) |
| Command mode | modo Comando | se entra con `:` desde Normal; se escribe un comando y Enter lo ejecuta |
| Ex command | comando Ex | lo que se escribe después de `:` (`:w`, `:q`, `:e`); el nombre viene del editor `ex` |
| command palette | paleta de comandos | buscador de comandos de VS Code/Sublime; el modo Comando se le parece |
| tab completion | completado con Tab | Tab termina de escribir el comando o la ruta por vos |
| completion menu | menú de completado | la lista de opciones que aparece mientras escribís; en LazyVim 16 la dibuja blink.cmp |
| ghost text | texto fantasma | la sugerencia en gris que aparece adelante del cursor antes de aceptarla |
| prefix | prefijo | el comienzo de una palabra: `:w` es la abreviatura de `:write` |
| nested | anidado | carpetas una dentro de otra (`foo/baz/fizz.txt`) |

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

SESIÓN #06 — 2026-10-28 — Neovim pelado y cómo salir (cap. 1, 1.7 completa)
- `nvim` o `nvim archivo` abre el editor. Neovim "raw" (pelado: sin config ni plugins) es soso; desde 0.10 trae colores más modernos, pero sigue sin íconos, explorador ni dashboard.
- Salir sin guardar: Esc → `:q!` → Enter. Esc asegura modo normal (en inserción, `:q!` se escribiría como texto); `:` abre la línea de comandos (ex); `q` = quit (salir); `!` = forzar (descarta los cambios).
- `:q` con cambios sin guardar se niega (`E37`); `:wq` guarda y sale; `:qa` sale de todo y `:qa!` de todo descartando. En LazyVim, `<leader>qq` = `:qa` (verificado en `keymaps.lua`).
- `:Tutor` abre el tutorial interactivo (en 0.12.5 solo en inglés, japonés y chino). El libro no lo asume; parte de lo que enseña LazyVim ya lo trae puesto (ej. `:set ic` → LazyVim activa `ignorecase` + `smartcase`).
- Nota del profe: el libro asume Neovim recién instalado, donde `nvim` abre el editor pelado. En esta máquina `nvim` carga la config del usuario: para verlo pelado, `nvim --clean` (factory defaults, valores de fábrica: sin config ni plugins).
- Ejercicios de la tanda: ninguno (contexto). PRÁCTICAS CREADAS: ninguna. Mudanza a `nvim-ia`: todavía no, va con la instalación de LazyVim.
- Dudas: preguntas de comprensión → bien las dos. Matiz: sin Esc, `:q!` + Enter no es "nada": escribe el texto y un salto de línea en el archivo (lo deja modificado). Salir es una SECUENCIA de teclas, no una combinación apretada a la vez.
- PRÓXIMO PASO: lo que sigue a la 1.7 (instalar LazyVim + mudanza a `nvim-ia`).

SESIÓN #07 — 2026-10-28 — Instalar LazyVim (cap. 1, 1.8.1 a 1.8.3)
- Neovim guarda todo en 4 carpetas: config (`~/.config/nvim`), datos (`~/.local/share/nvim`: plugins y Mason), estado (`~/.local/state/nvim`: historial, undo, logs) y caché (`~/.cache/nvim`). "Clean slate" (borrón y cuenta nueva) = borrar o mover las cuatro.
- `NVIM_APPNAME` (variable de entorno) cambia el nombre de las cuatro a la vez: `NVIM_APPNAME=x nvim` usa `~/.config/x`, etc. Así conviven varias configs. El libro la usa para la nueva; acá al revés: la vieja pasa a `nvim-ia` y la nueva queda como `nvim`.
- Dependencias recomendadas: lazygit (git en la terminal), ripgrep `rg` (buscar texto en el proyecto), fd (buscar archivos). Instaladas: lazygit 0.64.1, rg 15.2.0, fd 10.4.2.
- Instalar = `git clone` del starter en `~/.config/nvim` + borrar su `.git` (LazyVim se actualiza solo; la historia del repo no sirve). Acá importa el doble: `~/.config` es repo de dotfiles y un `.git` anidado le escondería los archivos.
- Nota del profe: el libro pide 3 herramientas; `:checkhealth lazyvim` de LazyVim 16 revisa 6 (git, rg, fd, lazygit, fzf, curl), todas instaladas. La URL del starter sigue vigente (README de LazyVim).
- Config tocada: mudanza a `nvim-ia` + clon del starter, hecha por el usuario y verificada (nvim = starter sin `.git`; nvim-ia con 49 plugins y Mason). Incidente: el bloque corrió dos veces y el 2º `mv` dejó basura en `nvim-ia/nvim` (config y state): borrada por el usuario y verificada. CLAUDE.md actualizado (HERRAMIENTAS, nvim-ia, caps. 1 y 16). Commit desde `~/.config`.
- Ejercicios: ninguno. PRÁCTICAS CREADAS: ninguna. Checklist nuevo: `ToDo/mudanza-a-lazyvim-limpio.md` (sirve también para el otro PC).
- Dudas: mover solo la config → bien la idea; faltó la consecuencia concreta (nvim-ia re-descarga plugins y Mason, sin historial). Por qué borrar el `.git` → bien lo de que LazyVim se actualiza solo; corregido: la config YA tiene repo (dotfiles) y un repo adentro de otro solo guarda un puntero.
- PRÓXIMO PASO: lo que sigue a la 1.8.3 (primer arranque de LazyVim).

SESIÓN #08 — 2026-10-28 — Primer arranque y el dashboard (cap. 1, 1.9; la 1.8.3 vino repetida) — tanda MIXTA (1 pantallazo)
- Primer `nvim`: lazy.nvim (gestor de plugins) descarga los plugins a `~/.local/share/nvim/lazy` y se compilan parsers de treesitter. Ante un `-- More --` (hay más), `G` salta al final; en la ventana de Lazy, `q` la cierra.
- El dashboard (pantalla de inicio) tiene acciones de UNA tecla que solo valen ahí: `f` buscar archivo, `n` nuevo, `r` recientes, `g` buscar texto, `c` config, `s` restaurar sesión, `x` extras, `l` Lazy, `q` salir (`:qa`).
- "Neovim loaded 25/70 plugins in N ms" = carga perezosa (lazy loading): arranca con los imprescindibles y el resto se carga al usarlo. De ahí el nombre "Lazy".
- `c` abre un picker sobre `stdpath('config')`: hoy es la config limpia, no la de la IA.
- Nota del profe: el starter bajó LazyVim 16.0.1 (el setup verificó 16.0.0). El dashboard es de snacks.nvim (`plugins/ui.lua`) con las mismas teclas que la figura; solo cambia el orden ("Find Text" antes de "Recent Files").
- Ejercicios: ninguno. PRÁCTICAS CREADAS: ninguna. Primer arranque hecho por el usuario (ya existen `lazy-lock.json` y `lazyvim.json`).
- Dudas: carga perezosa → bien el mecanismo; faltó la ganancia (arranque en milisegundos). `c` del dashboard → bien que muestra `~/.config/nvim`; faltó que desde la mudanza esa carpeta es el starter limpio, no la config de la IA.
- PRÓXIMO PASO: lo que sigue a la 1.9, en sesión limpia.

SESIÓN #09 — 2026-10-28 — El gestor de plugins lazy.nvim (cap. 1, 1.10 completa) — tanda MIXTA (2 pantallazos)
- lazy.nvim ≠ LazyVim: lazy.nvim es SOLO el gestor de plugins (instala, actualiza, carga perezosa); LazyVim es la distribución (plugins + config) y lazy.nvim es uno de sus plugins. Mismo autor.
- Abrir la ventana de Lazy: `l` en el dashboard, `<leader>l` (Espacio → `l`) en modo normal, o `:Lazy` (verificado en `keymaps.lua` y `plugins/ui.lua`). El modo se lee abajo a la izquierda (LazyVim usa una sola barra de estado, `laststatus = 3`).
- Es una ventana flotante (floating window) con atajos propios, todos en MAYÚSCULA: I install, U update, S sync, X clean, C check, L log, R restore, P profile, D debug, ? help; `q` cierra.
- `S` (Sync) = install + clean + update. Cada update reescribe `~/.config/nvim/lazy-lock.json` (commit exacto de cada plugin); `R` (Restore) vuelve a esas versiones. Con el lockfile en git: se deshace una actualización rota y el otro PC usa `R`, no `S`.
- Figura 3: ● cargado / ○ sin cargar; al lado, tiempo de carga y qué lo dispara (VeryLazy, LazyFile, una tecla como `<leader>ut`); debajo, los commits nuevos (conventional commits).
- "Space mode" es un nombre del libro: en Vim es la tecla líder (`<leader>` = Espacio) + el menú de which-key; el libro lo ve en el cap. 2.
- Nota del profe: el libro dice que al abrir salta el aviso "Plugin Updates" (Figura 2). El starter de LazyVim 16 trae en `lua/config/lazy.lua` `checker = { enabled = true, notify = false }`: el chequeo corre en silencio y el aviso es un ícono + número abajo a la derecha (lualine, `lazy.status.updates`). Motivo no documentado en el código.
- Ejercicios: ninguno. PRÁCTICAS CREADAS: ninguna (se prueba en vivo). Checklist nuevo: `ToDo/actualizar-plugins.md`.
- Dudas: lazy.nvim vs LazyVim → bien (analogía del rice); matiz: no es "lo mismo más liviano" (quedaría Neovim pelado + gestor vacío) y LazyVim es un plugin más que lazy.nvim actualiza. Secuencia para actualizar desde inserción → 1º `;wq` (corregido: `;` ≠ `:`, y `:wq` guarda y sale); 2º bien el núcleo (`<leader>l`, `S`, `q`), faltaron el `Esc` inicial y el `i` final.
- PRÓXIMO PASO: lo que sigue a la 1.10, en sesión limpia.

SESIÓN #10 — 2026-10-28 — Dotfiles en git y resumen del cap. 1 (cap. 1, 1.11-1.12: CAPÍTULO 1 CERRADO)
- Dotfiles = la config personal de Linux; el punto inicial del nombre la oculta (`eza -a` la muestra). LazyVim no trae "settings sync" (sincronización de ajustes) como VS Code: el autor recomienda un repo de git, y sumarle la config de la terminal, `.gitconfig` y la de la shell.
- Técnica del libro (artículo de Atlassian): bare repository (repo pelado) con el work tree en `$HOME` + un alias. La del usuario: `~/.config` como repo normal con `.gitignore` de lista blanca (`/*` + `!/carpeta`) y los secretos excluidos. Es más simple, pero no cubre la raíz de `$HOME` (`~/.gitconfig`; git también lee `~/.config/git/config`).
- Qué viaja al otro PC: `~/.config/nvim` con `lazy-lock.json`. No viajan `~/.local/share|state/nvim` ni `~/.cache/nvim` (se regeneran). Allá: pull → abrir nvim → `<leader>l` → `R`.
- Hallazgo: la lista blanca no tiene `!/nvim-ia`. Decisión del usuario: queda solo local, de consulta (para rescatar ideas); la config principal es `nvim`. El checklist de mudanza decía que el pull la traía: corregido.
- 1.12 (resumen): historia, terminal con GPU + Nerd Font, instalar Neovim y LazyVim. El cap. 2 (edición modal) abre el núcleo "A DOMINAR" y las primeras katas.
- Ejercicios: ninguno. PRÁCTICAS CREADAS: ninguna. Checklist tocado: `ToDo/mudanza-a-lazyvim-limpio.md`.
- Dudas: ninguna; preguntas de cierre (qué viaja al otro PC, qué hace `/*`) omitidas a pedido del usuario.
- PRÓXIMO PASO: cap. 2 desde el principio, en sesión limpia.

SESIÓN #11 — 2026-10-28 — Qué es la edición modal: intro y menú de Espacio (cap. 2, intro + 2.1 hasta la Figura 4)
- LazyVim es keyboard-centric (centrado en el teclado): el mouse anda, pero todo se hace con teclado y casi siempre con 1-2 teclas a la vez, sin acordes Ctrl+Shift+Alt (dolorosos y causa de lesiones). La clave: edición modal.
- Modo = la misma tecla significa otra cosa según el modo activo. "Dashboard Mode" y "Space mode" son nombres del libro: en Vim son modo Normal + atajos de una letra del buffer del dashboard, y modo Normal + tecla líder (Espacio, `vim.g.mapleader = " "`) + el menú de which-key.
- Discoverability (descubribilidad): dashboard y which-key muestran qué teclas existen; Neovim pelado no muestra nada.
- which-key: menú abajo a la derecha (preset "helix", verificado). `+` = grupo (submenú); sin `+` = acción directa; Esc cierra, Backspace vuelve un nivel. `:WhichKey` lo abre desde la raíz.
- Pareto del menú: `<leader><space>`, `<leader>/`, `<leader>,` (pickers, caps. 4 y 12) y los splits `<leader>-` (= `:sp`) / `<leader>|` (= `:vs`) (cap. 9); `` <leader>` `` = `:e #`.
- Nota del profe: la Figura 4 trae extras y atajos del autor. En LazyVim 16 limpio: `<leader>e/E` = explorador de Snacks (no mini.files); `<leader>,` dice "Buffers"; no existen `p` (extra yanky), `r`, `h`, `Del`, `Enter`, `+ai`, `+test`; `+debug` solo trae `+profiler`.
- Ejercicios: ninguno. PRÁCTICAS CREADAS: ninguna (las katas llegan con operadores y movimientos).
- Dudas: ninguna. Preguntas de cierre: 1 bien con matiz (Espacio ES la tecla líder, no "Espacio + líder"); 2 corregida (`f` es un grupo que abre submenú, `<leader>ff` busca archivos; el grep es `<leader>/`, acción directa).
- PRÓXIMO PASO: lo que sigue a la Figura 4, en sesión limpia.

SESIÓN #12 — 2026-10-28 — Modos Inserción y Normal: entrar y salir (cap. 2, 2.1 desde la Figura 4 hasta `I` y `A`)
- El meollo de la edición modal: la misma tecla hace otra cosa según el modo. `f` en el dashboard busca archivo; después de Espacio abre el grupo `+file/find`. Esc sale del menú.
- `n` en el dashboard = `:ene | startinsert` (verificado en snacks.nvim): buffer vacío y ya en Inserción, por eso aparece INSERT abajo a la izquierda. Figuras 5 y 6 (indicadores): cubiertas igual.
- Inserción (viene de vi): las teclas escriben. Ctrl-r + nombre de registro pega ese registro (`+` = portapapeles); which-key muestra la lista (plugin "registers", también en `"` de Normal).
- Normal: las teclas son comandos (cursor de bloque, NORMAL). Ctrl-r = redo (rehacer, deshace un `u`). Atajos memorables: `p` = put (poner), no paste. El autor casi no usa comandos en Inserción: vuelve a Normal.
- Salir: Esc. Ctrl-c también, pero no dispara InsertLeave ni expande abreviaturas (`:help i_CTRL-C`). Mover Esc (Capslock, `jk`): el núcleo no se remapea antes de F4; en dvorak `jk` ni siquiera está en la fila de inicio.
- Entrar: `i` antes del carácter del cursor, `a` (append) después, `A` al final de la línea, `I` antes del primer no-blanco.
- Nota del profe 1: `p` pega del portapapeles del sistema solo porque LazyVim pone `clipboard = "unnamedplus"` (`options.lua`; vacío si hay SSH). En Vim puro y `nvim --clean`, `p` usa el registro sin nombre. Se ve con `:set clipboard?`. Nota 2: el libro dice que `I` va al "very beginning" (principio absoluto); en realidad va después de la sangría; `gI` = columna 1 (`:help I`; con LSP activo no: ver Sesión #13).
- Ejercicios del libro: ninguno (`i Esc i Esc` es ilustración). PRÁCTICAS CREADAS: k01-insertar-en-su-lugar. Checklist nuevo: `ToDo/hacer-una-kata.md`.
- Dudas: ninguna. Preguntas de cierre: 1 bien (`a` para `xy`; faltó decir que `i` daba `yx`). 2 bien la idea; corregido: es `unnamedplus` (`+`, Ctrl-c/Ctrl-v), no `unnamed` (`*`, selección primaria del clic del medio), y en `--clean` `p` SÍ pega, pero lo último copiado/borrado dentro de nvim (o E353 si no hay nada).
- PRÓXIMO PASO: lo que sigue al párrafo de `I` y `A`.

SESIÓN #13 — 2026-10-28 — Mayúsculas, `o`/`O` y `gi` (cap. 2, 2.1.1 completa) — tanda MIXTA (1 pantallazo: Figura 7)
- Regla de las mayúsculas: la minúscula hace algo; la mayúscula hace lo mismo MÁS GRANDE (`i`/`a` → `I`/`A`) o lo CONTRARIO (`o` → `O`).
- `o` (open: abrir) = línea nueva debajo + Inserción; `O` = arriba. La sangría la pone nvim (`autoindent` copia la de la línea actual; LazyVim suma `smartindent` con `shiftwidth = 2` después de `{`).
- `gi` = volver a donde se SALIÓ de Inserción la última vez en ese buffer (marca `'^`, `:help gi`) y seguir escribiendo. El libro dice "entered" (entraste): impreciso.
- "Go To mode" es nombre del libro: `g` es un prefijo, como Espacio; which-key muestra el grupo `+goto` (`editor.lua`).
- El código se edita mucho más de lo que se escribe desde cero: Normal ↔ Inserción todo el tiempo, con Normal como base.
- Nota del profe 1: la Figura 7 trae extras del autor; en LazyVim 16 limpio no existen `g/` (rip-substitute), `ga` (text-case), `gp`/`gP` "Put Text…" (yanky) ni `g^A`/`g^X` (extra dial). `gD`/`gI`/`gr`/`gy` solo aparecen con LSP. `gi` dice "Go to last insert" (como la figura; el texto del libro trae otra etiqueta).
- Nota del profe 2 (corrige la #12): con LSP activo, LazyVim remapea `gI` a Goto Implementation (`lsp/init.lua:82`); la columna 1 vale solo sin LSP. Tarjeta de Anki corregida.
- Ejercicio del libro: probar a/i/o/A/I/O/gi moviéndose con el mouse (en vivo, sin entrega). PRÁCTICAS CREADAS: k02-abrir-lineas.
- Dudas: qué es "implementation" → explicado (interfaz = QUÉ, sin cuerpo; la clase que `implements` = CÓMO; `gd` va a la declaración, `gI` al cuerpo que corre). Preguntas de cierre: 1 bien (`gi`; `i` escribe donde estás). 2 bien el qué; faltó el porqué: LazyVim remapea `gI` cuando hay LSP.
- PRÓXIMO PASO: lo que sigue a la 2.1.1, en sesión limpia.

SESIÓN #14 — 2026-10-28 — Modo Visual (anticipo) y modo Comando: `:w` `:q` `:x` `:e`, completado y `:help` (cap. 2, 2.2-2.4: CAP. 2 COMPLETO) — tanda MIXTA (4 pantallazos: Figuras 8-10 y Listings 5-6)
- Modo Visual = seleccionar texto con las teclas de movimiento; el libro lo deja para el cap. 8.
- Modo Comando: `:` desde Normal abre la ventanita Cmdline (la dibuja noice.nvim) para escribir un comando Ex (de `ex`, el antecesor de vi). `<Esc>:q!<Enter>` desarmado: a Normal, a Comando, quit, forzar sin guardar, ejecutar.
- `:w` (write) guarda; `:w otro.txt` con el buffer ya nombrado escribe una COPIA (guardar como = `:saveas`). `:q` sale, `:wq` guarda y sale, `:x` igual pero escribe solo si hubo cambios. La abreviatura oficial la da `:help` con corchetes: `:w[rite]`.
- `:e ruta` (edit) abre un archivo; la ruta es relativa a la carpeta donde se abrió nvim (`:pwd`). Enter EJECUTA lo que haya en la línea; `Ctrl-y` (yes) acepta la opción del menú y deja seguir escribiendo la ruta.
- `:help tema`: la documentación viene con el editor. Prefijos por modo: `i_` Inserción, `c_` Comando, `v_` Visual (`:help i_CTRL-R`); sin prefijo es Normal. En LazyVim, `<leader>sh` busca en la ayuda con el picker; `Ctrl-]` sigue un enlace y `Ctrl-o` vuelve.
- Nota del profe: el libro describe el menú nativo (wildmenu). LazyVim 16 usa blink.cmp v1.10.2 (`extras/coding/blink.lua`, preset `cmdline`): el menú aparece SOLO al tipear después de `:`, sin nada preseleccionado; Tab/Shift-Tab (o Ctrl-n/Ctrl-p) recorren; Ctrl-y acepta; Ctrl-e cancela; ←/→ mueven el cursor; ↓/↑ NO entran a la carpeta: traen comandos del historial.
- Ejercicios de la tanda: ninguno. Lab en vivo PENDIENTE (en el nvim limpio, desde `~/Proyectos/Vim`): `:q` y ver el menú solo + Tab + Ctrl-e; `:e ejer` + Tab + Ctrl-y + Tab; `:e ` + ↓ (historial); `:help :x`. PRÁCTICAS CREADAS: ninguna.
- Dudas: ninguna. Preguntas de cierre SIN RESPONDER (el usuario tuvo que salir): (1) en `:e src/` con `main/` resaltado, ¿qué tecla acepta y deja seguir la ruta, y qué haría Enter? (2) ¿cómo se pide la ayuda de Ctrl-r en modo Inserción?
- PRÓXIMO PASO: cap. 3 (movimientos) desde el principio, en sesión limpia.

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
