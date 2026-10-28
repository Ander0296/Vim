# KATA k01 — Insertar en su lugar (cap. 2, 2.1, Sesión #12)

## Enunciado

La clase Java de `inicio.txt` tiene dos errores repetidos:

- a los tres campos (fields: atributos de la clase) les falta el
  modificador `private`, que va al principio de cada línea, justo
  después de la sangría;
- a cuatro sentencias les falta el `;` del final.

Transformá `trabajo.txt` (una copia de `inicio.txt`) hasta que quede
idéntico a `objetivo.txt`.

Reglas:

- Sin flechas y sin mouse. Si te equivocás escribiendo, vale Backspace
  dentro del modo inserción; si te equivocás con un comando, Esc y `u`
  (undo: deshacer).
- Para pasar de una línea a otra usá `j` (abajo) y `k` (arriba): es lo
  único de movimiento que hace falta acá (los movimientos llegan en el
  cap. 3).
- Cada vez que entres al modo inserción, que sea con el comando que te
  deja YA en el lugar donde tenés que escribir, sin moverte antes.
- Terminá en modo normal y salí con `:wq` (write + quit: guardar y
  salir).

Par: no tiene. Es la primera kata: sirve para calibrar desde dónde
arrancás.

## Comandos (desde la carpeta de la kata)

```
cd ~/Proyectos/Vim/ejercicios/k01-insertar-en-su-lugar
cp inicio.txt trabajo.txt
nvim -W teclas.log trabajo.txt
diff -u trabajo.txt objetivo.txt
```

Si `diff` no muestra nada, salió. Si muestra líneas, se rehace TODO
desde el `cp` (volver a abrir nvim para arreglarlo pisa el log del
primer intento).

Si te trabás: revisá la Sesión #12 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean`).

## MI EXPLICACIÓN

(qué hace cada comando que usaste y por qué lo elegiste)

---

PROMPT DE ENTREGA (copiá esto y pegalo en Claude cuando termines):

```
/entrega k01 "insertar en su lugar" — mi trabajo está en ejercicios/k01-insertar-en-su-lugar/ (trabajo.txt, teclas.log y MI EXPLICACIÓN en el README)
```
