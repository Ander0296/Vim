# REPASO k05-r1 — Contar con números relativos (kata k05; cap. 3, 3.3-3.4, Sesión #17)

## Enunciado

La clase `Inventario` de `inicio.txt` tiene 5 errores, en líneas
separadas. Corregilos en el orden que quieras:

1. al atributo `precio` le falta el `;` del final;
2. al `return` de `getCantidad` le falta el `;`;
3. en `agregar`, ARRIBA de `cantidad = cantidad + unidades;`, falta la
   línea `// TODO: validar unidades`, con la misma sangría que la línea
   de abajo;
4. en `quitar`, la condición está al revés: `unidades < cantidad` tiene
   que decir `unidades > cantidad`;
5. al `return` de `valorTotal` le falta el `;`.

Lo que se entrena: "prefixed with a count" (con un conteo adelante).
El número que ves en la columna de la izquierda ES el conteo: lo leés
y tecleás ese número + `j` (abajo) o `k` (arriba). Sin contar líneas a
ojo y sin restar números.

Reglas:

- Para cambiar de línea, SOLO un número + `j` / `k`. Sin número, como
  mucho 2 seguidas: "more than twice in succession" (más de dos veces
  seguidas) ya es desperdicio.
- No valen: flechas, mouse, `s` (flash), `/`, `G`, `gg`, ni `Ctrl-d` /
  `Ctrl-u` / `Ctrl-f` / `Ctrl-b`.
- Si la línea a la que vas no entra en la pantalla: `zz` (acomoda la
  pantalla sin mover el cursor) y después leés el número.
- Dentro de la línea: `f` / `t` (y sus mayúsculas `F` / `T`, hacia
  atrás). Para corregir: `A`, `O` / `o`, `r` + Esc.
- Si te equivocás con un comando: Esc y `u` (undo: deshacer).
- Terminá en modo normal y salí con `:x` (o `:wq`).

Par: ~54 teclas (25 de esas son el texto del comentario).

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata k05-r1
```

Al salir de nvim te dice ✅ o ❌. Con ❌, corré `./kata k05-r1` otra
vez: arranca de cero.

Si te trabás: revisá la Sesión #17 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

Resolvé todo a mano, en tu nvim (la config real de LazyVim, no
`nvim --clean` ni `nvim-ia`).

## Entrega

```
/entrega k05-r1
```
