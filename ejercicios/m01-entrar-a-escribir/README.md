# m01 — Entrar a escribir (kata mixta)

## Enunciado

Esta clase no compila. Dejala idéntica a `objetivo.txt`:

1. Arriba de todo falta la línea `package banco;` (pegada a la clase,
   sin línea vacía en el medio).
2. Al campo `saldo` le falta `private` adelante.
3. A `movimientos` le falta el `;` del final.
4. En `depositar`, debajo de la suma al saldo, falta la línea
   `movimientos++;`.
5. La última línea cierra la clase con `)` en vez de `}`.

Kata mixta: no te digo qué comando va en cada cambio. Elegí vos; el par
te dice si había un camino más corto.

Par: 56 teclas (todas, incluido el `:x` y el Enter para salir).

Única regla: sin flechas ni mouse.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata m01
```

Al salir te dice ✅ o ❌ y cuántas teclas usaste contra el par. Con ❌,
corré `./kata m01` otra vez: arranca de cero.

Si te trabás: revisá las Sesiones #12, #13, #17 y #19 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

## Entrega

```
/entrega m01
```
