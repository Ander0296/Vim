# MECANOGRAFÍA — líneas de comandos de Vim (ttyper)

En este proyecto no se tipean frases: se tipean COMANDOS DE VIM de lo
que estudio, para que la gramática quede en los dedos (en dvorak). Las
agrega Claude al cerrar cada tanda (1-2 líneas por sesión, cortas:
8-14 tokens).

Cada línea vive además en su propio archivo de ttyper, aplanada a un
token por línea:
`~/.config/ttyper/texts/vim-sNN.txt` (si la sesión tiene dos líneas:
`vim-sNNa.txt` y `vim-sNNb.txt`)

Atajo del sistema para practicar: **CTRL+SUPER+ALT+T**

Solo van comandos que se tipean tal cual (letras, símbolos, `:` + Ex).
Esc, Ctrl y `<leader>` no se pueden escribir en ttyper.

Las líneas NO se editan después: son material de repaso. Si un concepto
cambia, se agrega una línea nueva.

# ============================================================
# LÍNEAS POR SESIÓN
# ============================================================

s01 — por qué Vim: lo que va después de `:` son comandos de ex:
`:w :q :wq :q! :help :Lazy :s/vi/vim/ :s/ed/ex/`

s02 — Neovim, Lua y LazyVim: el mismo "hola" en Lua y en VimScript:
`:lua print("hola") :echo "hola" :Lazy :help lua-guide :s/vim/nvim/ :wq`

s03 — la terminal: en qué terminal corre nvim (repaso de lo anterior):
`:echo $TERM :echo "kitty" :lua print("gpu") :w :q :wq :q! :s/vi/vim/`
