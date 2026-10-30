# Checklist — hacer una kata de edición en nvim

Recorrelo cada vez que hacés una kata: antes de abrir nvim, mientras
trabajás y antes de entregar.

## Antes de abrir nvim

- [ ] Leí el enunciado ANTES de abrir nvim. Por qué: todo lo que hago
  adentro (abrir el README, el explorador, scrollear) queda en el log y
  se mezcla con la kata.
- [ ] Anoto qué teclas la kata me OBLIGA a usar (ej.: "`w`/`e`/`b` en
  al menos una corrección"), no solo las prohibidas. Antes de salir,
  chequeo que las usé. Por qué: ni el ✅ ni el par detectan una tecla
  obligatoria que nunca apreté.
- [ ] Estoy en `~/Proyectos/Vim` y corro `./kata kNN` (un repaso:
  `./kata kNN-rX`). El resto lo hace solo: copia el inicio, abre mi
  `nvim` grabando cada tecla y, al salir, compara contra el objetivo.

## Mientras trabajo

- [ ] Sin flechas ni mouse.
- [ ] Antes de cada salto, chequeo que la tecla esté entre las que la
  kata permite. Por qué: un `3j` o un `f` llegan igual y el ✅ no lo
  detecta, pero ese salto no entrenó lo que la kata buscaba.
- [ ] Antes de corregir, chequeo que el comando de edición también esté
  permitido. Si el cursor ya está SOBRE la letra mala y la kata pide
  `r`, es `r` + la letra buena: nada de `a`/`i` + Backspace. Por qué:
  entrar a inserción y borrar hacia atrás suma teclas, y el Backspace es
  justo lo que la kata quiere sacarte.
- [ ] Antes de entrar a inserción, miro DÓNDE tengo que escribir. Si es
  al principio o al final de la línea, entro con `I` o `A`, no con
  `i`/`a` después de caminar con `hhhh`/`llll`. Por qué: `.` repite
  también el lugar; con `I`/`A` el `.` cae solo en la línea siguiente.
- [ ] Después de apretar `A` (o `I`), miro que el cursor haya saltado al
  final (o al principio) de la línea ANTES de escribir. Si no saltó,
  apreté `a` (o `i`) sin Shift: Esc y de nuevo. Por qué: `a` también
  entra a Inserción, pero justo a la derecha del cursor; que el texto
  caiga al final es casualidad, no el comando.
- [ ] Al abrir una línea nueva, miro en qué columna quedó el cursor
  ANTES de escribir. Por qué: la línea nueva copia la sangría de la
  línea desde la que la abrí, y una línea vacía no tiene sangría.
- [ ] Si un comando salió mal: Esc y `u` (deshacer), en vez de parchar
  encima.
- [ ] Antes de salir, comparo la pantalla contra el objetivo línea por
  línea: cada `;`, cada espacio, cada línea vacía (el objetivo, abierto
  en OTRA terminal, no dentro de nvim). Por qué: un ❌ obliga a correr
  la kata de cero, y un cambio olvidado se ve en 10 segundos mirando.
- [ ] Termino en modo normal (abajo a la izquierda dice NORMAL) y salgo
  con `:wq`. Guardar sin salir (`:w`, Ctrl-s) NO alcanza: nvim escribe
  `teclas.log` recién al cerrarse, y mientras siga abierto el log está
  vacío.

## Antes de entregar

- [ ] `./kata` terminó con ✅.
- [ ] Si dijo ❌: corro `./kata kNN` otra vez, que arranca de cero. No
  arreglo `trabajo` abriéndolo a mano: esas teclas no quedan en el log.
- [ ] Entrego con `/entrega kNN` y en el mismo mensaje cuento qué hace
  cada comando que usé y por qué lo elegí.
