# KATA k03 — Saltar con flash (cap. 3, 3.1, Sesión #15)

## Enunciado

La clase Java de `inicio.txt` tiene seis errores, cada uno en un lugar
distinto de la pantalla:

1. línea 2: `Strinf` tiene que decir `String`;
2. línea 13: el `+` tiene que ser `*`;
3. línea 16: el `(` del FINAL de la línea tiene que ser `{`;
4. línea 17: el `<` tiene que ser `>`;
5. línea 18: `stoek` tiene que decir `stock`;
6. línea 21: le falta el `;` al final.

Corregilos hasta que quede idéntica a `objetivo.txt`. Lo que se entrena
es CÓMO LLEGÁS a cada error, no el arreglo.

Reglas:

- Para moverte, SOLO flash (`s`, seek: buscar con la vista) y `$`. Nada
  de `h j k l`, flechas, mouse ni `/`.
- Para corregir, SOLO `r` (replace: reemplazar un carácter, sin salir de
  Normal) y `A` (Inserción al final de la línea) + Esc.
- Si te equivocás con un comando: Esc y `u` (undo: deshacer).
- Terminá en modo normal y salí con `:wq` o `:x`.

Par: no tiene (las etiquetas de flash cambian según dónde esté el
cursor al abrir).

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k03
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k03` otra vez:
arranca de cero.

Si te trabás: revisá la Sesión #15 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean`).

## Entrega

```
/entrega k03
```
