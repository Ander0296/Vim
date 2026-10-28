# CONCEPTO — el modo Normal como base, `:wq` contra `:x` y el portapapeles (cap. 2, Sesiones #12-#14)

## Enunciado

Son los tres conceptos que quedaron flojos en el examen del cap. 2
(2026-10-28). Es un repaso espaciado: hacelo desde el 2026-11-02, no
antes (al otro día no mide nada).

Respondé abajo, en MI RESPUESTA, con tus palabras y a mano. Escribila
en nvim: de paso practicás Inserción y Normal. Las partes marcadas EN
VIVO se hacen en tu nvim y se anota lo que se vio.

**1. El modo de base.** Un compañero que viene de VS Code te dice:
"Vim es incómodo: cada vez que quiero escribir tengo que apretar `i`
antes". Contestale en 4-6 líneas:

a) por qué en Vim pasás la mayor parte del tiempo en Normal mode (modo
   Normal) y no en Insert mode (modo Inserción);
b) un ejemplo concreto de una edición en código Java donde eso es una
   ventaja.

Regla: en tu respuesta NO podés usar las palabras "normal" ni
"comando".

**2. El mapa de los modos.** Dibujá con flechas de texto
(`A --tecla--> B`) cómo se pasa entre Normal mode (modo Normal), Insert
mode (modo Inserción) y Command mode (modo Comando): con qué tecla se
entra a cada uno, desde cuál, y cómo se vuelve. Después, en una línea:
¿qué te dice ese dibujo sobre el modo Normal?

**3. `:wq` contra `:x`.** Trabajás en un proyecto Java con un programa
que vuelve a correr los tests cada vez que un archivo cambia (un file
watcher: vigilante de archivos). Abrís `App.java` SOLO para leerlo, no
tocás nada, y salís.

a) ¿Qué pasa si salís con `:wq` (write + quit: escribir + salir)? ¿Y
   con `:x`? ¿Por qué?
b) Ahora sí modificaste el archivo: ¿hay alguna diferencia entre los
   dos?
c) ¿A git le importa con cuál de los dos saliste? ¿Por qué?
d) ¿Cuál vas a usar por costumbre, y con qué argumento?

**4. El portapapeles.**

a) ¿Qué es un register (registro) en Vim? Explicalo SIN usar la
   palabra "registro".
b) ¿Qué opción de LazyVim hace que `p` pegue lo que copiaste en el
   navegador con Ctrl-c, y con qué valor? EN VIVO: ¿con qué comando
   ves ese valor en TU nvim? Corrélo y anotá lo que muestra.
c) EN VIVO: abrí `nvim --clean`, NO copies ni borres nada, y apretá
   `p` en modo Normal. Anotá el mensaje que aparece abajo, tal cual, y
   explicá qué significa y por qué en tu nvim de siempre no habría
   pasado lo mismo.

Si te trabás: revisá las Sesiones #12, #13 y #14 de GUIA.md

## MI RESPUESTA

---

PROMPT DE ENTREGA (copiá esto y pegalo en Claude cuando termines):

```
/entrega lib01 "normal, :x y portapapeles" — mi respuesta está en ejercicios/lib01-normal-x-portapapeles.md
```
