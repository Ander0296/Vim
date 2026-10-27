# Vim — aprender Neovim + LazyVim con Claude Code (foco en Java)

Sistema de estudio con Claude Code como profesor particular, creado
desde mi plantilla-profesor: yo le paso el material por tandas, él lo
explica en español, mantiene la guía (`GUIA.md`), lleva las prácticas
con repetición espaciada (`EJERCICIOS.md`) y el plan por fases hacia mi
objetivo (`RUTA.md`). **Yo hago TODA la práctica a mano.**

No hay mensajes que copiar y pegar: **cada cosa es un comando**, y el
profe me dice cuál sigue. Tampoco escribo comandos de git: los hace él.

¿Primera vez en la vida con git/GitHub/SSH, o vas a enlazar otro PC?
→ Leé `INSTALACION.md`: ahí está TODO explicado desde cero.

## Qué estudio acá

- **Material 1 (FASE 1):** "LazyVim for Ambitious Developers", de Dusty
  Phillips. Libro libre online, 20 capítulos, en inglés (el profe
  traduce todo lo que cita).
- **Material 2 (FASE 2):** "Practical Vim" 2ª ed., de Drew Neil (Vim
  puro). El PDF lo aporto yo cuando lleguemos.
- **Objetivo:** ser pro en Neovim para programar Java: editar sin
  pensar, moverme por el código con LSP y pickers, debuggear y testear
  Java desde nvim, y tener una config propia entendida línea por línea.
- **Mi config de nvim NO vive acá**: está en `~/.config/nvim`, en mi
  repo de dotfiles, y la escribo yo. Este repo guarda lo que aprendo.

## Los dos lugares donde se escriben cosas

- `[TERMINAL]` = la consola de siempre
- `[CLAUDE]` = dentro del programa, después de escribir `claude`

## El mapa en 30 segundos

```
Vim/
├── material/        el capítulo que estoy viendo (capNN.md, bajado con
│   │                curl + pandoc). NO va a git: copyright
│   └── visto/       capítulos ya explicados — los archiva Claude solo
├── ejercicios/      mis prácticas. Claude deja el ENUNCIADO + el
│   │                prompt de entrega; la solución la hago yo
│   ├── kNN-.../     KATAS: inicio.txt → objetivo.txt, con mis teclas
│   │                grabadas en teclas.log
│   ├── jNN-.../     prácticas sobre java-lab/ (desde el cap. 10)
│   ├── libNN-...md  preguntas de concepto, se responden por escrito
│   └── repasos/     los repasos, siempre desde cero
├── java-lab/        (llega en el cap. 10) proyecto Java chico para
│                    practicar LSP, debug y tests
├── ToDo/            checklists: qué verificar antes de dar algo por
│                    terminado (los mantiene Claude)
├── GUIA.md        ★ lo que ENTENDÍ, sesión a sesión
├── EJERCICIOS.md  ★ SOLO lo vivo: pendientes, repasos y conceptos
│                    dominados. Se lee entero cada sesión: va corto
├── PENDIENTES.md    la deuda que NO es una práctica: material que no
│                    llegó y contenido diferido. Lo triagea
│                    /pendientes, no se lee al empezar
├── RUTA.md          el plan por fases hasta mi objetivo
├── MECANOGRAFIA.md  líneas de comandos de Vim para tipear (ttyper)
├── ANKI.txt         tarjetas de repaso 80/20 para importar en Anki
├── CLAUDE.md        las reglas del profe
└── .claude/          los comandos (commands/) y los dos automatismos
                      (hooks/): pull al abrir, y el candado
```

**Los dos automatismos que corren solos:**
- al abrir cualquier sesión se hace `git pull`, aunque me olvide de
  `/arranque`;
- Claude tiene **prohibido por el harness** editar o pisar cualquier archivo
  que ya exista en las carpetas de trabajo (`ejercicios/` y `java-lab/`).
  Solo puede CREAR archivos nuevos (el de arranque). Si algún día necesito
  desactivarlo: `/hooks`.

Archivos que crecen aparte y NO se leen al empezar:
`GUIA-ARCHIVO.md` (sesiones viejas) y `EJERCICIOS-ARCHIVO.md`
(prácticas completadas con su corrección).

# ============================================================
# EL ÚNICO FLUJO QUE TENGO QUE SABER
# ============================================================

Da igual si vengo a estudiar material nuevo, a entregar una práctica o
a hacer un repaso. **Siempre es lo mismo:**

