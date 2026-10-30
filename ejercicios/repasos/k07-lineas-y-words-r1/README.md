# REPASO k07-r1 — Saltar a una línea, a sus extremos y por WORDS (kata k07; cap. 3, 3.7-3.9, Sesión #19)

## Enunciado

Compilaste `Inventario` (es `inicio.txt`) y el compilador te devolvió
esto. Arreglá cada cosa EN ESTE ORDEN, del 1 al 6:

1. `Inventario.java:6: error: cannot find symbol — variable
   UnidadesEnStock` ("no se encuentra el símbolo — variable
   UnidadesEnStock"): la variable es `unidadesEnStock`, con minúscula.
2. `Inventario.java:6: error: ')' expected` ("se esperaba un `)`"): a
   `stock.size(` le falta su `)`.
3. `Inventario.java:12: error: ';' expected` ("se esperaba un `;`"): la
   línea termina en `:` y tiene que terminar en `;`.
4. `Inventario.java:16: error: cannot find symbol — class Return` ("no
   se encuentra el símbolo — clase Return"): es `return`, con
   minúscula.
5. Sin error, pero el `System.out.println` de la línea 10 es de debug:
   comentalo con `//` en la COLUMNA 0, antes de la sangría (como lo
   hace IntelliJ), no pegado al texto.
6. `Inventario.java:1: error: class inventario is public, should be
   declared in a file named inventario.java` ("la clase inventario es
   pública: tendría que estar en un archivo llamado inventario.java"):
   la clase se tiene que llamar `Inventario`, con mayúscula.

Lo que se entrena: "Moving by Words, Only BIGGER" (moverse por
palabras, solo que más grandes: `W`, `B`, `E`, `gE`), "Line Targets"
(destinos en la línea: `0`, `^`, `$`, `g_`) y "Jumping to Specific
Lines" (saltar a una línea concreta: número + `G`, `gg`, `G`).

Reglas:

- Para cambiar de línea, SOLO número + `G` (o `:número` + Enter), `gg`
  y `G`. El número es el del mensaje del compilador, no el de la
  columna de números relativos.
- Dentro de la línea, SOLO `0`, `^`, `$`, `g_` y `W` / `B` / `E` / `gE`
  (con conteo).
- OBLIGATORIO: `0`, `^` y `$` al menos una vez cada uno; `W` / `B` /
  `E` / `gE` en al menos una corrección; `gg` para el arreglo 6.
- No valen: `h`, `j`, `k`, `l`, flechas, mouse, `w` / `e` / `b` / `ge`
  (las minúsculas: hoy van las grandes), `f` / `t` / `F` / `T`, `;`,
  `,`, `s` (flash), `/`, `Ctrl-d` / `Ctrl-u`, ni `I` / `A` (hoy se
  llega en modo Normal).
- Para corregir: `r`, `i`, `a` + Esc. Si te equivocás: Esc y `u`
  (undo: deshacer).
- Terminá en modo normal y salí con `:x` o `:wq`.

Par: ~40 teclas.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k07-r1
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k07-r1` otra
vez: arranca de cero.

Si te trabás: revisá la Sesión #19 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean` ni `nvim-ia`).

## Entrega

```
/entrega k07-r1
```

Con una línea por arreglo: qué teclas usaste y por qué esas.
