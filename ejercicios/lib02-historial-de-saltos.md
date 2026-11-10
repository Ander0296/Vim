# LIBRO — Historial de saltos: qué deja miga y adónde vuelve `Ctrl-o` (cap. 3, sección 3.10, Sesión #20)

## Enunciado

Respondé abajo, en MI RESPUESTA, con tus palabras y a mano (escribila
en nvim: de paso practicás). La pregunta 3 es EN VIVO: se hace en tu
nvim y se anota lo que se vio.

1. Para cada movimiento, decí si deja la posición de partida en el
   "jump history" (historial de saltos) o no: `G`, `42G`, `:42` +
   Enter, `15j`, `3w`, `fa`, `s` (flash), `Ctrl-d`.
   Después, en una o dos líneas: ¿qué tienen en común los que SÍ la
   dejan?

2. Suponé que el historial arranca vacío. Archivo de 100 líneas, cursor
   en la línea 10. Tipeás, en este orden: `70G`, `10j`, `gg`, `5G`.
   a) Apretás `Ctrl-o` cuatro veces seguidas. ¿En qué línea quedás
      después de cada una?
   b) Desde ahí, `Ctrl-i` dos veces. ¿En qué línea quedás después de
      cada una?
   c) ¿Por qué la línea 70 no aparece nunca?

3. EN VIVO. Abrí nvim con cualquier archivo y, antes de mover nada,
   apretá `Ctrl-o`. Anotá qué pasó. ¿Por qué puede pasar eso? ¿Con qué
   tecla volvés adonde estabas?

4. Estás en la línea 240 arreglando un método. Subís con `3G`, agregás
   un import con `o` y apretás Esc. Para volver al método tenés dos
   opciones: `240G` o `Ctrl-o`. ¿Cuál te deja en tu método, y por qué
   la otra no?

Si te trabás: revisá la Sesión #20 de GUIA.md

## MI RESPUESTA
G = Si
42G = Si
:42  + enter = no
15j no
3w no
fa no
s (flash) si
control d no

2. Supongo que en la primera, da un salto de más que no se guardó o no se tiene conocimiento
b. queda en la linea 80
la linea 70 no aparece nunca porque se hizo el salto desde la linea 80, 10j no crea migas.

3. Me envía a la última miga así esté en otro archivo, control i me devuelve a donde estaba

La que me deja en el método es la control o, 240G no sirve porque se ha agregado una linea, el método baja una linea y ya deja de estar en la 240



---

PROMPT DE ENTREGA (copiá esto y pegalo en Claude cuando termines):

```
/entrega lib02 "historial de saltos" — mi respuesta está en ejercicios/lib02-historial-de-saltos.md
```
