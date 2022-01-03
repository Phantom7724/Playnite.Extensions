# Extensions for Playnite

This is a collection of extensions for [Playnite](https://github.com/JosefNemec/Playnite) I created.

## Installation

1) Get the latest Release from the [Release Tab](https://github.com/erri120/Playnite.Extensions/releases/).
2) Copy the folder to your `Playnite/Extensions/` folder.

## Metadata Providers

### DLsite

**Website**: [English](https://dlsite.com/maniax/?locale=en_US), [Japanese](https://dlsite.com/maniax/?locale=ja_JP)

**Supported Fields**:

- Name
- Features/Genres/Tags
- Developers
- Release Date
- Icon
- Cover/Background Image

**Usage**:

This Metadata Provider expects either a link to the game on DLsite (eg: `https://www.dlsite.com/maniax/work/=/product_id/RJ246037.html`) or the id (eg: `RJ246037`) in the _Name_ field. If the Plugin finds neither a link nor an id it will go into search mode and you can search the game on DLsite. If the request for metadata is in happening in the background, the Plugin will choose the first search result by default.

**Settings**:

The following settings can be adjusted in _Add-ons..._ -> _Extensions settings_ -> _Metadata Sources_ -> _DLsite_:

| Name                                                                   | Default Value | Description                                                                                                             |
|------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------|
| Preferred Language                                                     | `en_US`       | DLsite supports `en_US`, `ja_JP`, `ko_KR`, `zh_CN` and `zh_TW`                                                          |
| Include Scenario Writers as Developers                                 | Yes           | This will include Scenario Writers in the Developers field in Playnite                                                  |
| Include Illustrators as Developers                                     | Yes           | This will include Illustrators in the Developers field in Playnite                                                      |
| Include Voice Actors as Developers                                     | Yes           | This will include Voice Actors in the Developers field in Playnite                                                      |
| Include Music Creators as Developers                                   | Yes           | This will include Music Creators in the Developers field in Playnite                                                    |
| Which property should the DLsite categories be assigned to in Playnite | Features      | You can decide whether the "Categories" from DLsite should go into the "Features", "Genres" or "Tags" field in Playnite |
| Which property should the DLsite genres be assigned to in Playnite     | Genres        | You can decide whether the "Genres" from DLsite should go into the "Features", "Genres" or "Tags" field in Playnite     |
| Max Search Results                                                     | 30            | Maximum amount of search results that should appear, must be `30`, `50` or `100`                                        |

**Config location**: `7fa7b951-3d32-4844-a274-468e1adf8cca/config.json`

### F95zone

**Website**: [F95zone](https://f95zone.to)

**Supported Fields**:

- Name
- Developers
- Features/Genres/Tags
- Version
- Community Score
- Cover/Background Image

**Usage**:

This Metadata Provider expects either a link to the game on F95zone (eg: `https://f95zone.to/threads/corruption-of-champions-fenoxo.1719/`) or the id (eg: `F95-1719`) in the _Name_ field. If the Plugin finds neither a link nor an id it will go into search mode and you can search the game on F95zone. If the request for metadata is in happening in the background, the Plugin will choose the first search result by default.

The search function is only available if you logged into your account in the settings menu.

**Settings**:

The following settings can be adjusted in _Add-ons..._ -> _Extensions settings_ -> _Metadata Sources_ -> _F95zone_:

| Name                                                                | Default Value | Description                                                                                                                                                                                                                                                                                           |
|---------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Login                                                               | -             | Use this Login Button to log into F95zone with your account. If this does not work you can copy the required cookies from your browser into the text fields below.                                                                                                                                    |
| Cookie `xf_csrf`                                                    | -             | Cookie used for authentication.                                                                                                                                                                                                                                                                       |
| Cookie `xf_user`                                                    | -             | Cookie used for authentication.                                                                                                                                                                                                                                                                       |
| Cookie `xf_tfa_trust`                                               | -             | Cookie used for authentication if the user has Two-Factor authentication enabled. If you do not have TFA enabled you don't need to set this value.                                                                                                                                                    |
| Which property should the F95zone labels be assigned to in Playnite | Features      | You can decide whether the "Categories" from DLsite should go into the "Features", "Genres" or "Tags" field in Playnite                                                                                                                                                                               |
| Which property should the F95zone tags be assigned to in Playnite   | Tags          | You can decide whether the "Genres" from DLsite should go into the "Features", "Genres" or "Tags" field in Playnite                                                                                                                                                                                   |
| Check for Updates on Startup                                        | false         | This Plugin will check for updates on startup if you want. You can also specify the minimum wait time between updates per game.                                                                                                                                                                       |
| Update Interval in Days                                             | 7             | This is the minimum wait time between update checking **per game**. This value must be a positive number.                                                                                                                                                                                             |
| Look for Updates of Completed Games                                 | false         | Setting this to true will make the Plugin look for updates for games that have the F95zone "Completed" label. I don't recommend setting this to true because it is very unlikely that a game will receive an update once it is marked as "Completed" and will only put strain on the F95zone servers. |

**Config location**: `3af84c02-7825-4cd6-b0bd-d0800d26ffc5/config.json`

## Troubleshooting

Always check the log file `playnite.log` in `%appdata%/Playnite` or in the Playnite installation directory first. You can also try deleting your config file for a specific extension if you think that is the problem, the paths to the config files are in the description of the each extension.