```
[TERMINAL]  cd ~/Proyectos/Vim
[TERMINAL]  si hace falta, bajo el capítulo a material/  (ver "Cómo traer una tanda")
[TERMINAL]  claude
[CLAUDE]    /arranque
```

Y ya está. El profe hace `git pull`, mira dónde quedamos, qué prácticas
tengo pendientes y qué repasos vencieron, y me dice en menos de 10
líneas qué toca hoy. Termina siempre con un bloque así:

```
▶ SIGUE: explicar las secciones 2.1 a 2.4 (tanda de texto, ~300 líneas)
  1. /rename vim-s01     ← el nombre de ESTA sesión
  2. /tanda
```

Copio eso y sigo. **No tengo que acordarme de ningún número, ningún
nombre ni ningún mensaje.** Si el bloque no aparece, lo pido: "¿qué
sigue?".

Si quiero forzar algo distinto a lo que detectó, se lo digo de una:
`/arranque vengo a entregar la kata 3`.

El `/setup` ya se hizo (2026-10-27): el proyecto arranca directo con
`/arranque`. La primera sesión se llama `vim-s01` y empieza por el
capítulo 1.

# ============================================================
# LOS COMANDOS
# ============================================================

Los prompts completos viven en `.claude/commands/`.

| Comando | Para qué | Cuándo lo uso |
| --- | --- | --- |
| `/arranque` | dónde quedamos, cómo se llama esta sesión y qué toca hoy | **siempre, primero** |
| `/tanda` | me explica las secciones del capítulo que está en `material/` | por cada tanda |
| `/entrega` | corrige la práctica que terminé (kata, java-lab o preguntas) | cuando termino una |
| `/repaso` | repaso vencido, desde cero | cuando el profe avisa |
| `/pendientes` | triage: qué se pudre, qué se salda, qué doy de baja | domingo, 5 minutos |
| `/examen` | me toma examen en frío, sin material al lado | cuando quiera probarme |
| `/cambio` | cierra esta sesión y abre una limpia | mitad del día |
| `/cierre` | guarda todo y sube a git | antes de salir, siempre |
| `/setup` | configura el proyecto | ya se corrió (2026-10-27) |

Todos aceptan contexto extra: `/tanda cap. 2, de la 2.1 a la 2.4`,
`/entrega kata k03 en ejercicios/k03-borrar-hasta-la-coma/, diff vacío`.

El prompt de `/entrega` ya relleno está **al final de cada archivo de
arranque** (en una kata, al final de su `README.md`): lo copio de ahí,
es más rápido.

# ============================================================
# CÓMO TRAER UNA TANDA (esto define si la sesión vuela o se arrastra)
# ============================================================

Una tanda es el pedazo de material que le paso a Claude de una vez.
Lo que hace lenta y cara una sesión es el material acumulado en el
contexto: TODO lo que le pasé antes se le vuelve a enviar en cada
respuesta. Por eso el tamaño de la tanda depende del FORMATO.

REGLA MADRE: el libro es una página web con texto, así que va como
TEXTO. Un pantallazo cuesta 3 o 4 veces más que la misma página en
texto, y encima Claude lo lee con menos precisión.

El libro está online, un capítulo por página. Lo bajo de a UN capítulo,
ya convertido a texto, con este comando (desde `~/Proyectos/Vim`;
este ejemplo es el capítulo 2):

```
curl -s https://lazyvim-ambitious-devs.phillips.codes/course/chapter-2/ | pandoc -f html -t gfm --wrap=none -o material/cap02.md
```

Qué hace cada parte:
- `curl -s <dirección>` baja la página web (el HTML), sin mostrar la
  barra de progreso.
- `|` le pasa lo que bajó al comando siguiente.
- `pandoc -f html -t gfm` lo convierte de HTML a Markdown (texto con
  títulos `##`); `--wrap=none` no corta las líneas largas.
- `-o material/cap02.md` lo guarda en ese archivo.

Para otro capítulo cambio el número en DOS lugares: `chapter-2` y
`cap02` (siempre con dos dígitos: `cap07`, `cap12`).

Una TANDA no es el capítulo entero: es un rango de secciones numeradas
(2.1, 2.2...), unas 250-400 líneas. El capítulo queda en `material/`
hasta que se explica su última sección; el profe lee solo el pedazo de
cada tanda y anota por dónde vamos. Yo no corto nada: si quiero, le
digo qué secciones (`/tanda cap. 2, de la 2.1 a la 2.4`), y si no,
elige él.

