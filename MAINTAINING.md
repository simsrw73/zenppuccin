# Maintaining Zenppuccin

## Layout

| File | What it holds |
| --- | --- |
| `theme/latte.css`, `mocha.css`, `frappe.css`, `macchiato.css` | One Catppuccin palette each |
| `theme/tokens.css` | Accent selection, accent roles, and the Zen and Firefox design tokens both sheets need |
| `theme/latte-contrast.css` | The "Latte accents: high contrast" values |
| `userChrome.css` | The browser window. Imports `theme/` under Zen's browser appearance setting |
| `userContent.css` | about: pages. Imports `theme/` under Website appearance (`prefers-color-scheme`) |
| `preferences.json` | The options Sine shows |

Sine installs the whole repository, so `theme/` arrives next to the two sheets, and their relative `@import`s resolve.

## Checklist after a Zen or Sine update

The theme depends on Zen's internal markup, class names and variables. None of them are a public API. When Zen renames one, that part of the theme stops applying and nothing reports an error. After an update, check each item in light and dark mode, and search Zen's source for any name that has stopped matching.

### Browser window (`userChrome.css`)

- [ ] **Space backgrounds:** with "Keep Zen's space gradients" off, the sidebar and title area show the flavor color in every space, not Zen's gradient. Depends on `#zen-browser-background`, `#zen-toolbar-background` and the `--zen-main-browser-background*` variables Zen writes inline.
- [ ] **Grain:** a space with a texture set in Edit Theme shows no grain. Depends on `.zen-browser-grain`.
- [ ] **Space header:** a frame-colored bar with the name, the icon in the accent, and the fold chevron at the trailing edge. The chevron shows only for a space that has pinned tabs. Depends on:
  - `.zen-current-workspace-indicator` and its `-name`, `-icon`, `-stack` and `-chevron` children
  - `[zen-emoji-open]`
  - `zen-workspace[haspinnedtabs]` and `[collapsedpinnedtabs]`
  - `[zen-sidebar-expanded]`
- [ ] **Essentials:** base-colored tiles, a soft accent tint on the selected tile, the optional ring, and the icon halo. Depends on `.tabbrowser-tab[zen-essential="true"]`, `--zen-essential-tab-selected-bg*` and `zen.theme.essentials-favicon-bg`.
- [ ] **Sidebar top and bottom bars** match the sidebar. Depends on `#zen-sidebar-top-buttons` and `#zen-sidebar-foot-buttons`.
- [ ] **Content canvas:** a tab shows base, not white or gray, before its page paints; Glance's backdrop is base too. Depends on `browser[type="content"][transparent="true"]` inside `#tabbrowser-tabpanels .browserSidebarContainer` and `--zen-transparent-browser-background`.
- [ ] **Glance buttons:** close, expand and split are text-colored circles with crust icons; close turns red while asking to confirm. Depends on `.zen-glance-sidebar-container`, `.zen-glance-sidebar-close` and `[waitconfirmation]`.
- [ ] **Address bar:** the resting field on the frame, and the solid open view. Depends on `--zen-urlbar-background-base` and `--zen-urlbar-background-transparent`.
- [ ] **Translucency** (Medium, on Windows with Mica):
  - It shows through in an active window.
  - It goes solid when the window is inactive, and in compact mode (`[zen-compact-mode="true"]`).
- [ ] **Light and dark switching:** Edit Theme's auto, light and dark icons switch the window's flavor. Depends on `zen.view.window.scheme` (0 dark, 1 light, 2 system).
- [ ] **Private windows** get the accent-tinted frame. Depends on `[zen-private-window="true"]`.
- [ ] **Media controls and toasts** use the palette. Depends on `#zen-media-controls-toolbar`, `#zen-media-progress-bar` and `#zen-toast-container .zen-toast`.

### about: pages (`userContent.css`)

- [ ] **Settings:** Zen's panes (Look and Feel, Tab Management, Keyboard Shortcuts) and Sine's Mods pane are drawn as cards. Depends on `#mainPrefPane [data-category^="paneZen"]` and `[data-category="paneSineMods"]`.
- [ ] **Row hovers** in Settings and about:keyboard are square fills clipped by the squircle frame, not round pills. Depends on:
  - `moz-box-button`, `moz-box-link` and `moz-box-group`, with `--box-border-radius-inner`
  - `moz-card`, with `--card-border-radius`
  - Zen's `--zen-squircle-value` scaling
- [ ] **about:keyboard** is themed at all. If it isn't, check that `userContent.css` and `theme/` are real files, not symlinks (see below).
- [ ] **Dropdowns:** the selected item uses the accent, not blue or cyan. Depends on `--color-accent-primary-selected`.
- [ ] **Sine's options dialog:**
  - Sections show as bold headings.
  - The dialog is about 550px wide.
  - The search and install boxes have a visible border.

  Depends on `.sineItemPreferenceDialog`, `.sineItemPreferenceDialogContent`, `.separator-label` and `.sineCKSOption-input`.

### Firefox tokens

Firefox and Zen sometimes add new design tokens with hard-coded blues or violets. If a stray color appears, inspect the element, find the variable it comes from, and map it in `theme/tokens.css`. If only one sheet needs it, map it in that sheet instead.

## Development install

To try changes live, the repository is wired into a Zen profile's `chrome/sine-mods/zenppuccin/` folder:

- `userChrome.css` and `preferences.json` can be symlinks to the repository.
- `userContent.css` and the `theme/` folder must be real copies. about: pages such as about:keyboard run sandboxed and can't follow a symlink out of the profile. Copy them again after every edit.
- Set `"no-updates": true` for the mod in `chrome/sine-mods/mods.json`, so Sine doesn't overwrite the local files.
- Restart Zen completely to pick up CSS changes.
