# WALLPAP-ENG-resource

![](https://img.shields.io/steam/collection-files/1865840540?style=flat-square&label=items)  
[![](https://img.shields.io/static/v1?style=for-the-badge&message=atom&color=222222&logo=RSS&logoColor=FFA500&label=)](https://github.com/scillidan/WALLPAP-ENG-resource/commits/main.atom)

resource of [Wallpaper Engine](https://www.wallpaperengine.io/).  
Almost all come from favorite anime. uploaded them many years ago, and recently carried out "garbage collection".  
See [table.md](/table.md) to get some stream-data.  
See [name.csv](/data_name.csv) and [source.csv](/data_source.csv) to get more information.

## Tools

- [qBittorrent Enhanced Edition](https://github.com/c0re100/qBittorrent-Enhanced-Edition)
- [Jackett](https://github.com/Jackett/Jackett)
- [FFmpeg Batch AV Converter](https://github.com/eibol/ffmpeg_batch)
- [HandBrake](https://handbrake.fr)
- [Handbrake Watcher](https://github.com/shannah/handbrake-watcher)
- ...

## Witchcraft 🧙

replace `^` with `\` in `bash`.

```cmd
curlie -k https://raw.githubusercontent.com/scillidan/WALLPAP-ENG-resource/main/table.md ^
  | sd "\[\d{10}\]\(" "" ^
  | sd "(\)\|\S+subsc)" "|![](//img.shields.io/steam/subsc" ^
  | mdtable2csv ^
  | sd "//steamc" "https://steamc" ^
  | xsv select source,version,urlid ^
  | csview
````

![](https://raw.githubusercontent.com/scillidan/repo_cos/main/screenshot/WALLPAP-ENG-resource_cmd.png)

## No License

All these videos on [steamcommunity](https://steamcommunity.com/), their copyrights belong to the original producer, etc 👮