| Formato del material             | Tanda                                   | Tandas por sesión |
| -------------------------------- | --------------------------------------- | ----------------- |
| TEXTO (el capítulo en .md)       | 250-400 líneas (menos si es muy denso)  | 2-3               |
| IMÁGENES (pantallazos)           | 3-5 imágenes                            | 1                 |
| MIXTA (aunque sea 1 imagen)      | como imágenes                           | 1                 |

Pantallazos: SOLO si el libro muestra algo visual que el texto pierde
(una captura de cómo se ve la pantalla, un popup, un layout de
ventanas). Ese pantallazo suelto va a `material/` y el resto sigue en
texto; la tanda pasa a ser mixta: una sola en esa sesión.

Cuando se termina un capítulo, Claude mueve solo su `capNN.md` a
`material/visto/`. Yo no muevo nada.

En la FASE 2 (Practical Vim) el material es un PDF que aporto yo: el
texto se saca con `pdftotext` y el profe me pasa el comando exacto al
llegar.

# ============================================================
# CÓMO SE HACE UNA KATA, PASO A PASO
# ============================================================

Una KATA es un ejercicio corto de edición: un texto de partida
(`inicio.txt`) que tengo que convertir en otro (`objetivo.txt`) dentro
de nvim, con las menos teclas posibles. nvim graba cada tecla que
aprieto, así el profe ve no solo SI llegué, sino CÓMO llegué.

Cada kata es una carpeta en `ejercicios/` (ej:
`ejercicios/k01-borrar-palabras/`) con tres archivos que deja el profe:
`README.md` (el enunciado, los comandos y el prompt de entrega),
`inicio.txt` y `objetivo.txt`. Esos dos son el ENUNCIADO: no los toco.

**1. `[TERMINAL]` Entro a la carpeta de la kata:**

```
cd ~/Proyectos/Vim/ejercicios/k01-borrar-palabras
```

**2. `[TERMINAL]` Miro qué hay que cambiar** (las líneas con `-` son lo
que sobra, las con `+` lo que tiene que quedar):

```
diff -u inicio.txt objetivo.txt
```

**3. `[TERMINAL]` Hago mi copia de trabajo:**

```
cp inicio.txt trabajo.txt
```

**4. `[TERMINAL]` Abro nvim GRABANDO mis teclas:**

```
nvim -W teclas.log trabajo.txt
```

`-W` (mayúscula) graba en `teclas.log` todo lo que tecleo hasta que
salgo. Es con mi config de LazyVim de siempre: nada de `--clean`.
Edito hasta que quede como el objetivo y salgo con `:wq`.

**5. `[TERMINAL]` Compruebo el resultado:**

```
diff -u trabajo.txt objetivo.txt
```

Sin salida = salió. Si muestra líneas, vuelvo al paso 3: cada intento
pisa `teclas.log`, así que queda grabado solo el último (el bueno).

**6. Explico.** En la sección `MI EXPLICACIÓN` del `README.md` de la
kata escribo qué comandos usé y por qué (o lo digo en el chat al
entregar). Teclear bien sin saber por qué no cuenta.

**7. `[CLAUDE]` Entrego** con el prompt `/entrega` que está al final del
`README.md`.

El profe mira mis teclas y me corrige la EFICIENCIA: "usaste `xxxx`,
era `dw`". Si la kata dice **"Par: N teclas"**, esa es la meta (como en
VimGolf): no hace falta clavarla, sirve para saber cuánto margen tengo.
Flechas, Backspace o `jjjj` en modo normal siempre aparecen en la
corrección.

Si una kata usa archivos `.java` (pasa cuando nvim tiene que saber que
es Java, por ejemplo para objetos de texto como `af` = una función),
los pasos son los mismos con `.java` en vez de `.txt`: el `README.md`
de esa kata ya los trae así.

Los otros dos tipos de práctica: `jNN` (sobre el proyecto `java-lab/`,
desde el cap. 10; su `README.md` dice desde dónde abrir nvim) y `libNN`
(preguntas de concepto: respondo por escrito en el mismo archivo, en
`MI RESPUESTA`).

# ============================================================
# CÓMO ES UNA SESIÓN, PASO A PASO (como si no supiera nada)
# ============================================================

Dos palabras que uso todo el tiempo, y no son lo mismo:

- **SESIÓN** = una conversación con Claude, de punta a punta. Empieza cuando
  escribo `claude` en la terminal y termina cuando aprieto `Ctrl+D`.
