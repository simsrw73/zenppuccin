# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Zen Browser users who find the theme on the Sine mod marketplace and want Catppuccin colors across the whole browser. They install it with one link, choose options once in Sine, and then live in the browser every day. For them it's ambient: it has to look right in every state and scheme without them having to think about it.

## Product Purpose

Zenppuccin restyles Zen Browser's own interface with the Catppuccin palette: the browser window (sidebar, tabs, Essentials, URL bar, menus, panels) through `userChrome.css`, and Zen's internal about: pages (Settings, new tab) through `userContent.css`. Success means a Catppuccin user installs it once and the whole browser feels native to the palette, stays readable, and holds up across Zen updates.

## Positioning

It's a single Sine mod with live options. Users pick the dark flavor and accent in Sine's option panel, with no separate theme to install for each flavor and accent. It follows both of Zen's appearance settings: Latte in light mode and the chosen flavor in dark mode, for both browser appearance and website appearance. It covers Zen's about: pages as well as the browser window. It goes past a palette swap with opinionated detail work, such as Essentials tiles that sit flush with the sidebar and take an accent tint when selected, private windows tinted with the accent, and per-element icon fill handling. It began as a fork of the official catppuccin/zen-browser theme and isn't an official Catppuccin port.

## Operating Context

- Installed and configured through Sine (**Settings → Sine Mods**). Options are declared in `preferences.json` and read in CSS as `zenppuccin.*` prefs.
- Zen keeps browser appearance (`zen.view.window.scheme`) and website appearance separate, and the theme has to follow both.
- Zen's own CSS uses `!important` and inline `style.setProperty()`, so the theme overrides with user-sheet `!important`. Zen's `zen-theme.css` loads in both the browser window and about: pages, so shared tokens go in both sheets.
- Zen space gradients and the Edit Theme dialog interact with the theme background (see the keep-space-gradients option).

## Capabilities and Constraints

- Options: dark flavor (Frappé, Macchiato, Mocha by default), accent (any of the 14 Catppuccin accents, Mauve by default), keep space gradients, plain icons, Essentials ring.
- Pure CSS. No scripts, so behavior is limited to what userChrome and userContent selectors and prefs can express.
- Has to survive Zen and Firefox updates that rename selectors or tokens.

## Brand Commitments

- Name: Zenppuccin. Author: simsrw73. Home: https://github.com/simsrw73/zenppuccin.
- Be faithful to the Catppuccin palette and its style guide, including which color fills which role (surfaces, overlays, text, accents).
- Never present it as an official Catppuccin port. Credit Catppuccin and the catppuccin/zen-browser origin (MIT).

## Evidence on Hand

- README.md, theme.json and preferences.json describe the install flow and the options.
- No screenshots, user feedback, install counts or testimonials are on hand yet. Don't invent them.

## Product Principles

1. Faithful to Catppuccin by default: palette colors in the roles the style guide assigns them.
2. Readability and accessibility win over fidelity. Where they conflict, bring up alternatives and decide together with the maintainer; never resolve it silently either way.
3. One install, a few clear options. Each option has to earn its place and work with every flavor and accent.
4. Respect Zen's model: its two appearance settings, its spaces, and its native affordances stay intact and work as Zen users expect.
5. Detail is the differentiator: the hover, selected, private and empty states get the same care as the default view.

## Accessibility & Inclusion

Text and icon contrast have to stay readable in every flavor and accent combination, including light-on-light accents in Latte. Any conflict between Catppuccin fidelity and contrast or legibility goes to the maintainer as a decision with alternatives.
