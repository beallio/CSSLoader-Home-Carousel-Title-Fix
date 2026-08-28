# Home Carousel Title Fix

This CSSLoader theme removes the incorrect hover state from the first recent-game card after controller focus moves to a different card.

## Before / after

| Before: stale first-game title remains visible | After: only the focused game's title remains |
| --- | --- |
| ![Before enabling Home Carousel Title Fix](Home%20Carousel%20Title%20Fix/assets/home-carousel-before.png) | ![After enabling Home Carousel Title Fix](Home%20Carousel%20Title%20Fix/assets/home-carousel-after.png) |

## Install locally

1. Install [CSSLoader](https://github.com/DeckThemes/SDH-CssLoader).
2. Copy the `Home Carousel Title Fix` folder to `/home/deck/homebrew/themes/`.
3. Open CSSLoader.
4. Enable **Home Carousel Title Fix**.

Required file structure:

```text
/home/deck/homebrew/themes/Home Carousel Title Fix/theme.json
/home/deck/homebrew/themes/Home Carousel Title Fix/shared.css
/home/deck/homebrew/themes/Home Carousel Title Fix/README.md
/home/deck/homebrew/themes/Home Carousel Title Fix/developer.md
/home/deck/homebrew/themes/Home Carousel Title Fix/assets/home-carousel-before.png
/home/deck/homebrew/themes/Home Carousel Title Fix/assets/home-carousel-after.png
```

See [developer.md](Home%20Carousel%20Title%20Fix/developer.md) for implementation and patch details.

## Compatibility

- Label themes: Themes that move Home carousel labels or force label visibility can cause conflicts.
- Dimming methods: This theme supports `filter` dimming only.
- Unsupported methods: Themes that use `opacity` or background overlays do not work with these patches.
- Steam updates: If a Steam update changes CSS module hashes, the rules become inactive and do not change the user interface.

## License

MIT
