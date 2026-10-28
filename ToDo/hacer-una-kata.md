# Checklist — hacer una kata de edición en nvim

Recorrelo cada vez que hacés una kata: antes de abrir nvim, mientras
trabajás y antes de entregar.

## Antes de abrir nvim

- [ ] Leí el enunciado ANTES de abrir nvim. Por qué: todo lo que hago
  adentro (abrir el README, el explorador, scrollear) queda en el log y
  se mezcla con la kata.
- [ ] Estoy en `~/Proyectos/Vim` y corro `./kata kNN` (un repaso:
  `./kata kNN-rX`). El resto lo hace solo: copia el inicio, abre mi
  `nvim` grabando cada tecla y, al salir, compara contra el objetivo.

## Mientras trabajo

- [ ] Sin flechas ni mouse.
- [ ] Antes de entrar a inserción, miro DÓNDE tengo que escribir. Si es
  al principio o al final de la línea, entro con `I` o `A`, no con
  `i`/`a` después de caminar con `hhhh`/`llll`. Por qué: `.` repite
  también el lugar; con `I`/`A` el `.` cae solo en la línea siguiente.
- [ ] Si un comando salió mal: Esc y `u` (deshacer), en vez de parchar
  encima.
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
