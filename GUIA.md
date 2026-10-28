# GUÍA: Neovim + LazyVim con foco en Java — "LazyVim for Ambitious Developers" (Dusty Phillips); en F2, "Practical Vim" (Drew Neil)

No asume conocimiento previo — la mantiene Claude Code sesión a
sesión. Cada sesión cubre una tanda del material (acá: un rango de
secciones de un capítulo, ~250-400 líneas de texto; 3-5 imágenes si
vino como pantallazos), explicada en español y conectada con práctica
hecha a mano.
Prácticas: ver EJERCICIOS.md.

## INICIO RÁPIDO

- Último punto estudiado: cap. 1 COMPLETO (1.11 "A Note on Managing Dot Files" y 1.12 "Summary" incluidas, hasta "…in LazyVim.") → la próxima tanda es el cap. 2 (edición modal) desde el principio: https://lazyvim-ambitious-devs.phillips.codes/course/chapter-2/
- Última tanda: Sesión #10 (2026-10-28, en la sesión de Claude vim-s05)
- PRÓXIMA SESIÓN: `/rename vim-s06`
  (el nombre de la sesión de Claude sale SIEMPRE de esta línea, no se
  calcula: es un contador distinto al de las tandas, porque una sesión
  de Claude puede cubrir 2-3 tandas. Claude la actualiza al cerrar.)
- Prácticas pendientes: ninguna todavía — esta línea lista SOLO lo
  pendiente (nombres, sin historial); estados completos, fechas y
  repasos viven en EJERCICIOS.md (fuente de verdad)
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
