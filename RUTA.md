# RUTA — el plan completo: de los libros a ser pro en Neovim para programar Java

Este archivo define las FASES del proyecto. La fase actual lleva la
marca (⬅ FASE ACTUAL). Los detalles finos de cada fase se definen AL
LLEGAR, con lo vigente en ese momento.

## Lo que NUNCA cambia (en todas las fases)

- Las sesiones numeradas, Engram, GUIA.md y EJERCICIOS.md.
- Yo hago toda la práctica a mano; Claude explica, corrige y guía.
- Los repasos espaciados (evolucionan a integradores, no desaparecen).
- git lo maneja el profe: pull al abrir, commit + push al cerrar.
- Todo en español; lo citado en inglés, traducido al lado.
- Lo instalado gana sobre el libro: si no coinciden, se verifica en mi
  máquina y se anota como NOTA DEL PROFE.
- Mi config vive en `~/.config/nvim` y la escribo yo, a mano, con su
  propio git: este repo registra lo aprendido, nunca copia la config.

## FASE 1 — LazyVim for Ambitious Developers (⬅ FASE ACTUAL)

Objetivo: terminar los 20 capítulos ENTENDIENDO, no solo leyendo: la
gramática modal, la navegación, los pickers y las herramientas de
programación de LazyVim, sobre la versión instalada (LazyVim 16).

Cómo: tandas por rango de secciones + katas de edición grabadas con
`nvim -W` + preguntas de concepto. Desde el cap. 10, prácticas sobre
`java-lab/` (LSP, navegación, debug y tests de Java).

Termina cuando: los 20 capítulos están explicados, PENDIENTES.md en
cero, los repasos individuales al día, y pasé la prueba de victoria
EN VIVO, sin material al lado:
- una kata NUEVA de gramática modal (operador + movimiento/objeto)
  resuelta con el `teclas.log` sin flechas ni Backspace, en no más de
  1,5 × el par;
- sobre `java-lab/`: ir a la definición, ver las referencias,
  renombrar un método, poner un breakpoint y correr un test, todo
  desde nvim y sin preguntar ningún atajo.

## FASE 2 — Practical Vim (Vim puro, a fondo)

Objetivo: pasar de "uso LazyVim" a "entiendo Vim": el modelo que está
debajo de todos los atajos, con "Practical Vim" 2ª ed. (Drew Neil).

- Primera tarea de la fase: crear `ToDo/practical-vim-vs-lazyvim.md`
  con cada choque entre el libro (Vim puro) y LazyVim, VERIFICADO en
  la config instalada (ya se sabe de `s`/`S` → flash y `gs` →
  mini.surround).
- Material: el PDF lo aporto yo; el texto sale con `pdftotext`.
- Evaluación simulada con Claude: katas sin material al lado.
- Los repasos individuales de F1 que queden se terminan acá.

Termina cuando: el libro está cubierto (con el Pareto que se fije al
llegar), el checklist de choques está completo, y resuelvo en vivo una
kata de macro o de `:g`/`:normal` sobre un archivo Java de 50+ líneas,
sin material al lado.

## FASE 3 — Mundo real: HeadFirst-Java 100% en Neovim

Objetivo: cerrar la brecha entre "hago katas" y "trabajo así todos los
días".

- Hacer HeadFirst-Java ENTERO en nvim, sin abrir ningún IDE: editar,
  compilar, correr, debuggear y testear desde nvim y la terminal.
- Cada fricción real (algo que en un IDE es un clic y acá no sé hacer)
  se anota y se resuelve: ese es el temario de esta fase.
- Plugins y herramientas de esta fase se eligen AL LLEGAR, con lo
  vigente en ese momento.

Termina cuando: 4 semanas seguidas de HeadFirst-Java sin abrir un IDE,
con la lista de fricciones en cero (cada una resuelta o dada de baja
con su motivo).

## FASE 4 — Referente: config propia entendida línea por línea

- Recorrer `~/.config/nvim` ENTERA y poder explicar cada línea: qué
  hace, por qué está, qué pasa si la saco. Lo que no entienda o no use,
  se borra.
- Diseñar keymaps propios pensados para dvorak (recién acá se tocan
  teclas del núcleo, si conviene), con la ergonomía medida en mis
  `teclas.log` de todo el proyecto.

Termina cuando: (a) explico en voz alta, sin documentación, cualquier
archivo de mi config elegido al azar, y (b) reconstruyo mi entorno de
Neovim en una máquina limpia desde mi repo de dotfiles, sin ayuda.

## Decisiones que se toman AL LLEGAR (a propósito no se fijan hoy)

- Cómo se crea y se resetea `java-lab/` entre prácticas (cap. 10).
- El Pareto fino de Practical Vim (F2), con el índice del PDF en mano.
- Plugins y herramientas de F3 (cambian; se busca lo vigente).
- Qué keymaps dvorak valen la pena en F4 (salen de los `teclas.log`
  reales, no de un blog).
