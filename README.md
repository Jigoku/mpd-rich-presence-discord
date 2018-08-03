
<center>
    <img align="right" src="assets/readme/header.png">
</center>

<h1 align="center">
    <a href="https://github.com/SSStormy/mpd-rich-presence-discord">MPD Rich Presence for Discord</a>
</h1>

<p align="center">
    <b>Broadcast MPD state via Discord Rich Presence</b>
</p>

<hr>

<p align="center">
  AUR:
  <a href="https://aur.archlinux.org/packages/mpd-rich-presence-discord-git/" target="_blank">
    <img src="http://badge.kloud51.com/aur/v/mpd-rich-presence-discord-git.svg" alt="AUR Version"/>
  </a>
  
  <a href="https://aur.archlinux.org/packages/mpd-rich-presence-discord-git/" target="_blank">
    <img src="http://badge.kloud51.com/aur/s/mpd-rich-presence-discord-git.svg" alt="AUR Status"/>
  </a>
  
  <a href="https://aur.archlinux.org/packages/mpd-rich-presence-discord-git/" target="_blank">
    <img src="http://badge.kloud51.com/aur/m/mpd-rich-presence-discord-git.svg" alt="AUR Status"/>
  </a>
  
  <dl>
    <dt><a href="#images">Images</a></dt>
    <dd><a href="#single-app-mode">Single App Mode</a></dd>
    <dd><a href="#multi-app-mode">Multi App Mode</a></dd>
    <dt><a href="#multi-app-vs-single-app-mode">Multi App vs Single App Mode</a></dt>
    <dt><a href="#command-line-arguments">Command Line Arguments</a></dt>
    <dt><a href="#compiling">Compiling</a></dt>
    <dt><a href="#similar">Similar</a></dt>
  </dl>
</p>

---

## Images

### Single App Mode
| State | Image |
| :-: | :-: |
| Playing | ![Playing](assets/readme/single-playing.png)
| Paused | ![Paused](assets/readme/single-paused.png)
| Idle | ![Idle](assets/readme/single-idle.png)

### Multi App Mode

| State | Image |
| :-: | :-: |
| Playing | ![Playing](assets/readme/multi-playing.png)
| Paused | ![Paused](assets/readme/multi-paused.png)
| Idle | ![Idle](assets/readme/multi-idle.png)

---

## Multi App vs Single App Mode
* Single App Mode

  * This mode will use one sindle MPD app. The three different MPD states (Playing, paused and idle) will be displayed via this app.
  
  * This mode syncs faster than the multi app mode.
  
* Multi App Mode

  * This mode will use multiple different MPD apps: 
    * `MPD (Playing)`
    * `MPD (Paused)`
    * `MPD` (reserved for idle)
  
  * These app names will show up next to your name on the sidebar.
  
  * This mode syncs slower than the single app mode.

---

## Command Line Arguments

Example: `mpd_discord_richpresence -h=211.111.111.112 -P=password -p=6606 --fork --no-idle --use-multiple-apps`

| Paramater| Purpose  |
|--|--|
|`-h=ADDDRESS`|  the address where the MPD server (defaults to `127.0.0.1`)|
|`-p=PORT`|the port on which the target MPD server is listening  (defaults to `6600`)|
|`-P=PASSWORD`|the password to be sent after connection to the MPD server has been established in hopes of acquiring higher permissions. (default is empty, therfore no password sent.)|
|`--fork`|forks the process into the background.|
|`--no-idle`|Disables broadcasting of the idle state.|
|`--use-multiple-apps`| Uses the Multi App mode.|

---

## Compiling

### Dependencies
* pthread
* [discord-rpc](https://github.com/discordapp/discord-rpc)
* libmpdclient

A [build script](build.sh) is included.

The CMakeFile will take care of finding discord-rpc. If it cannot find it, it will pull the discordrpc github repo and compile from source.

---

## Similar

* [mpv-discordRPC, noaione](https://github.com/noaione/mpv-discordRPC) - MPV
* [foo_discord, NaamloosDT/](https://github.com/NaamloosDT/foo_discord) - foobar2000 rich presence
