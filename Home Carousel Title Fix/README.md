# Home Carousel Title Fix

> **Archived:** Active development moved to
> [Deck UI Restored](https://github.com/beallio/Deck-UI-Restored). Use its
> optional **Home Carousel Title Fix** for the maintained version. Upstream
> tracking continues in
> [Deck UI Restored issue #2](https://github.com/beallio/Deck-UI-Restored/issues/2).
>
> ## Why development moved from CSS to JavaScript
>
> The CSS workaround can hide the stale title, glow, and raised tile, but it must
> replace Steam's opacity, transform, filter, shadow, and stacking values with
> `!important` rules. A live CSSLoader theme survey found direct conflicts with
> six published themes, and CSS cannot recover the values chosen by every other
> theme.
>
> The Deck UI Restored implementation removes only Steam's stale hover classes
> when controller focus moves. Steam and CSSLoader then calculate their normal
> styles again. This JavaScript approach preserves other themes and fixes the
> incorrect state instead of covering it with replacement styles.
>
> The files in this repository remain available as a historical CSS fallback, but
> they are no longer under active development.


This CSSLoader theme removes the incorrect hover state from the first recent-game card after controller focus moves to a different card.

## Before / after

| Before: stale first-game title remains visible | After: only the focused game's title remains |
| --- | --- |
| ![Before enabling Home Carousel Title Fix](assets/home-carousel-before.png) | ![After enabling Home Carousel Title Fix](assets/home-carousel-after.png) |


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

See [developer.md](developer.md) for implementation and patch details.

## Compatibility

- Label themes: Themes that move Home carousel labels or force label visibility can cause conflicts.
- Dimming methods: This theme supports `filter` dimming only.
- Unsupported methods: Themes that use `opacity` or background overlays do not work with these patches.
- Steam updates: If a Steam update changes CSS module hashes, the rules become inactive and do not change the user interface.

## License

MIT
