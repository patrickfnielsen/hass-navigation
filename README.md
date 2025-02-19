# Navigation Card
[![hacs][hacs-badge]][hacs-url]
[![release][release-badge]][release-url]
![downloads][downloads-badge]
![build][build-badge]

**WARNING: THIS CARD IS IN ALPHA AT BEST!**

**Images**

![Cards - Noctis](https://github.com/patrickfnielsen/hass-navigation-card/blob/master/docs/images/theme-noctis.png?raw=true)


## What is Navigation Card
Navigation Card is designed to give you a usefull navigation bar at the bottom of your screen. Each icon can be customized as needed, and so can the actions.

If used together with Kiosk Mode a really clean layout can be archived.

## Installation

### HACS
Navgation Card is available in [HACS][hacs] (Home Assistant Community Store).
1. Install HACS if you don't have it already
2. Open HACS in Home Assistant
3. Go to "Frontend" section
4. Press the 3 dots in the top right, and select "Custom repositories"
5. For repository enter "https://github.com/patrickfnielsen/hass-navigation-card" and category select "frontend"
6. Click button with "+" icon
7. Search for "Navigation Card"

### Manual
1. Download `navigation-card.js` file from the [latest release][release-url].
2. Put `navigation-card.js` file into your `config/www` folder.
3. Add reference to `navigation-card.js` in Dashboard. There's two way to do that:
    - **Using UI:** _Settings_ → _Dashboards_ → _More Options icon_ → _Resources_ → _Add Resource_ → Set _Url_ as `/local/navigation-card.js` → Set _Resource type_ as `JavaScript Module`.
      **Note:** If you do not see the Resources menu, you will need to enable _Advanced Mode_ in your _User Profile_
    - **Using YAML:** Add following code to `lovelace` section.
        ```yaml
        resources:
            - url: /local/navigation-card.js
              type: module
        ```

## Configuration variables
TODO

### YAML Example
**IMPORTANT**: This should be placed as the last card

```yaml
type: custom:navigation-card
icon: mdi:home
items:
  - icon: mdi:home
    on_tap:
      action: navigate
      navigation_path: /dashboard-rooms/home
  - icon: mdi:lightbulb-group
    on_tap:
      action: navigate
      navigation_path: /dashboard-rooms/lights
  - icon: mdi:temperature-celsius
    on_tap:
      action: navigate
      navigation_path: /dashboard-rooms/climate
  - icon: mdi:blinds
    on_tap:
      action: navigate
      navigation_path: /dashboard-rooms/blinds
  - icon: mdi:robot-vacuum
    on_tap:
      action: navigate
      navigation_path: /dashboard-rooms/vacuum

```


### Theme customization
Navigation Card works without a theme, but you can add a theme like [Noctis](https://github.com/aFFekopp/noctis). If you want more information about themes, check out the official [Home Assistant documentation about themes][home-assitant-theme-docs].

<!-- Badges -->
[hacs-url]: https://github.com/hacs/integration
[hacs-badge]: https://img.shields.io/badge/hacs-default-orange.svg?style=flat-square
[release-badge]: https://img.shields.io/github/v/release/patrickfnielsen/hass-room-card?style=flat-square
[downloads-badge]: https://img.shields.io/github/downloads/patrickfnielsen/hass-room-card/total?style=flat-square
[build-badge]: https://img.shields.io/github/actions/workflow/status/patrickfnielsen/hass-room-card/build.yaml?branch=main&style=flat-square

<!-- References -->
[home-assistant]: https://www.home-assistant.io/
[home-assitant-theme-docs]: https://www.home-assistant.io/integrations/frontend/#defining-themes
[hacs]: https://hacs.xyz
[release-url]: https://github.com/patrickfnielsen/hass-room-card/releases
