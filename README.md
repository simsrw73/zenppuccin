# Zenppuccin

A theme for [Zen Browser](https://zen-browser.app/), built on the [Catppuccin](https://catppuccin.com/) palette and installed with the [Sine](https://github.com/CosmoCreeper/Sine) mod manager. It isn't an official Catppuccin port.

## Install

1. In Zen, open **Settings → Sine Mods**.
2. Paste this link into the install box and select **Install**:

   ```
   https://github.com/simsrw73/zenppuccin
   ```

## Options

Open the mod's options in Sine to choose:

**Colors**

- **Accent color:** any of the 14 Catppuccin accents (default Mauve).
- **Dark mode flavor:** Frappé, Macchiato or Mocha (default). Light mode always uses Latte.
- **Latte accents: high contrast:** some Latte accents are too light for text and for buttons with text on them. This uses darker shades of the same hue that pass WCAG contrast, shows links as plain text with an accent underline, and makes selection a soft accent tint. Off by default, which keeps Catppuccin's exact colors. Dark flavors don't change.

**Background**

- **Translucency:** Off (default), Subtle, Medium or Strong. Keeps the flavor's colors but lets the window backdrop show through the sidebar and title area, like Zen's own transparency. It needs Mica on Windows 11, macOS, or Linux with Zen's transparency setting on. It has no effect when your system asks for reduced transparency, when the window is inactive on Windows, or in compact mode. See [Transparency settings](#transparency-settings).
- **Keep Zen's space gradients:** keeps Zen's per-space gradient backgrounds instead of the theme's. While it's off, Zen's **Edit Theme** dialog has no visible effect.

**Sidebar**

- **Toolbar and sidebar icons:** the accent color (default) or the text color.
- **Ring around Essentials tiles:** draws a thin ring around Essentials tiles.

## Transparency settings

The Translucency option only decides how much of the flavor color covers the window. What shows through comes from your system and from Zen's own settings, which aren't in Zen's Settings page:

| Setting | Where | What it does |
| --- | --- | --- |
| **Transparency effects** | Windows **Settings → Personalization → Colors** | Must be on, or Windows draws no backdrop and the option has no effect. |
| `widget.windows.mica.toplevel-backdrop` | `about:config` | The Windows backdrop material. `2`, Zen's default, is Acrylic: frosted glass that blurs whatever is behind the window. `1` is Mica: a soft tint taken from your wallpaper, which barely looks transparent. |
| `zen.theme.acrylic-sidebar` | `about:config` | Zen's own blur behind the sidebar, including the floating sidebar in compact mode. |
| `zen.theme.acrylic-urlbar` | `about:config` | The same blur behind the open address bar. |
| `zen.widget.linux.transparency` | `about:config` | Turns on transparency on Linux. |

Restart Zen after changing any of them.

## Light and dark mode

Zen has two separate light and dark settings, and the theme follows both:

| Setting | What it changes | Where to find it |
| --- | --- | --- |
| **Browser appearance** | The browser window: sidebar, tabs, menus and address bar | Right-click the tab sidebar, select **Edit Theme**, and use the auto, light and dark icons at the top. |
| **Website appearance** | Web pages and Zen's own pages, such as Settings and the new tab page | **Settings → Website appearance** |

## Credits

Colors are from [Catppuccin](https://github.com/catppuccin/catppuccin). The styles started from [Catppuccin for Zen Browser](https://github.com/catppuccin/zen-browser). Both are MIT-licensed; see [LICENSE](LICENSE).
