# KATA k02 — Abrir líneas (cap. 2, 2.1.1, Sesión #13)

## Enunciado

A la clase Java de `inicio.txt` le faltan cuatro líneas COMPLETAS:

- un segundo campo (field: atributo de la clase), `private int vueltas;`,
  debajo de `private int cuenta;`;
- un comentario arriba de cada método: `// Suma uno a la cuenta.` y
  `// Vuelve la cuenta a cero.`;
- la sentencia `vueltas++;` debajo de `cuenta = 0;`.

Transformá `trabajo.txt` (una copia de `inicio.txt`) hasta que quede
idéntico a `objetivo.txt`.

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
- Terminá en modo normal y salí con `:wq`.

Par: no tiene (todavía estamos calibrando).

## Comandos (desde la carpeta de la kata)

```
cd ~/Proyectos/Vim/ejercicios/k02-abrir-lineas
cp inicio.txt trabajo.txt
nvim -W teclas.log trabajo.txt
diff -u trabajo.txt objetivo.txt
```

Si `diff` no muestra nada, salió. Si muestra líneas, se rehace TODO
desde el `cp`.

Si te trabás: revisá la Sesión #13 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean`).

## MI EXPLICACIÓN

(qué hace cada comando que usaste y por qué lo elegiste)

---

PROMPT DE ENTREGA (copiá esto y pegalo en Claude cuando termines):

```
/entrega k02 "abrir líneas" — mi trabajo está en ejercicios/k02-abrir-lineas/ (trabajo.txt, teclas.log y MI EXPLICACIÓN en el README)
```
