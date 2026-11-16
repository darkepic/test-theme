<h1 align="center">Test Theme</h1>

<p align="center">A dark reference theme for LYTE that styles every window type, with colors, a slider, a select and toggles you can change in the settings.</p>

<p align="center"><img src="assets/preview.png" alt="Test Theme in the Steam main window"></p>

## What it styles

Every window type that LYTE can reach has its own stylesheet, so you can see which file does what.

| Window | File | What changes |
| --- | --- | --- |
| All windows | `css/all.css` | Selection color and the optional window label |
| Main window | `css/main.css` | Top bar, navigation, library background, game list, section headers, bottom bar with a texture |
| Settings | `css/settings.css` | Page list, title and background |
| Friends | `css/friends.css` | Friends list background |
| Overlay | `css/overlay.css` | Accent frame |
| Menus | `css/menus.css` | Menu background, corners and separators |
| Notifications | `css/notifications.css` | Accent frame |
| Dialogs | `css/dialogs.css` | Dialog content and button row |
| Store | `css/store.css` | Store header and page corners |
| Community | `css/community.css` | Community header |
| Web pages | `css/web.css` | Selection color |

## Options

Open **Settings**, then **LYTE**, then **Themes**, and select **Options** on the theme.

| Option | Type | What it does |
| --- | --- | --- |
| Accent color | Color | Highlights, selection and focus |
| Surface color | Color | Library and settings background |
| Bar color | Color | Top bar, side lists and bottom bar |
| Corner radius | Slider, 0 to 12 px | Buttons and menus |
| Navigation size | Select | Compact, regular or roomy navigation text |
| Bottom bar texture | Toggle | Draws the bundled image on the bottom bar |
| Window labels | Toggle | Prints the window type in the lower right corner of every window |

Turn on **Window labels** to check that a style file reached the window you expect.

## Use options in your own theme

Every option becomes a CSS variable named after its id. Toggles and selects also set an attribute on the root element.

```css
.steam-SuperNav--Selected {
  box-shadow: inset 0 -2px 0 var(--accent, #4fd1c5);
}

html[data-theme-density="compact"] .steam-SuperNav {
  font-size: 12px;
}
```

The option itself is declared in `lyte.theme.json`:

```json
{
  "id": "accent",
  "type": "color",
  "label": "Accent color",
  "group": "Colors",
  "default": "#4fd1c5"
}
```

> Steam changes its class names often. Write `.steam-Name` and LYTE swaps in the current class for you.

## Install

Install it from the LYTE catalog, or download the repository and use **Import folder** on the Themes page.

## License

MIT
