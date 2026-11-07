![Zenppuccin logo: a smiling cat with a bow tie inside a ring of Catppuccin colors](images/zenppuccin.png)

# Zenppuccin

A theme for [Zen Browser](https://zen-browser.app/), built on the [Catppuccin](https://catppuccin.com/) palettes and installable with the [Sine](https://github.com/CosmoCreeper/Sine) mod manager. It covers all four flavors, with your choice of accent color and optional translucency.

This is not an official Catppuccin port.

## Goals

1. Catppuccin applied consistently across Zen's window, components and settings pages. By default, every color comes from the palette.
2. Your choice of dark flavor (Frappé, Macchiato or Mocha; Latte in light mode), accent color and translucency.
3. Better contrast where Catppuccin falls short of WCAG, mainly Latte's light accents. Where we can, we raise contrast without leaving the palette. The optional high-contrast Latte setting does leave it: it darkens accents while keeping their hue and saturation.
4. CSS only. No scripts.

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
- **Latte accents: high contrast:** some Latte accents are too light for text and for buttons with text on them. This uses darker shades of the same hue that pass WCAG contrast for text, buttons, accent icons and the focus ring. It also shows links as plain text with an accent underline, makes selection a soft accent tint, and darkens secondary text slightly. It's off by default, so you get Catppuccin's exact colors, and it doesn't change the dark flavors.

**Background**

- **Translucency:** Off (default), Subtle, Medium or Strong. The sidebar and title area keep the flavor's colors, and the window backdrop shows through them, as with Zen's own transparency. It needs Mica on Windows 11, macOS, or Linux with Zen's transparency setting on. It has no effect when your system asks for reduced transparency, when the window is inactive on Windows, or in compact mode. See [Transparency settings](#transparency-settings).
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

## Related

Zenppuccin is the browser theme in my own setup. These are the projects around it:

- **[dotfiles-windows](https://github.com/simsrw73/dotfiles-windows)**: My whole Windows setup, managed with chezmoi: `~/.config`, the PowerShell profile, apps, keys and secrets. The other projects here are either used by it or published from it.
- **[catelier](https://github.com/simsrw73/catelier)**: A Catppuccin theme for the yasb status bar, in all four flavors with your choice of accent. It's the bar in w11dwm-config and dotfiles-windows.
- **[w11dwm-config](https://github.com/simsrw73/w11dwm-config)**: The keyboard-driven tiling desktop (komorebi, AutoHotkey, yasb, Flow Launcher, wpm), copied out of dotfiles-windows to share and discuss. Its key bindings, app launcher and window switcher are built on Legend.ahk.
- **[Legend.ahk](https://github.com/simsrw73/Legend.ahk)**: An AutoHotkey v2 library: an Alt+/ overlay of the shortcuts for the app you're in, which-key style chord menus, pickers and a window switcher. It runs the keys in w11dwm-config and dotfiles-windows.
- **[DotForge](https://github.com/simsrw73/DotForge)**: A PowerShell module that installs and configures command-line tools: XDG paths, fzf pickers, completions, shell hooks. The PowerShell profile in dotfiles-windows loads it, and it sets up Starship to read the starship-p9cat config.
- **[starship-p9cat](https://github.com/simsrw73/starship-p9cat)**: A Starship prompt in the powerlevel9k style, in Catppuccin colors. It's the prompt in dotfiles-windows, and a port of the CatPow theme from poshcat.omp.
- **[poshcat.omp](https://github.com/simsrw73/poshcat.omp)**: Catppuccin themes for Oh My Posh, including CatPow, a powerlevel10k-style theme. It was my prompt before Starship; starship-p9cat carries CatPow over.

## Credits

Colors are from [Catppuccin](https://github.com/catppuccin/catppuccin). The styles started from [Catppuccin for Zen Browser](https://github.com/catppuccin/zen-browser). Both are MIT-licensed; see [LICENSE](LICENSE).
