# WALLPAP-ENG-resource

![](https://img.shields.io/steam/collection-files/1865840540?style=flat-square&label=items)

resource of [Wallpaper Engine](https://www.wallpaperengine.io/).  
Almost all come from favorite anime. uploaded them many years ago, and recently carried out "garbage collection".  
See [data.md](/data.md) to get some stream-data.  
See [name.csv](/name.csv) and [source.csv](/source.csv) to get more information.

## Tools

- [qBittorrent Enhanced Edition](https://github.com/c0re100/qBittorrent-Enhanced-Edition)
- [Jackett](https://github.com/Jackett/Jackett)
- [FFmpeg Batch AV Converter](https://github.com/eibol/ffmpeg_batch)
- [HandBrake](https://handbrake.fr)
- [Handbrake Watcher](https://github.com/shannah/handbrake-watcher)
- ...

## No License

All these videos on [steamcommunity](https://steamcommunity.com/), their copyrights belong to the original producer, etc 👮

## Todo

- [x] merge collections on steamcommunity
- [x] supplement the information of song
- [ ] clean up the names and introductions on the page

## Witchcraft 🧙

replace `^` with `\` in `bash`.

```cmd
curlie -k https://raw.githubusercontent.com/scillidan/WALLPAP-ENG-resource/main/data.md ^
  | sd "\[\d{10}\]\(" "" ^
  | sd "(\)\|\S+subsc)" "|![](//img.shields.io/steam/subsc" ^
  | mdtable2csv ^
  | sd "//steamc" "https://steamc" ^
  | xsv select source,version,urlid ^
  | csview
````

![](_media/WALLPAP-ENG-resource.png)