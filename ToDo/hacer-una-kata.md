# Checklist — hacer una kata de edición en nvim

Recorrelo cada vez que hacés una kata (de estreno `kNN` o mixta `mNN`):
antes de abrir nvim, mientras trabajás y antes de entregar. La kata
tiene UNA sola regla (sin flechas ni mouse); el resto lo elegís vos.

## Antes de abrir nvim

- [ ] Leí el enunciado ANTES de abrir nvim. Por qué: todo lo que hago
  adentro (abrir el README, el explorador, scrollear) queda en el log y
  se mezcla con la kata.
- [ ] Miré el par. Por qué: si mi plan gasta mucho más que eso, hay un
  camino más corto que todavía no estoy viendo.
- [ ] Estoy en `~/Proyectos/Vim` y corro `./kata kNN` (o `./kata mNN`).
  El resto lo hace solo: copia el inicio, abre mi `nvim` grabando cada
  tecla y, al salir, compara contra el objetivo y cuenta mis teclas.

## Mientras trabajo

- [ ] Sin flechas ni mouse.
- [ ] Si el cursor ya está SOBRE la letra mala, es `r` + la letra
  buena: nada de `a`/`i` + Backspace. Por qué: entrar a inserción y
  borrar hacia atrás suma teclas.
- [ ] Antes de entrar a inserción, miro DÓNDE tengo que escribir. Si es
  al principio o al final de la línea, entro con `I` o `A`, no con
  `i`/`a` después de caminar con `hhhh`/`llll`.
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
  con `:x` (o `:wq`). Guardar sin salir (`:w`, Ctrl-s) NO alcanza: nvim
  escribe `teclas.log` recién al cerrarse, y mientras siga abierto el
  log está vacío.

## Antes de entregar

- [ ] `./kata` terminó con ✅. Miro mis teclas contra el par: si me
  sobran muchas y tengo ganas, la corro otra vez para bajar la marca
  (opcional).
- [ ] Si dijo ❌: corro `./kata kNN` otra vez, que arranca de cero. No
  arreglo `trabajo` abriéndolo a mano: esas teclas no quedan en el log.
- [ ] Entrego con `/entrega kNN`. No hace falta explicar cada comando:
  el profe lee el log y me pregunta por 2-3 decisiones.
