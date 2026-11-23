<h1 align="center">Test Theme</h1>

<p align="center">A customizable dark theme in LYTE colors styling all 12 window targets with 10 color pickers and 11 layout and effect options.</p>

<p align="center"><img src="assets/preview.png" alt="Test Theme in the Steam main window"></p>

## What it styles

Every window target that LYTE supports has its own stylesheet, including shared desktop styling across Steam client windows.

| Window | File | What changes |
| --- | --- | --- |
| All windows | `css/all.css` | Color tokens, border modes, selection highlight, focus outlines, scrollbar styles and window labels |
| Desktop windows | `css/desktop.css` | Shared client controls and the search, table and game rows in the Add a Non-Steam Game dialog |
| Main window | `css/main.css` | Navigation, game list and shelves, game detail activity and side panels, download queue and graph surroundings |
| Settings | `css/settings.css` | Unified dark sidebar and content columns, active accent bar, field cards and dividers |
| Friends | `css/friends.css` | Friends list, quick-access row, custom online/in-game status colors, chat windows, hover cards and menus |
| Overlay | `css/overlay.css` | Translucent overlay panels, browser, notes, screenshots and timeline bar |
| Menus | `css/menus.css` | Menu popups, rounded items, hover highlight and separators |
| Notifications | `css/notifications.css` | Accent-bordered toast cards, subtle tint background and notification typography |
| Dialogs | `css/dialogs.css` | Modal frames, headers, properties surfaces and bottom button row |
| Store | `css/store.css` | Store header, body surface, cover radii, active row bar, discount badge and footer |
| Community | `css/community.css` | Responsive page frame, hubs, profiles, groups, Workshop, Market and discussions |
| Web pages | `css/web.css` | Support page panels, wizard buttons, selection highlight and footer |

## Options

Open **Settings**, then **LYTE**, then **Themes**, and select **Options** on the theme.

### Colors

| Option | Default | What it does |
| --- | --- | --- |
| Accent color | `#c8f542` | Highlights, active indicators, badges and focus outlines |
| Text on accent | `#0c0f02` | Text and icons on accent buttons and discount badges |
| Frame and bar color | `#09090a` | Top bar, bottom bar, sidebars, menus and web headers |
| Background color | `#111113` | Main Library, Settings content, Friends list and Store pages |
| Card color | `#18181b` | Shelves, settings rows, dialogs, toast cards and info panels |
| Control color | `#222227` | Buttons, search inputs, pills and hovered cards |
| Primary text | `#ededee` | Headings, titles and active labels |
| Muted text | `#9b9ba2` | Secondary labels, navigation items and metadata |
| In-game status | `#7fce5b` | Running games and friends currently in a game |
| Online status | `#57b9e6` | Friends currently online |

### Shape, layout & effects

| Option | Type | Default | What it does |
| --- | --- | --- | --- |
| Corner radius | Slider, 0 to 14 px | `6px` | Buttons, cards, inputs, menus and dialogs |
| Cover radius | Slider, 0 to 16 px | `8px` | Library game covers, event capsules and store tiles |
| Sidebar width | Slider, 220 to 360 px | `260px` | Minimum width of the Library game list sidebar |
| Navigation size | Select | `Regular` | Compact, regular or roomy top navigation text |
| Library shelves | Select | `Clean open` | Open shelves or framed card containers on Library home |
| Surface borders | Select | `Subtle hairline` | None, subtle hairline or accent-tinted borders |
| Ambient glow | Toggle | `true` | Soft accent spotlight behind Library home and game headers |
| Cover hover lift | Toggle | `true` | Gently lifts and shadows game covers on hover |
| Scrollbar style | Select | `Minimal neutral` | Minimal neutral, accent thumb or hidden scrollbars |
| Bottom bar texture | Toggle | `false` | Optional pattern overlay on the bottom bar |
| Window labels | Toggle | `false` | Prints the window target in the lower right corner of every window |

Turn on **Window labels** to check that a style file reached the window you expect.

## Use options in your own theme

Every option becomes a CSS variable named after its id. Toggles and selects also set an attribute on the root element.

```css
.steam-SuperNav--Selected {
  box-shadow: inset 0 -2px 0 var(--accent, #c8f542);
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
  "default": "#c8f542"
}
```

> Steam changes its class names often. Write `.steam-Name` and LYTE swaps in the current class for you.

## Install

Install it from the LYTE catalog, or download the repository and use **Import folder** on the Themes page.

## License

MIT
