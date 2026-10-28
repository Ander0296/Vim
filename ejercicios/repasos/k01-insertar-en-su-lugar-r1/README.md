# REPASO k01-r1 — Insertar en su lugar (kata k01; cap. 2, 2.1, Sesión #12)

## Enunciado

La clase Java de `inicio.txt` tiene dos errores repetidos:

- a los tres campos (fields: atributos de la clase) les falta el
  modificador `private`, que va al principio de cada línea, justo
  después de la sangría;
- a cuatro sentencias les falta el `;` del final.

Transformala hasta que quede idéntica a `objetivo.txt`.

Reglas:

- Sin flechas y sin mouse. Si te equivocás escribiendo, vale Backspace
  dentro del modo inserción; si te equivocás con un comando, Esc y `u`
  (undo: deshacer).
- Para pasar de una línea a otra usá `j` (abajo) y `k` (arriba).
- Cada vez que entres al modo inserción, que sea con el comando que te
  deja YA en el lugar donde tenés que escribir, sin moverte antes.
- Terminá en modo normal y salí con `:wq` (write + quit: guardar y
  salir) o `:x`.

Par: no tiene.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k01-r1
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k01-r1` otra
vez: arranca de cero.

Si te trabás: revisá la Sesión #12 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean`).

## Entrega

```
/entrega k01-r1
```