- **TANDA** = el pedazo de material que le paso de una vez.

**En una sesión puede entrar más de una tanda.** Cuántas, no lo calculo yo:
me lo dice el profe (ver "quién decide qué", más abajo).

### PASO 1 — preparo el material `[TERMINAL]`

```
cd ~/Proyectos/Vim
```

Si el capítulo que toca todavía no está en `material/`, lo bajo con el
comando de "Cómo traer una tanda". Si ya está (vamos por la mitad de
ese capítulo), no hago nada: el profe sabe por qué sección vamos.

Si hoy no vengo a ver material nuevo —vengo a entregar una práctica, a hacer
un repaso o a que me tome examen— este paso no va.

### PASO 2 — abro la sesión `[TERMINAL]`

```
claude
```

Al abrir, el profe hace `git pull` solo. No tengo que hacer nada.

### PASO 3 — `/arranque` `[CLAUDE]`

**Siempre es el primer comando, sin excepción.** Me responde en menos de 10
líneas: dónde quedamos, qué prácticas tengo pendientes, qué repasos
vencieron y qué toca hoy. Y termina con un bloque así:

```
▶ SIGUE: explicar las secciones 3.1 a 3.4 (tanda de texto, ~300 líneas)
  1. /rename vim-s08
  2. /tanda
```

Si quiero otra cosa, se lo digo de una: `/arranque vengo a entregar la kata 3`.

### PASO 4 — le pongo nombre a la sesión `[CLAUDE]`

Copio el `/rename` que me dio y lo pego. Eso es todo lo que hace: le pone
nombre a esta conversación para poder retomarla con `claude --resume` si se
cierra la terminal. **El número no lo invento yo ni lo cuento**: sale de la
guía y me lo pasa el profe ya escrito.

### PASO 5 — entrego lo que traigo hecho `[CLAUDE]`

Si terminé una práctica, va **antes** que el material nuevo: el prompt ya
relleno está al final del archivo de arranque, lo copio de ahí.

```
/entrega kata k03 en ejercicios/k03-borrar-hasta-la-coma/, diff vacío
```

Si toca un repaso vencido, `/repaso`. Si el profe me propuso examen,
`/examen`.

### PASO 6 — `/tanda` `[CLAUDE]`

Me explica el material pieza por pieza, anunciando cuál va ("SECCIÓN 2.3:")
para que lo siga con la vista. Cuando termina, deja todo guardado solo:
guía, líneas de tipeo, tarjetas de Anki, y si se terminó el capítulo lo
mueve a `material/visto/`.

**Puedo interrumpirlo cuando quiera.** Si algo no se entendió, lo digo y lo
explica de nuevo de otra forma, las veces que haga falta. Eso no "gasta" la
sesión: es exactamente para lo que está.

### PASO 7 — el profe decide qué sigue `[CLAUDE]`

Acá no decido yo. Al terminar la tanda me dice una de estas tres, con el
motivo en una línea:

| Me dice | Qué hago |
| --- | --- |
| "seguimos con otra tanda" | otro `/tanda` (si es otro capítulo, primero lo bajo a `material/`) |
| "conviene cortar acá" | `/cambio` → `Ctrl+D` → `claude` → el `/rename` que me dio |
| "cerremos el día" | `/cierre` |

**`/cambio` no es lo mismo que `/cierre`.** `/cambio` es "sigo estudiando
hoy, pero en una conversación limpia": guarda todo, sube a git y me da el
nombre de la sesión siguiente. `/cierre` es "terminé por hoy".

### PASO 8 — cierro `[CLAUDE]` + `[TERMINAL]`

```
/cierre
```

Verifica que quedó todo guardado, archiva lo cerrado, me muestra qué cambió
en git y me pide el OK para subirlo. Después, `Ctrl+D` y listo.

**Nunca me voy sin `/cierre`.** Es lo que guarda el día y lo sube: sin eso,
mañana (o el otro PC) no se entera de nada.

# ============================================================
# QUIÉN DECIDE QUÉ (para no tener que acordarme de nada)
# ============================================================

