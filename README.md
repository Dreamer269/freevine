<h3 align="center">Freevine<br/>
<sup>A Download Utility for Free Streaming Services</sup></h3>
<p align="center">
    <a href="https://python.org">
        <img src="https://img.shields.io/badge/python-3.9+-blue" alt="Python version">
    </a>
    <a href="https://docs.python.org/3/library/venv.html">
        <img src="https://img.shields.io/badge/python-venv-blue" alt="Python virtual environments">
    </a><br/>
    <a href='https://ko-fi.com/A0A2MZDCO' target='_blank'><img height='30' style='border:0px;height:30px;' src='https://storage.ko-fi.com/cdn/kofi3.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>
</p>

## Features:

- [x] Movies & TV-series
- [x] Episode selection and batch options
- [x] Quality selection
- [x] Automatic PSSH, manifest, and key retreival 
- [x] Config file with customized settings
- [x] Search option
- [x] Proxy option
- [x] Option to add login credentials with user profile or cookies 
- [x] [Supported sites](https://github.com/stabbedbybrick/freevine/blob/main/supportedsites.md)

## Requirements:

* [Python](https://www.python.org/)

* [N_m3u8DL-RE](https://github.com/nilaoda/N_m3u8DL-RE/releases/)

* [ffmpeg](https://ffmpeg.org/)

* [mkvmerge](https://mkvtoolnix.download/downloads.html)

* [mp4decrypt](https://www.bento4.com/downloads/)

* [shaka packager](https://github.com/shaka-project/shaka-packager)

* [hola-proxy](https://github.com/Snawoot/hola-proxy) (optional)

* Valid Widevine CDM (only needed for encrypted streams)

> [!TIP]
> Windows users are recommended to use Powershell 7 in Windows Terminal for best experience

## Installation:

1. Install Python (check 'Add to PATH' if on Windows)
2. Clone main branch or download latest version from [Releases](https://github.com/stabbedbybrick/freevine/releases)
3. Place required tools inside Freevine folder OR add them to system PATH (recommended)
4. Create `/utils/wvd/` folder and place either .wvd file or private_key and client_id blob inside
5. Install necessary packages: `pip install -r requirements.txt`

> [!TIP]
> Clone/download the main branch for immediate fixes and updates

## Usage:

Available commands:

```
Commands:
  clear-cache   Delete download cache
  file          Read commands from a text file
  get           Download series or movies
  profile       Create a profile with user credentials
  search        Search one or multiple services for titles
  service-info  Print information about each streaming service
```

Available arguments for `get` command:

```
  --proxy TEXT                 Request or specify a proxy server
  --threads TEXT               Concurrent download fragments
  --format TEXT                Specify file format
  --muxer TEXT                 Select muxer
  --no-mux                     Choose to not mux files
  --save-name TEXT             Name of saved file
  --save-dir TEXT              Save directory
  --sub-only                   Download only subtitles
  --sub-no-mux                 Choose to not mux subtitles
  --sub-no-fix                 Leave subtitles untouched
  --use-shaka-packager         Use shaka-packager to decrypt
  --add-command TEXT           Add extra command to N_m3u8DL-RE
  --slowdown INTEGER           Add sleep (in seconds) between downloads
  -fn, --force-numbering       Force add numbering to episodes
  -e, --episode TEXT           Download episode(s)
  -s, --season TEXT            Download complete season
  -c, --complete               Download complete series
  -m, --movie                  Download movie
  -t, --titles                 List all titles
  -i, --info                   Print title info
  -sv, --select-video TEXT     Select video stream
  -sa, --select-audio TEXT     Select audio stream
  -dv, --drop-video TEXT       Drop video stream
  -da, --drop-audio TEXT       Drop audio stream
  -ss, --select-subtitle TEXT  Select subtitle
  -ds, --drop-subtitle TEXT    Drop subtitle
```
Examples:

```
freevine.py get --help (READ THIS!)

freevine.py get --titles URL
freevine.py get --movie URL
freevine.py get --info --episode S01E01 URL
freevine.py get --sub_only --episode S01E01 URL
freevine.py get --episode S01E01 URL
freevine.py get --episode "name of episode" URL
freevine.py get --episode EPISODE_URL
freevine.py get --episode S01E01-S01E10 URL
freevine.py get --episode S01E01,S03E12,S05E03 URL
freevine.py get --season S01,S03,S05 URL
freevine.py get --select-video res=720 --season S01 URL
freevine.py get --select-audio name=English --episode S01E01 URL

freevine.py service-info
freevine.py service-info "iplayer"

freevine.py profile --help
freevine.py profile --username "username" --password "password" --service "service"

freevine.py search --help
freevine.py search iplayer "KEYWORDS"

freevine.py clear-cache

```
> [!TIP]
> See "N_m3u8DL-RE --morehelp select-video/audio/subtitle" for possible selection patterns

## Disclaimer

1. This project is purely for educational purposes and does not condone piracy
2. RSA key pair required for key derivation is not included in this project

