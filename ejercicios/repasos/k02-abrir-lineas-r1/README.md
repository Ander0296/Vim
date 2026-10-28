# REPASO k02-r1 — Abrir líneas (kata k02; cap. 2, 2.1.1, Sesión #13)

## Enunciado

A la clase Java de `inicio.txt` le faltan cuatro líneas COMPLETAS:

- un segundo campo (field: atributo de la clase), `private int vueltas;`,
  debajo de `private int cuenta;`;
- un comentario arriba de cada método: `// Suma uno a la cuenta.` y
  `// Vuelve la cuenta a cero.`;
- la sentencia `vueltas++;` debajo de `cuenta = 0;`.

Transformala hasta que quede idéntica a `objetivo.txt`.

Reglas:

- Sin flechas y sin mouse. Si te equivocás escribiendo, vale Backspace
  dentro del modo inserción; si te equivocás con un comando, Esc y `u`
  (undo: deshacer).
- Para pasar de una línea a otra usá `j` (abajo) y `k` (arriba).
- Cada línea nueva se crea con un solo comando que la abre Y te deja
  escribiendo en ella: nada de ir al final de otra línea y apretar
  Enter.
- Ojo con la sangría: antes de tipear espacios, mirá dónde quedó el
  cursor.
- Terminá en modo normal y salí con `:wq` o `:x`.

Par: no tiene.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k02-r1
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k02-r1` otra
vez: arranca de cero.

Si te trabás: revisá la Sesión #13 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean`).

## Entrega

```
/entrega k02-r1
```
