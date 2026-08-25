# Home Carousel Title Fix

A narrowly scoped CSSLoader theme for the Steam Deck Home screen. It hides the stale title from the first recent-game card when another carousel card has controller focus.

The theme does not patch Steam files or JavaScript. On Steam builds containing Valve's native fix, the stale `ShowAsHovered` state is absent and this theme's rule matches nothing.

## Install locally

1. Install [CSSLoader](https://github.com/DeckThemes/SDH-CssLoader).
2. Copy the `Home Carousel Title Fix` folder to `/home/deck/homebrew/themes/`.
3. Open CSSLoader and enable **Home Carousel Title Fix**.

The installed layout must be:

```text
/home/deck/homebrew/themes/Home Carousel Title Fix/theme.json
/home/deck/homebrew/themes/Home Carousel Title Fix/shared.css
```

## How it works

The rule activates only when:

- the Home carousel contains a `.gpfocuswithin` item;
- the label's own item is not focused; and
- that label still has Steam's `ShowAsHovered` class.

This preserves the default first title before controller navigation, preserves the focused item's title, and hides only the stale nonfocused title.

CSSLoader-friendly class names are paired with current raw SteamUI hashes. CSSLoader can translate known historical class names through its stable/beta mapping service; the raw selectors cover the current affected SteamUI bundle.

## DeckThemes submission

Use the [DeckThemes submission form](https://deckthemes.com/submit/) with:

- Repository URL: `https://github.com/beallio/CSSLoader-Home-Carousel-Title-Fix`
- Subfolder: `Home Carousel Title Fix`
- Commit ID: the release commit or tag being submitted
- Target: `Home`

Before store submission, verify the theme on the latest Steam stable and beta clients and capture an accurate post-fix preview image on a Steam Deck. Those live-device checks cannot be replaced by bundle or parser validation.

## Compatibility

Other themes that reposition or force visibility of Home carousel labels may conflict. Test combinations with carousel-layout themes individually.

If Valve changes the relevant CSS module hashes before CSSLoader publishes updated translations, the rule becomes inert rather than modifying unrelated UI.

## License

MIT
