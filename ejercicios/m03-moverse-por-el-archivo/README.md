# m03 — Moverse por el archivo (kata mixta)

## Enunciado

El archivo es largo: no entra entero en la pantalla. Tiene cuatro
errores. Dejalo idéntico a `objetivo.txt`.

Dos los encontró el compilador:

```
Biblioteca.java:4: error: class Bibloteca is public, should be declared in a file named Bibloteca.java
Biblioteca.java:36: error: ';' expected
```

(1: "la clase `Bibloteca` es pública, tendría que estar declarada en un
archivo llamado `Bibloteca.java`" → el nombre tiene que ser
`Biblioteca`, como el archivo. 2: "se esperaba `;`" → falta el `;` al
final de esa línea.)

Los otros dos no los ve el compilador, los vas a tener que encontrar
vos:

3. `disponibles()` cuenta los libros prestados en vez de los
   disponibles: a la condición del `if` le falta un `!` (no) adelante
   de `prestado`.
4. En `main`, el segundo título está mal escrito: tiene que ser
   `Rayuela`, igual que en la línea que lo presta.

Kata mixta: no te digo qué comando va en cada cambio. Elegí vos; el par
te dice si había un camino más corto.

Par: ~31 teclas (todas, incluido el `:x` y el Enter para salir; puede
variar en una o dos según el alto de tu terminal).

Única regla: sin flechas ni mouse.

## Cómo se corre (desde `~/Proyectos/Vim`)

```
./kata m03
```

Al salir te dice ✅ o ❌ y cuántas teclas usaste contra el par. Con ❌,
corré `./kata m03` otra vez: arranca de cero.

Si te trabás: revisá las Sesiones #15, #16, #17 y #19 de GUIA.md
Checklist: ToDo/hacer-una-kata.md

## Entrega

```
/entrega m03
```
