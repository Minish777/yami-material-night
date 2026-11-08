# Yami Midnight

Midnight Discord theme in [yami](https://github.com/Trendorin/yami) palette colors.
Static snapshot: `themes/flavors/yami.theme.css` — install by URL in BetterDiscord / Equicord / Vencord / Equibop:

```
https://raw.githubusercontent.com/Minish777/yami-midnight/master/themes/flavors/yami.theme.css
```

DM icon is the yami logo (`assets/yami-logo.svg`). Theme modules (layout) come from the original Midnight build.

## Dynamic version (changes with your wallpaper)

A Discord theme file is static CSS — it cannot recolor itself when the wallpaper changes.
The dynamic version lives **locally** and is generated from yami's wallpaper palette:

### 1. Install yami and enable the wallpaper palette
```sh
# install yami (see https://github.com/Trendorin/yami), then in a terminal:
yami palette wallpaper
```
Now the accent (and the whole palette) follows your wallpaper automatically.

### 2. Add the Equibop/Equicord template
Create `~/.config/yami/templates/equibop` with Midnight structure and palette placeholders,
e.g. (color section only — full template = Midnight theme with `{{accent}}` etc.):

```css
/* yami-output: ~/.config/equibop/themes/yami.theme.css */
@import url('https://refact0r.github.io/midnight-discord/build/midnight.css');
/* ... Midnight options ... */
:root {
  --colors: on;
  --bg-4: {{bg}};
  --text-1: {{text}};
  --accent-1: {{accent}};
  --accent-2: {{deep}};
  /* ... */
}
```

Placeholders: `{{accent}}`, `{{deep}}`, `{{bright}}`, `{{bg}}`, `{{panel}}`, `{{surface}}`,
`{{border}}`, `{{text}}`, `{{textDim}}`, `{{textFaint}}`, `{{color0}}`–`{{color15}}`
(`.strip` = without `#`, `.rgb` = `r, g, b`).
The `yami-output:` line says where to write the rendered file (must be under
`~/.config`, `~/.local/share` or `~/.cache`).

### 3. Render + enable
```sh
# yami renders templates on every palette/wallpaper change automatically;
# force a render now:
python3 ~/.local/share/yami/src/tools/theme.py
# or: yami templates   (shows per-template status)
```
Then enable the generated theme in your client (Equibop: Settings → Themes → `yami.theme.css`).
Change the wallpaper — the theme recolors itself.

## Regenerating this static snapshot
Copy your rendered `~/.config/equibop/themes/yami.theme.css` colors into
`themes/flavors/yami.theme.css` (keep the Midnight `@import` and options), commit, done.
