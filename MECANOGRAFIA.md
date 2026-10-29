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

s04 — la fuente: probar que la terminal dibuja los íconos de una Nerd Font:
`:echo "" :echo $TERM :lua print("nerd") :echo "font" :w :q :wq :q!`

s05 — instalar Neovim: chequear versión y requisitos desde adentro:
`:checkhealth lazyvim :checkhealth nvim-treesitter :version :echo "" :w :q :wq :q!`

s06 — Neovim pelado y cómo salir (con y sin forzar):
`nvim --clean :Tutor :q! :qa :qa! :wq :w :q :Tutor :q!`

s07 — instalar LazyVim: abrir otra config, las dependencias y el chequeo:
`NVIM_APPNAME=nvim-ia nvim git clone mv lazygit rg fd :checkhealth lazyvim :q!`

s08 — primer arranque y dashboard: Lazy, los extras y salir:
`:Lazy :LazyExtras :qa :enew :checkhealth lazyvim :Lazy G q :qa :LazyExtras`

s09 — lazy.nvim: abrir, chequear, sincronizar, ver el log, restaurar y cerrar:
`:Lazy C S q :Lazy L q :Lazy R q :Lazy P q`

s10 — dotfiles: el repo de la config, la lista blanca y restaurar en el otro PC:
`.gitignore !/nvim /* ~/.config/nvim git pull :Lazy R q eza -a ~/.gitconfig`

s11 — menú de Espacio: which-key y lo que hay debajo de los splits y del otro buffer:
`:WhichKey :sp :vs :q :e# :Lazy q :WhichKey :e# :sp :vs :qa`

s12 — modos Inserción y Normal: entrar en el lugar justo, put y salir; el `n` del dashboard:
`i a I A gI p u :wq A I a i gI :q!`
`:enew :startinsert :checkhealth :WhichKey :wq :q! i a I A`

s13 — abrir líneas arriba y abajo, volver a la última inserción:
`o O gi o O gi I A i a :wq :q!`

s14 — modo Comando: guardar, salir, abrir archivos y la ayuda:
`:w :q :wq :x :q! :e :help :qall :x :w`
`:write :w :quit :q :edit :e :help :x :wq`

s15 — flash: saltar a lo que ves, reemplazar un carácter y llegar al final de la línea:
`s rx $ A r* $r{ A; r> rc :x`

s16 — desplazar la pantalla: el menú `z` para ubicar la línea del cursor:
`zt zz zb zt0 zz0 zb0 z. z- zs ze zH zL`

s17 — conteos y números relativos: número + `j`/`k` para cambiar de línea, y la opción escrita en Lua:
`15k 5l 5j 12k 3j 7k 20j vim.opt.relativenumber=false vim.opt.number=false`

s18 — `f`/`t` y palabras: saltar a un carácter, repetir el salto y moverse por palabras:
`fs 3fs Fs 2Ft t) T( d2ts 3w 3e 2b 4ge be ; ,`
