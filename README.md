# Fuwari Typora Theme

[中文版本](README_zh.md)

This is a Typora theme inspired by [Fuwari](https://github.com/saicaca/fuwari), a static blog template built with Astro.

The theme ports Fuwari's visual language to Typora as plain CSS:

- soft card-like writing surface
- Fuwari-inspired OKLCH color palette with default hue `250`
- fixed light-mode theme
- dashed underline links
- rounded inline code and light code fences
- rounded images, soft blockquotes, dashed dividers, and highlighted list markers
- basic styling for Typora sidebar, outline, TOC, source mode, tables, task lists, math blocks, and metadata

## Files

- `fuwari-light.css` - fixed light-mode Typora theme. Typora shows this as `Fuwari Light`.
- `fuwari-assets/fuwari-base.css` - shared styles imported by the theme file. Keep this folder next to the CSS file.

## Installation

### From Release (recommended)

1. Download `fuwari-light-v1.0.0.zip` from [Releases](https://github.com/Caph-dev/typora-fuwari-theme/releases/tag/v1.0.0).
2. Open Typora → `Preferences` → `Appearance` → `Open Theme Folder`.
3. Extract the zip and copy `fuwari-light.css` and `fuwari-assets/` into the theme folder.
4. Restart Typora and select `Fuwari Light` from the `Themes` menu.

### From source

Clone or download this repository, then copy `fuwari-light.css` and `fuwari-assets/` into the Typora theme folder.

Typical Typora theme folder on macOS:

```text
/Users/{username}/Library/Application Support/abnerworks.Typora/themes/
```

## Recommended fonts

The theme works with system fonts out of the box. Install the following fonts locally for the best experience:

| Role | Font | Link |
| --- | --- | --- |
| Body text | Roboto | <https://fonts.google.com/specimen/Roboto> |
| Body text (alternative) | Inter | <https://rsms.me/inter/> |
| Code | Maple Mono Normal NF CN | <https://github.com/subframe7536/maple-font> |
| Code (alternative) | JetBrains Mono | <https://www.jetbrains.com/lp/mono/> |

## Design notes

The CSS is hand-written for Typora instead of copied from Fuwari's Tailwind and Stylus source. It maps the following Fuwari ideas to Typora selectors:

- `#write` becomes a centered article card similar to a Fuwari post body.
- `:root` defines the theme palette and maps it to Typora variables such as `--bg-color`, `--text-color`, `--primary-color`, `--side-bar-bg-color`, and `--monospace`.
- Inline code uses `--fuwari-inline-code-bg` (light blue `#e2f0ff`) and `--fuwari-inline-code-color`.
- Code fences use a light "Slate Paper" palette — cool, restrained syntax highlighting with distinct token colors.
- Links use the dashed underline and soft hover background used by Fuwari posts.

No external fonts or images are bundled. If `Roboto` or `JetBrains Mono` is installed locally, Typora will use them automatically; otherwise the CSS falls back to system fonts.

## Compatibility

Typora is based on WebKit on macOS and Chromium on Windows/Linux. This theme uses modern CSS features such as `oklch()`, `color-mix()`, `clamp()`, and `:has()`. Recent Typora versions should render these correctly. If an older version does not support part of the palette, update Typora first.

## Customization

To change the accent color, edit this variable in `fuwari-light.css`:

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
3. Adjust palette variables in `fuwari-light.css` and shared selectors in `fuwari-assets/fuwari-base.css`.
4. Restart Typora or switch themes back and forth to reload the CSS.

## Sources referenced

- Fuwari repository: <https://github.com/saicaca/fuwari>
- Fuwari demo: <https://fuwari.vercel.app/posts/expressive-code/>
- Typora custom theme guide: <https://theme.typora.io/doc/Write-Custom-Theme/>
- Typora theme installation guide: <https://theme.typora.io/doc/Install-Theme/>
- Typora style documentation: <https://support.typora.io/style/>

---

Learn AI on LinuxDo <https://linux.do/>
