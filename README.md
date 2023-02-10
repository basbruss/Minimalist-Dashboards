# UI-Lovelace-Minimalist Dashboards

![UI-Minimalist Version](https://img.shields.io/github/v/release/UI-Lovelace-Minimalist/UI)
[![Minimalist Discord](https://badgen.net/discord/online-members/TPXg9b7GfR)](https://discord.gg/TPXg9b7GfR)

This repo functions as a showcase of the [Minimalist](https://github.com/UI-Lovelace-Minimalist/UI) themed dashboards I am currently using. Feel free to take some inspiration from it to design your own Minimalist dashboards!
*It's not advised to directly copy this repo for your own use*

## [Adaptive Dashboard](https://ui-lovelace-minimalist.github.io/UI/setup/adaptive_dash/)

This dashboard is designed to view on all sort of devices.
 <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mockups/light%20mode.png" width="600"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mockups/dark%20mode.png" width="600">
 

## Resources
This dashboard is made with the Adaptive Dashboard provided by [UI-Minimalist](https://ui-lovelace-minimalist.github.io). It uses the custom Frontend Plugins from HACS recommended by Minimalist and some additions.
| Resources used                            |
|-------------------------------------------------------------------------|
| [`browser-mod`](https://github.com/thomasloven/hass-browser_mod)        |
| [`button-card`](https://github.com/custom-cards/button-card)            |
| [`lovelace-card-mod`](https://github.com/thomasloven/lovelace-card-mod) |
| [`mini-graph-card`](https://github.com/kalkih/mini-graph-card)          |
| [`mini-media-player`](https://github.com/kalkih/mini-media-player)      |
| [`my-cards-slider-card`](https://github.com/AnthonMS/my-cards)          |
| [`light-entity-card`](https://github.com/ljmerza/light-entity-card)     |
| [`layout-card`](https://github.com/thomasloven/lovelace-layout-card)    |
| [`weather-radar-card`](https://github.com/Makin-Things/weather-radar-card)    |
| [`state-switch`](https://github.com/thomasloven/lovelace-state-switch) |
| [`swiper-card`](https://github.com/bramkragten/swipe-card)|

## Helpers
I am using two `input_select` helpers in combination with `state-swtich`for this dashboard.

1. `input_select.adaptive_dashboard` for the right-side popups <br>
        the options can be found in `popup.yaml`.
2. `input_select.adaptive_slider` for the card-slider. <br>
        the options can be found in `main.yaml`.
## File system

I am using a so called "split config". This allows me to put each tab in it's own YAML-file. And it allows me to re-use parts which are included in multiple tabs without copying large amounts of code. 

To take this approach even further I have also introduced YAML-anchors to my files.
