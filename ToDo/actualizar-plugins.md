# Actualizar los plugins de LazyVim (lazy.nvim)

Cuándo usarlo: cuando abajo a la derecha de la barra de estado aparece
un ícono con un número (= plugins con actualización disponible).

## En este PC

- [ ] Hay un número abajo a la derecha de la barra de estado. Por qué
      no hay aviso emergente: el starter de LazyVim trae
      `notify = false` en `~/.config/nvim/lua/config/lazy.lua`.
- [ ] `git status` en `~/.config` está limpio ANTES de actualizar. Por
      qué: si la actualización rompe algo, se vuelve al
      `lazy-lock.json` del último commit.
- [ ] Abajo a la izquierda dice NORMAL (si no, Esc).
- [ ] `<leader>l` (Espacio, después `l`) o `:Lazy` → se abre la ventana
      de lazy.nvim.
- [ ] (Opcional) En la lista "Updates", buscar un `!` después del tipo
      (`feat!:`) o la palabra BREAKING: avisan cambios que pueden romper
      algo.
- [ ] `S` (Sync) en MAYÚSCULA y esperar a que termine. Todas las teclas
      de esa ventana van con Shift.
- [ ] `q` cierra la ventana.
- [ ] Salir (`:qa`), abrir nvim de nuevo y correr `:checkhealth
      lazyvim`: sin errores nuevos.
- [ ] `git status` en `~/.config` muestra `nvim/lazy-lock.json`
      modificado → commitearlo. Si no aparece nunca, el lockfile está
      ignorado por git: conviene versionarlo.

## Si algo se rompió

- [ ] Volver `nvim/lazy-lock.json` a la versión anterior con git (en
      `~/.config`).
- [ ] `<leader>l` → `R` (Restore): baja los plugins a las versiones del
      lockfile.

## En el otro PC (después de traer los dotfiles con `git pull`)

- [ ] `<leader>l` → `R` (Restore), NO `S`. Por qué: `S` actualiza a lo
      último y reescribe el lockfile, y los dos PCs quedan con
      versiones distintas; `R` instala exactamente las versiones
      commiteadas.

## Trampas

| Confusión | Realidad |
| --- | --- |
| `S` = "save" (guardar) | `S` = Sync: install + clean + update |
| lazy.nvim = LazyVim | lazy.nvim es solo el gestor de plugins; LazyVim es la distribución (plugins + config) que lo trae |
| Esperar un aviso emergente al abrir | El starter de LazyVim 16 lo apaga: el aviso es el número de la barra de estado |
| `S` en el otro PC "para ponerlo al día" | Eso actualiza de más; para copiar las versiones del lockfile es `R` |
