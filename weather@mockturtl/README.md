# cinnamon-weather

Adaptation of Gnome Shell's [weather extension](https://github.com/simon04/gnome-shell-extension-weather) for the Cinnamon desktop.

cinnamon-weather uses [Semantic Versioning](http://semver.org/).  For the current version number, see `metadata.json`.  

----

## Setup

**The applet obtains the location automatically, see below what the weather providers offer and how to obtain API keys if your chosen weather provider needs one.**

In **Manual Location** mode the applet either accepts:

* **Coordinates** in Latitude, Longitude format (e.g. 37.77,122.41). You can use [OpenWeatherMap's finder](https://openweathermap.org/find) and paste the coordinates in from there.
* or an **Address** (it can be just a city and country, it is pretty flexible). After 3 seconds, the applet will replace what you entered with the full address what it finds so you can verify if it's correct. You can also get your exact address to enter from [OpenStreetMap's Nominatim search](https://nominatim.openstreetmap.org/), that's what the applet uses as well.

You can also save locations what you entered manually and switch between them in the applet *(arrows will appear on both sides of the location in the applet if you have more than two saved)*. 

## Weather providers to choose from

| Weather Providers       | Needs API key | **Maximum Forecast Days** | **Maximum Forecast Hours** | Required Packages         |
| ----------------------- | ------------- | ------------------------- | -------------------------- | ------------------------- |
| **OpenWeatherMap**      | No            | 7                         | 48                         | --                        |
| **DarkSky**             | Yes*          | 8                         | 168                        | --                        |
| **Visual Crossing**     | Yes           | 15                        | 336                        | --                        |
| **MET Norway**          | No            | 10                        | 48                         | --                        |
| **WeatherBit**          | Yes           | 16                        | 0**                        | --                        |
| **Yahoo**               | No            | 10                        | 0                          | python3-requests-oauthlib |
| **ClimacellV3**         | Yes*          | 16                        | 96                         | --                        |
| **ClimacellV4**         | Yes           | 15                        | 108                        | --                        |
| **Met Office UK**       | No            | 5                         | 36                         | --                        |
| **US National Weather** | No            | 7                         | 156                        | --                        |

### OpenWeatherMap

The default, works out of the box. Big Thanks to them supporting free open source projects, like this!

### DarkSky

***[DarkSky has been acquired by Apple](https://blog.darksky.net/dark-sky-has-a-new-home/)** as of March 31, 2020. It does not allow new signups, and it will cease to function at the end of 2021.

## Visual Crossing

* Needs an API key, you can [Sign Up here](https://www.visualcrossing.com/weather/weather-data-services#/signup) and grab one

* Provides 1000 Free calls a day

### MET Norway

Current weather is shown for the next hour, and the daily forecasts are generated from 6 hour forecasts, so there is a possibility that they  are inaccurate sometimes.

### Weatherbit.io

* To get an API key, go to [Weatherbit.io](https://www.weatherbit.io/account/create) and create an account. Then go your [Dashboard](https://www.weatherbit.io/account/dashboard) where you should find your secret key already created.

* At least 10 minutes as refresh rate is recommended, since otherwise you might exceed you daily quota.

* **Hourly Weather forecast requires a non-free account

### Yahoo

Current weather refreshes every 2 hours.

### Climacell V3

*Doesn't accept new registrations anymore, will be closed down later this year (2021)

### Climacell V4

API key can be obtained [here](https://app.climacell.co/signup?planid=5fa4047f4acee993fbd7399d&vid=153ef940-c389-41d4-847e-d83d632059d0). Register and the API key will be shown in the Overview section. Free plan comes with 1000 free calls per day.

### Met Office UK

Sometimes it takes like 5-10 seconds to obtain weather, please be patient when it loads up the first time.

* Only covers the UK

* It uses the nearest forecast site and observation sites in an 50km area, it displays an error if it does not find any. Please open a new issue if this happens and you live in the UK! (There are much less observation sites than forecast sites.)

### US National Weather

Sometimes it takes 10-15 seconds to obtain weather, please be patient when it loads up the first time.

* Only covers the US

* Observations are quite spotty so it combines multiple observation stations if needed in a 50km area.

## Versions

*Versions are automatically selected based on you Cinnamon's version*

* [Cinnamon](https://github.com/linuxmint/Cinnamon) 3.0+ **NOW EOL, won't receive more updates**
* [Cinnamon](https://github.com/linuxmint/Cinnamon) 3.8+

## Configuration

Right-click to access `cinnamon-settings` -> _Applets -> Configure_.

## Mailing list

http://groups.google.com/group/cinnamon-weather

## Future Plans

* None at the moment, I can take requests for provider integrations or for new features

## Known Issues

* Hourly forecast toggle button is not centered to the middle of the popup menu

* Sunset/Sunrise is not displayed correctly if there is a mismatch between the Location Timezone and System Timezone when using Manual Location with some of the weather providers

* DarkSky verbose conditions are only in cm/celsius or in/fahrenheit

### Troubleshooting

#### Enabling debug mode

You can enable debug mode for more logging by creating a file named ```DEBUG``` in the folder of the applet here: ```~/.local/share/cinnamon/applets/weather@mockturtl/```, then restart Cinnamon.

#### See the logs producing by applets

You can see Logs by opening the Cinnamon 'Looking Glass' debugger. You can open it by Right Clicking on your Panel (taskbar), then Troubleshoot->Looking Glass

Logs can be found under the ```Log``` Tab.

[Changelog](https://github.com/linuxmint/cinnamon-spices-applets/blob/master/weather%40mockturtl/CHANGELOG.md)