| Decisión | Quién |
| --- | --- |
| Qué material entra hoy | **yo** |
| Si la tanda es muy grande | el profe me avisa |
| **Cuándo cortar la sesión** | **el profe** — me lo dice con el motivo |
| Cómo se llama cada sesión | el profe (sale de la guía) |
| **Cuándo tomar examen** | **el profe lo propone**, yo digo sí o no |
| Cuándo toca un repaso | el profe (las fechas están agendadas) |
| Qué pendiente se da de baja | yo, con la propuesta del profe (`/pendientes`) |
| Resolver las prácticas | **yo, siempre** |
| Cambios en mi config de nvim | **yo**, a mano, en `~/.config/nvim` (el profe explica qué y dónde) |
| Todo lo de git de ESTE repo | el profe (`pull` al abrir, `commit` + `push` al cerrar) |

Si en algún momento no sé qué sigue, la pregunta es literal: **"¿qué sigue?"**
El profe siempre tiene que poder contestarla con un bloque `▶ SIGUE`.

### Cuándo me va a proponer un examen

No tengo que acordarme: me lo propone él, en una línea, cuando pasa alguna de
estas. Si digo que no, no insiste.

- Sumé 3 conceptos nuevos a la lista de dominados.
- Cerré una unidad del material.
- Se graduó una práctica (pasó su tercer repaso).
- Pasaron ~2 semanas sin ningún examen.
- Contesté algo con la palabra correcta pero sonó recitado.

El examen va **al principio** de una sesión, nunca al final de una cargada:
ahí el que rinde mal es el contexto, no yo.

# ============================================================
# SI SE CERRÓ LA TERMINAL SIN QUERER (mismo día)
# ============================================================

`[TERMINAL]` `claude --resume vim-sNN`
Solo para retomar el MISMO día. Día nuevo = sesión nueva.

# ============================================================
# REGLAS DE ORO
# ============================================================

1. `/arranque` siempre primero. De ahí sale el nombre de la sesión y
   todo lo demás.
2. El libro va como TEXTO (curl + pandoc). Pantallazo solo para lo que
   el texto pierde.
3. Tamaño de tanda según formato (tabla de arriba). Es un techo, no una
   cuota: si me paso, el profe me avisa.
4. NUNCA salir sin `/cierre`: es lo que guarda el día y lo sube.
5. **Cuándo cortar lo dice el profe**, yo no lo calculo. Cuando lo dice:
   `/cambio` primero, nunca `Ctrl+D` pelado — sin eso la tanda no queda
   registrada en la guía y se pierde. Y si noto que empieza a olvidar
   cosas dichas antes o se pone lento, se lo digo: esa es la señal de
   contexto saturado y se corta igual.
6. Los ejercicios que trae el propio material SIEMPRE los intento a
   mano ANTES de mirar la solución o pedírsela a Claude.
7. Los repasos se hacen DESDE CERO, sin mirar mi versión original.
8. `material/` NUNCA va a git (copyright, y este repo es público; ya
   está en `.gitignore`). El profe lo verifica antes de cada commit.
9. El número de sesión solo avanza. Varias sesiones en un día es lo
   NORMAL: cada tanda de imágenes abre una nueva.
10. Las katas SIEMPRE con `nvim -W teclas.log` y con mi config de
    siempre (nunca `--clean`): sin el log, el profe no puede corregir
    el CÓMO.
11. Mi config de nvim NO vive en este repo: los cambios van en
    `~/.config/nvim`, escritos por mí, con el git de `~/.config`.

# ============================================================
# MECANOGRAFÍA Y TARJETAS ANKI
# ============================================================

Mecanografía (las líneas salen de `MECANOGRAFIA.md`):
- Acá no tipeo frases: tipeo COMANDOS DE VIM de lo que estudié (ej:
  `ciw dap :%s/foo/bar/g yi(`), para que la gramática me quede en los
  dedos en dvorak.
- CTRL+SUPER+ALT+T (atajo de mis dotfiles) abre/oculta ttyper flotante
  con una línea al azar de mis proyectos de estudio.
- Al terminar una línea: `q` pasa a otra al azar, `r` repite la misma.
  Cada línea vive en su propio archivo de ttyper
  (`~/.config/ttyper/texts/vim-sNN.txt`); Claude solo agrega los
  archivos nuevos al cerrar cada tanda. Yo no los toco.

Tarjetas Anki (`ANKI.txt`, mazo "Vim"):
- En Anki: Archivo → Importar → elegir el `ANKI.txt` de este repo. El
  mazo, el separador tab y las etiquetas ya vienen preconfigurados en
  las cabeceras del propio archivo.
- Re-importar el MISMO archivo no duplica: actualiza las tarjetas que
  cambiaron y agrega las nuevas (Anki matchea por la pregunta).
- Rutina: después de cada `git pull` con tarjetas nuevas, re-importo.
