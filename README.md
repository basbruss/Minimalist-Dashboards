# UI-Lovelace-Minimalist Dashboards

![UI-Minimalist Version](https://img.shields.io/github/v/release/UI-Lovelace-Minimalist/UI)
[![Minimalist Discord](https://badgen.net/discord/online-members/TPXg9b7GfR)](https://discord.gg/TPXg9b7GfR)

This repo functions as a showcase of the [Minimalist](https://github.com/UI-Lovelace-Minimalist/UI) themed dashboards I am currently using. Feel free to take some inspiration from it to design your own Minimalist dashboards!
*It's not advised to directly copy this repo for your own use*

## [Mobile Dashboard](https://github.com/basbruss/Minimalist-Dashboards/tree/main/dashboard/mobile)

This dashboard is designed to view on mobile devices.

<img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/light_main.PNG" width="200"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/light_lights.PNG" width="200"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/light_woonkamer.PNG" width="200">
<img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/dark_lights.PNG" width="200"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/dark_main.PNG" width="200"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/mobile/dark_woonkamer.PNG" width="200"> 

## [Web Dashboard (Sidebar)](https://github.com/basbruss/Minimalist-Dashboards/tree/main/dashboard/web)

This dashboard is designed to show on PC's and Tablets. It makes use of the ["Sidebar View"](https://www.home-assistant.io/lovelace/sidebar/) style lovelace dashboard.

<img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/web/light_main.png" width="400"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/web/light_lights.png" width="400"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/web/dark_main.png" width="400"> <img src="https://raw.githubusercontent.com/basbruss/Minimalist-Dashboards/main/git_assets/web/dark_lights.png" width="400">

## File system

I am using a so called "split config". This allows me to put each tab in it's own YAML-file. And it allows me to re-use parts which are included in multiple tabs without copying large amounts of code (like the sidebar).

All my dashboard files use `!include` to add additional tabs. I don not use `!include_dir_merge_list: mobile/` because that sorts based on an alphabetic/numeric order. This approach allows me to have more control of the order of the tabs without changing names of the files to achieve a different order.
```yaml
---
button_card_templates: !include_dir_merge_named "../../custom_components/ui_lovelace_minimalist/__ui_minimalist__/ulm_templates/"

title: "UI Lovelace Minimalist"
theme: "minimalist-mobile-tapbar"
views:
  - !include "mobile/main.yaml"
  - !include "mobile/lights.yaml"
  - !include "mobile/woonkamer.yaml"
  - !include "mobile/slaapkamer.yaml"
  - !include "mobile/badkamer.yaml"
  - !include "mobile/network.yaml"
  - !include "mobile/energy.yaml"
```

```yaml
config
└── ui_lovelace_minimalist
    ├── custom_cards
    └── dashboard
        ├── ui-lovelace.yaml            #web-dashboard
        ├── ui-lovelace-mobile.yaml     #mobile-dashboard
        ├── mobile                      #mobile-tabs
        |   ├── main.yaml
        |   ├── lights.yaml
        |   ├── woonkamer.yaml
        |   ├── slaapkamer.yaml
        |   ├── badkamer.yaml
        |   ├── network.yaml
        |   ├── energy.yaml
        |   └── bar
        |       ├── chip_bar_top.yaml
        |       ├── chip_bar_top_back.yaml
        |       └── chip_bar_under.yaml
        └── web                        #web-tabs
            ├── main.yaml
            ├── lights.yaml
            ├── woonkamer.yaml
            ├── slaapkamer.yaml
            ├── badkamer.yaml
            └── areas
                └── chips.yaml
                └── climate.yaml
                └── devices.yaml
                └── media.yaml
                └── power.yaml
                └── rooms.yaml
                └── sidebar.yaml
```

## Mulitple dashboards

The integration only configures one dashboard for you (`"ui_lovelace.yaml"`). You can alter this file to your liking. To add more dashboards you can configure them in your `"configuration.yaml"` file. It should be something like:
```yaml
lovelace:
  mode: storage
  # Add yaml dashboards
  dashboards:
    lovelace-minimalist-mobile:
      mode: yaml
      title: Minimalist Mobile
      icon: mdi:flower
      show_in_sidebar: true
      filename: ui_lovelace_minimalist/dashboard/ui-lovelace-mobile.yaml
    # lovelace-minimalist-tablet:
    #   mode: yaml
    #   title: Minimalist tablet
    #   icon: mdi:flower
    #   show_in_sidebar: true
    #   filename: ui_lovelace_minimalist/dashboard/ui-lovelace-tablet.yaml
```
