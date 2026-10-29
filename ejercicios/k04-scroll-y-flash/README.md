# KATA k04 — Desplazar la pantalla y saltar con flash (cap. 3, 3.2, Sesión #16)

## Enunciado

La clase Java de `inicio.txt` es LARGA (181 líneas): los errores no
entran todos en la pantalla. Corregilos EN ESTE ORDEN:

1. arriba de todo, en los `import`: `Lisr` tiene que decir `List`;
2. en el método `buscarPorAutor` (por la mitad del archivo): `retirn`
   tiene que decir `return`;
3. en `promedioPorSocio`, el último método: al `return` le falta el `;`
   del final;
4. volviendo para arriba, en `obtenerPorTitulo`: el texto
   `"Libro no encontrsdo: "` tiene que decir `encontrado`.

Lo que se entrena: "You can't label something you can't see!" (¡no
podés etiquetar lo que no ves!). Primero traés el objetivo a la
pantalla desplazándola (scroll); recién ahí saltás con flash.

Reglas:

- Para moverte, SOLO: `Ctrl-d` / `Ctrl-u` (media pantalla), `Ctrl-f` /
  `Ctrl-b` (pantalla entera), `Ctrl-e` / `Ctrl-y` (una línea), `zt` /
  `zz` / `zb`, `s` (flash) y `$`.
- No valen: `h j k l` (con o sin número), `G`, `gg`, `/`, `f`/`t`,
  flechas, RePág/AvPág, ni el mouse o su rueda.
- Para corregir, SOLO `r` (replace: reemplazar un carácter) y `A`
  (Inserción al final de la línea) + Esc.
- Si te equivocás con un comando: Esc y `u` (undo: deshacer).
- Terminá en modo normal y salí con `:wq` o `:x`.

Par: no tiene (depende de cuántas líneas entran en tu terminal).

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k04
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k04` otra vez:
arranca de cero.

Si te trabás: revisá la Sesión #16 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean` ni `nvim-ia`).

## Entrega

```
/entrega k04
```
