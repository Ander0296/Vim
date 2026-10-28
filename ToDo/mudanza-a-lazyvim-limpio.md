# Mudanza a un LazyVim limpio (la config vieja pasa a `nvim-ia`)

Para pasar de una config de Neovim existente a un LazyVim limpio SIN
perder la vieja: la vieja queda como secundaria (se abre con
`NVIM_APPNAME=nvim-ia nvim`) y la nueva pasa a ser `nvim`.

Por qué se mueven CUATRO carpetas y no solo la config: Neovim guarda
cosas en cuatro lugares, y `NVIM_APPNAME` cambia el nombre de las
cuatro a la vez.

| Carpeta | Qué guarda |
| --- | --- |
| `~/.config/nvim` | la config: `init.lua`, `lua/` |
| `~/.local/share/nvim` | datos: plugins (`lazy/`) y herramientas de Mason (`mason/`: jdtls, debug, tests) |
| `~/.local/state/nvim` | estado: historial (`shada`), `undo`, `swap`, sesiones, logs |
| `~/.cache/nvim` | caché: se puede regenerar (ej. el workspace de jdtls) |

## A. En el PC donde se hace la mudanza

- [ ] Cerrá TODOS los nvim abiertos (todas las terminales, tmux, zellij).
      Por qué: un nvim abierto sigue escribiendo `swap` y `shada` en las
      carpetas viejas mientras las movés.
- [ ] Confirmá que `~/.config/nvim-ia` NO existe: `eza -d ~/.config/nvim-ia`
      tiene que dar error. Por qué: si ya existe, `mv` mete la carpeta
      ADENTRO de ella en vez de renombrarla.
- [ ] Corré los `mv` UNA sola vez. Si algo se cortó a mitad, NO repitas
      el bloque entero: mirá con `eza -d` qué carpetas ya se movieron y
      seguí desde el paso que falta. Por qué: ya pasó — la segunda
      corrida metió el starter recién clonado en `~/.config/nvim-ia/nvim`
      y un estado nuevo en `~/.local/state/nvim-ia/nvim`.
- [ ] Mové las cuatro carpetas (`mv`, nunca `rm -rf`):
      ```
      mv ~/.config/nvim      ~/.config/nvim-ia
      mv ~/.local/share/nvim ~/.local/share/nvim-ia
      mv ~/.local/state/nvim ~/.local/state/nvim-ia
      mv ~/.cache/nvim       ~/.cache/nvim-ia
      ```
- [ ] Probá la vieja: `NVIM_APPNAME=nvim-ia nvim` abre igual que antes y
      NO descarga plugins. Si descarga todo, faltó mover
      `~/.local/share/nvim`.
- [ ] Cloná el starter (plantilla de arranque):
      `git clone https://github.com/LazyVim/starter ~/.config/nvim`
- [ ] Borrá SU `.git`: `rm -rf ~/.config/nvim/.git`. Leé la ruta dos
      veces antes del Enter: tiene que terminar en `/nvim/.git`.
      Por qué: si `~/.config` es un repo de dotfiles, un `.git` adentro
      de `nvim/` lo vuelve un repo anidado y el de dotfiles deja de
      guardar sus archivos.
- [ ] Verificá: `eza -a ~/.config/nvim` NO muestra `.git`.
- [ ] Commit de la mudanza desde la raíz del repo de dotfiles
      (`~/.config`), con el flujo de ese repo.

## B. En otro PC que recibe esos dotfiles por git

El `git pull` de dotfiles trae `~/.config/nvim` (nueva). `nvim-ia` vive
solo en el PC de origen, como consulta: el `.gitignore` de `~/.config`
es lista blanca y no tiene `!/nvim-ia`. Las otras tres carpetas nunca
viajan: son locales de cada PC.

- [ ] ANTES del `git pull` de dotfiles (o como mucho antes de abrir
      nvim): cerrá todos los nvim y apartá las tres carpetas locales
      viejas (o borralas si no las querés):
      ```
      mv ~/.local/share/nvim ~/.local/share/nvim-viejo
      mv ~/.local/state/nvim ~/.local/state/nvim-viejo
      mv ~/.cache/nvim       ~/.cache/nvim-viejo
      ```
      Por qué: si no, el LazyVim nuevo arranca con los plugins y el
      estado de la config vieja.
- [ ] Abrí `nvim`: su primer arranque descarga sus plugins. Después,
      `<leader>l` → `R` para quedar en las versiones del `lazy-lock.json`.

## Trampas conocidas

- Un `.gitignore` de lista blanca (empieza con `/*`) deja afuera, sin
  avisar, toda carpeta nueva o renombrada hasta que se le agrega su
  línea `!/nombre`.
- `mv a b` con `b` ya existente NO renombra: mete `a` adentro de `b`.
  Señal de que pasó: aparece una carpeta `nvim/` adentro de alguna
  `nvim-ia/` (revisá las cuatro con `eza -a`).
- `alias v nvim` y `EDITOR=nvim` (fish) abren la config NUEVA, que no
  trae los extras de Java hasta activarlos. Para programar Java mientras
  tanto (solo en el PC de origen): `NVIM_APPNAME=nvim-ia nvim`.
- Lo que vivía dentro de `~/.config/nvim` (ej. su `CLAUDE.md` o
  `guia.txt`) se muda con la carpeta: queda en `~/.config/nvim-ia`.
