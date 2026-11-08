# Yami Midnight

Midnight Discord theme in [yami](https://github.com/Trendorin/yami) palette colors — dark, minimal, generated from your wallpaper.

## Preview

![Yami Midnight — palette](assets/preview-yami-midnight.png)

![Yami Midnight — chat](assets/preview-chat.png)

![Yami Midnight — settings](assets/preview-settings.png)

## Install

In BetterDiscord / Equicord / Vencord / Equibop add the theme by URL:

```
https://raw.githubusercontent.com/Minish777/yami-midnight/master/themes/flavors/yami.theme.css
```

Theme: `themes/flavors/yami.theme.css`. DM icon is the yami logo (`assets/yami-logo.svg`).
Layout modules come from the original [Midnight](https://github.com/refact0r/midnight-discord) build.

## Dynamic version (changes with your wallpaper)

A Discord theme file is static CSS — it cannot recolor itself when the wallpaper changes.
The dynamic version lives locally and is generated from yami's wallpaper palette:

1. Install yami and enable the wallpaper palette:
   ```sh
   yami palette wallpaper
   ```
   The accent and the whole palette now follow your wallpaper automatically.

2. Add the client template at `~/.config/yami/templates/equibop` (Midnight structure
   with palette placeholders + output line):

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
   (`.strip` = without `#`, `.rgb` = `r, g, b`). The `yami-output:` line must point under
   `~/.config`, `~/.local/share` or `~/.cache`.

3. Render and enable:
   ```sh
   yami templates        # shows per-template status
   # change the wallpaper — the theme recolors itself
   ```
   Then enable the generated theme in your client (Equibop: Settings → Themes).

## Regenerating this snapshot

Copy your rendered `~/.config/equibop/themes/yami.theme.css` colors into
`themes/flavors/yami.theme.css` (keep the Midnight `@import` and options), commit, done.

## Credits

- [Midnight](https://github.com/refact0r/midnight-discord) by refact0r — base theme, layout modules, options
- [yami](https://github.com/Trendorin/yami) — palette generation and template system
- Yami Midnight flavor, logo usage and guides — Minish777

---

## Русский перевод

Midnight-тема Discord в цветах палитры [yami](https://github.com/Trendorin/yami) — тёмная, минималистичная, генерируется из обоев.

### Установка

В BetterDiscord / Equicord / Vencord / Equibop добавьте тему по ссылке:

```
https://raw.githubusercontent.com/Minish777/yami-midnight/master/themes/flavors/yami.theme.css
```

Тема: `themes/flavors/yami.theme.css`. Иконка личных сообщений — логотип yami (`assets/yami-logo.svg`). Модули раскладки — из оригинальной сборки [Midnight](https://github.com/refact0r/midnight-discord).

### Динамическая версия (меняется с обоями)

Файл темы Discord — статичный CSS, сам он не перекрасится при смене обоев. Динамическая версия живёт локально и генерируется из палитры обоев yami:

1. Установите yami и включите палитру из обоев: `yami palette wallpaper` — акцент и вся палитра следуют за обоями автоматически.
2. Добавьте шаблон клиента в `~/.config/yami/templates/equibop` (структура Midnight с плейсхолдерами палитры + строка `yami-output:`).
3. Отрисуйте: `yami templates`, затем включите сгенерированную тему в клиенте (Equibop: Настройки → Темы). Смените обои — тема перекрасится сама.

### credits

- [Midnight](https://github.com/refact0r/midnight-discord) от refact0r — базовая тема, модули раскладки, опции
- [yami](https://github.com/Trendorin/yami) — генерация палитры и система шаблонов
- Yami Midnight flavor, использование логотипа и гайды — Minish777
