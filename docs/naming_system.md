# Export Naming System

## Pattern

```
{base}[_animation][_toy|_tool].{ext}
```

## Base Name

- Uses the **project name**, sanitized to `lowercase_snake_case`
  - Spaces become underscores
  - Special characters are removed
  - All characters lowercased
  - Example: `"My Cool Art!"` → `my_cool_art`
- If the project has no name or is unnamed, falls back to `glyph_art`

## Suffixes

| Suffix | Condition |
|---|---|
| `_animation` | Export contains multiple frames (animated GIF, WebM, MP4, or multi-frame data) |
| `_toy` | Glyph Toy/Tool icon mode is active and current profile is Phone 3 |
| `_tool` | Glyph Toy/Tool icon mode is active and current profile is Phone 4a |
| `_data` | Data export (JSON, binary, array) — always last before extension |

Suffixes stack in order: `_animation` → `_toy`/`_tool` → `_data`

## Examples

### Project named "My Cool Art" on Phone 3

| Export Type | Filename |
|---|---|
| Static image | `my_cool_art.png` |
| Static image + Glyph Toy | `my_cool_art_toy.png` |
| Static SVG | `my_cool_art.svg` |
| Static SVG + Glyph Toy | `my_cool_art_toy.svg` |
| ICO | `my_cool_art.ico` |
| Animated GIF | `my_cool_art_animation.gif` |
| Animated GIF + Glyph Toy | `my_cool_art_animation_toy.gif` |
| Animated WebM | `my_cool_art_animation.webm` |
| Animated WebM + Glyph Toy | `my_cool_art_animation_toy.webm` |
| Single-frame data (JSON) | `my_cool_art_data.json` |
| Multi-frame data (JSON) | `my_cool_art_animation_data.json` |

### Unnamed project on Phone 4a

| Export Type | Filename |
|---|---|
| Static image | `glyph_art.png` |
| Static image + Glyph Tool | `glyph_art_tool.png` |
| Animated GIF + Glyph Tool | `glyph_art_animation_tool.gif` |
| Single-frame data | `glyph_art_data.json` |
| Multi-frame data | `glyph_art_animation_data.json` |
