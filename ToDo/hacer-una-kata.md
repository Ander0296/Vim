# Checklist — hacer una kata de edición en nvim

Recorrelo cada vez que hacés una kata: antes de abrir nvim, mientras
trabajás y antes de entregar.

## Antes de abrir nvim

- [ ] Estoy en la carpeta de la kata (`pwd` termina en `kNN-nombre`).
- [ ] Copié el inicio otra vez: `cp inicio.txt trabajo.txt` (o `.java`
  si la kata es de Java). Un `trabajo.txt` con cambios de un intento
  viejo hace que el log nuevo no cuente toda la historia.
- [ ] Abro con `nvim -W teclas.log trabajo.txt`: `-W` en MAYÚSCULA y el
  log antes del archivo. Sin `-W` no se graba ninguna tecla.
- [ ] Uso `nvim` (mi LazyVim), no `nvim --clean` ni
  `NVIM_APPNAME=nvim-ia nvim`: sus atajos son parte de lo que se mide.

## Mientras trabajo

- [ ] Sin flechas ni mouse.
- [ ] Si un comando salió mal: Esc y `u` (deshacer), en vez de parchar
  encima.
- [ ] Termino en modo normal (abajo a la izquierda dice NORMAL) y salgo
  con `:wq`.

## Antes de entregar

- [ ] `diff -u trabajo.txt objetivo.txt` no muestra NADA.
- [ ] Si mostró algo y abrí nvim de nuevo para arreglarlo: rehago TODO
  desde el `cp`. `-W` pisa el log, así que el segundo intento borra las
  teclas del primero y el log queda incompleto.
- [ ] Llené MI EXPLICACIÓN del README: qué hace cada comando que usé y
  por qué lo elegí.
- [ ] Copio el prompt `/entrega` del final del README tal cual.
