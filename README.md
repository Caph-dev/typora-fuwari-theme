# Fuwari Typora Theme

This is a Typora theme inspired by [Fuwari](https://github.com/saicaca/fuwari), a static blog template built with Astro.

The theme ports Fuwari's visual language to Typora as plain CSS:

- soft card-like writing surface
- Fuwari-inspired OKLCH color palette with default hue `250`
- separate fixed light, dark, and light-with-dark-code theme entrypoints
- dashed underline links
- rounded inline code and dark code fences
- rounded images, soft blockquotes, dashed dividers, and highlighted list markers
- basic styling for Typora sidebar, outline, TOC, source mode, tables, task lists, math blocks, and metadata

## Files

- `fuwari-light.css` - fixed light-mode Typora theme. Typora shows this as `Fuwari Light`.
- `fuwari-dark.css` - fixed dark-mode Typora theme. Typora shows this as `Fuwari Dark`.
- `fuwari-light-dark-code.css` - light-mode Typora theme with dark code fences. Typora shows this as `Fuwari Light Dark Code`.
- `fuwari-assets/fuwari-base.css` - shared styles imported by the theme files. Keep this folder next to the CSS files.

## Installation

1. Open Typora.
2. Open the theme folder from `Preferences` -> `Appearance` -> `Open Theme Folder`.
3. Copy these items into that theme folder:
   - `fuwari-light.css`
   - `fuwari-dark.css`
   - `fuwari-light-dark-code.css`
   - `fuwari-assets/`
4. Make sure `fuwari-light.css`, `fuwari-dark.css`, and `fuwari-light-dark-code.css` are directly inside the Typora theme folder. The `fuwari-assets/` folder should also be directly inside that same folder so the imports resolve.
5. Restart Typora.
6. Select `Fuwari Light`, `Fuwari Dark`, or `Fuwari Light Dark Code` from the `Themes` menu.

Typical Typora theme folder on macOS:

```text
/Users/{username}/Library/Application Support/abnerworks.Typora/themes/
```

## Design notes

The CSS is hand-written for Typora instead of copied from Fuwari's Tailwind and Stylus source. It maps the following Fuwari ideas to Typora selectors:

- `#write` becomes a centered article card similar to a Fuwari post body.
- `:root` defines the theme palette and maps it to Typora variables such as `--bg-color`, `--text-color`, `--primary-color`, `--side-bar-bg-color`, and `--monospace`.
- Inline code uses Fuwari-like `--fuwari-inline-code-bg` and `--fuwari-inline-code-color`.
- Code fences use a dark background inspired by Fuwari's Expressive Code examples.
- Links use the dashed underline and soft hover background used by Fuwari posts.

The previous auto-switching single-file theme has been replaced by explicit theme files. This avoids Typora choosing the dark palette automatically because of the operating system color scheme.

No external fonts or images are bundled. If `Roboto` or `JetBrains Mono` is installed locally, Typora will use them automatically; otherwise the CSS falls back to system fonts.

## Compatibility

Typora is based on WebKit on macOS and Chromium on Windows/Linux. This theme uses modern CSS features such as `oklch()`, `color-mix()`, `clamp()`, and `:has()`. Recent Typora versions should render these correctly. If an older version does not support part of the palette, update Typora first.

## Customization

To change the accent color, edit this variable in `fuwari-light.css` and `fuwari-dark.css`. The `fuwari-light-dark-code.css` theme imports `fuwari-light.css`, so it inherits the light theme accent automatically:

```css
:root {
  --hue: 250;
}
```

Examples:

- `200` - teal/cyan
- `250` - Fuwari default blue-violet
- `310` - purple/pink
- `345` - pink/red

## Debugging in Typora

If you want to fine-tune the theme:

1. Enable Typora debug mode.
2. Right-click the element you want to inspect and choose `Inspect Elements`.
3. Adjust palette variables in `fuwari-light.css`, `fuwari-dark.css`, or `fuwari-light-dark-code.css`, and shared selectors in `fuwari-assets/fuwari-base.css`.
4. Restart Typora or switch themes back and forth to reload the CSS.

## Sources referenced

- Fuwari repository: <https://github.com/saicaca/fuwari>
- Fuwari demo: <https://fuwari.vercel.app/posts/expressive-code/>
- Typora custom theme guide: <https://theme.typora.io/doc/Write-Custom-Theme/>
- Typora theme installation guide: <https://theme.typora.io/doc/Install-Theme/>
- Typora style documentation: <https://support.typora.io/style/>
