# Developer notes

## How it works

The rules apply when:

- The Home carousel contains a `.gpfocuswithin` item.
- The target item is not focused.
- The target item contains a `ShowAsHovered` class.

Affected elements and classes:

| Class | Element | Stale effect |
| --- | --- | --- |
| `basicgamecarousel_ShowAsHovered` | Label wrapper | The title remains visible. |
| `basicgamecarousel_ShowAsHovered` | Capsule glow | The glow stays at `opacity: .5`. |
| `appportrait_ShowAsHovered` | `LibraryItemBox` | The tile keeps its hover transform, brightness, and shadow. |

CSSLoader translates the stable class names in `shared.css` to the current SteamUI hashes. Do not add the raw hashes to the selectors because CSSLoader would inject duplicate selectors.

## Patches

| Patch | Default | Target variable |
| --- | --- | --- |
| Match tile brightness | Auto | `--hctf-tile-brightness` |
| Match tile saturation | Auto | `--hctf-tile-saturate` |

Brightness and saturation use this order:

1. The user patch variables `--hctf-tile-brightness` and `--hctf-tile-saturate`.
2. The Darken Unfocused Games variables `--ren-game-tile-brightness` and `--ren-game-tile-saturate`.
3. The Steam resting values `brightness(0.9)` and `saturate(1)`.

Use **Auto** for stock Steam and Darken Unfocused Games. For another filter-based dimming theme, set both sliders to the values used by that theme.

## Screenshot validation

- Hardware: Steam Deck
- Configuration: Darken Unfocused Games used `0.5` brightness and saturation.
- Client state: The tested Steam client cleared the stale classes automatically.
- Reproduction: The test applied the known stale classes after focus moved to the second card.

The before image shows the stale title, glow, tile transform, brightness, and shadow. The after image shows the corrected resting state while the second card remains focused.
