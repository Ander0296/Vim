# KATA k06 — Saltar con f/t y moverse por palabras (cap. 3, 3.5-3.6, Sesión #18)

## Enunciado

La clase `Pedido` de `inicio.txt` tiene 5 errores, todos en el MEDIO
de una línea:

1. en el constructor, `dooble` tiene que decir `double`;
2. en el constructor, `totl` tiene que decir `total`;
3. en `calcularIva`, `0.12` tiene que decir `0.15`;
4. en `resumen`, `" - Totl: "` tiene que decir `" - Total: "`;
5. en `resumen`, `client` tiene que decir `cliente`.

Lo que se entrena: "Find mode" (modo Encontrar: `f`/`F`), "'Til mode"
(modo Hasta: `t`/`T`) y "moving by words" (moverse por palabras: `w`,
`e`, `b`). Llegar al carácter exacto sin caminar letra por letra.

Reglas:

- Dentro de la línea, SOLO `f` / `F` / `t` / `T` (con conteo, y
  repitiendo con la misma letra, con `;` o con `,`) y `w` / `e` / `b` /
  `ge` (con conteo).
- Usá `f`/`F`/`t`/`T` en al menos dos correcciones y `w`/`e`/`b` en al
  menos una.
- En la línea de `resumen`, arreglá PRIMERO `Totl` (el de la derecha) y
  DESPUÉS volvé hacia atrás a `client`.
- Para cambiar de línea: número + `j` / `k`, o un `f`/`t` que te deje
  directo ahí (en LazyVim, `f` sigue buscando en las líneas de abajo).
- No valen: `h`, `l`, flechas, mouse, `s` (flash), `/`, `0`, `^`, `$`,
  `G`, `gg`, ni `Ctrl-d` / `Ctrl-u`.
- Para corregir: `r`, `i`, `a` + Esc. Si te equivocás: Esc y `u`
  (undo: deshacer).
- Terminá en modo normal y salí con `:wq` o `:x`.

Par: ~38 teclas.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k06
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k06` otra vez:
arranca de cero.

Si te trabás: revisá la Sesión #18 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean` ni `nvim-ia`).

## Entrega

```
/entrega k06
```
