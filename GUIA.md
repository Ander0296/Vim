# GUÍA: Neovim + LazyVim con foco en Java — "LazyVim for Ambitious Developers" (Dusty Phillips); en F2, "Practical Vim" (Drew Neil)

No asume conocimiento previo — la mantiene Claude Code sesión a
sesión. Cada sesión cubre una tanda del material (acá: un rango de
secciones de un capítulo, ~250-400 líneas de texto; 3-5 imágenes si
vino como pantallazos), explicada en español y conectada con práctica
hecha a mano.
Prácticas: ver EJERCICIOS.md.

## INICIO RÁPIDO

- Último punto estudiado: ninguno todavía — arrancamos en el cap. 1 (Sesión #01)
- Última tanda: ninguna todavía (las tandas se numeran "Sesión #NN")
- PRÓXIMA SESIÓN: `/rename nvim-s01`
  (el nombre de la sesión de Claude sale SIEMPRE de esta línea, no se
  calcula: es un contador distinto al de las tandas, porque una sesión
  de Claude puede cubrir 2-3 tandas. Claude la actualiza al cerrar.)
- Prácticas pendientes: ninguna todavía — esta línea lista SOLO lo
  pendiente (nombres, sin historial); estados completos, fechas y
  repasos viven en EJERCICIOS.md (fuente de verdad)
- Último triage (`/pendientes`): nunca todavía
- Último examen (`/examen`): nunca todavía
- Entorno verificado: 2026-10-27 — NVIM v0.12.5, LazyVim 16.0.0, jdtls + java-debug-adapter + java-test (Mason), openjdk 26, Maven 3.9.16, pandoc 3.10.2, ttyper 1.6.0

## VOCABULARIO (solo si el material está en otro idioma; una fila por término nuevo)

| Original (inglés)                    | Español | En una frase |
| ------------------------------------ | ------- | ------------ |
| (se llena a partir de la sesión #01) | —       | —            |

============================================================
(ACÁ VAN LAS SESIONES — Claude agrega la SESIÓN #01 en la primera
clase y sigue numerando hacia abajo, una sección por sesión, usando
el formato CORTO de referencia del final del archivo. Cuando este
archivo supere ~500 líneas, Claude mueve las sesiones viejas a
GUIA-ARCHIVO.md — ver la regla en CLAUDE.md.)
============================================================

# ============================================================
# FORMATO DE CADA SESIÓN (referencia para Claude — copiar y llenar)
# Formato CORTO obligatorio: 5-8 bullets, SIN bloques de código ni
# contenido repetido del chat (eso ya vive en el chat, el material y
# los archivos de práctica). Sin narrar las dudas (tema + veredicto
# en una línea). Máximo ~15 líneas por sesión.
# ============================================================

SESIÓN #NN — [fecha] — [tema] (cap. N, secciones N.M-N.P, % avance)
- [idea clave 1, una línea]
- [idea clave 2...]
- Ejercicios de la tanda: [nombre + pendiente/completado, o "ninguno"]
- Nota del profe: [solo si la hubo, una línea — ej. libro vs LazyVim 16]
- Config tocada: [solo si la hubo: archivo de ~/.config/nvim y qué se cambió]
- Dudas: [tema + bien/corregido en una línea, o "ninguna"]
- PRÁCTICAS CREADAS: [kNN/jNN/libNN o "ninguna"]
- PRÓXIMO PASO: [una línea]
