CMUS-D (C* Music Player Daemon)
===============================

This package provides a remote graphical frontend for the [C* Music Player][cmus] using the `MPRIS D-Bus Interface`

How it works
------------
`cmus` has a remote tool [cmus-remote(1)](https://linux.die.net/man/1/cmus-remote) that can control and query `cmus` through a socket.
`cmusd` takes advantage of this by parsing the status of `cmus` on request and sending playback controls to it.
This data is updated twice every second for precision.

# Features
* Album art: This is generated and rendered after being extracted by `ffmpeg`
* Playback (Next, Previous, Pause, Play, PlayPause, Stop, Seek)
* Hybrid Connection: The daemon can either spawn a `cmus` process within itself or connect to an already active one
* Auto logging

Installing
----------
The project is written in Native JavaScript [NodeJS](https://github.com/nodejs/node).
[Download and install Node.js, NPM](https://nodejs.org/en/download/).

### Via [NPM][npm]
``` bash
$ npm install cmusd -g
```
### Manual Installatiion
``` bash
$ git clone https://gitlab.com/Miraclx/cmusd.git
$ cd cmusd
$ npm run setup
```

Usage
-----
``` bash
$ # Launch the daemon
$ cmusd

$ # Clean all logfiles, quit
$ cmusd -x

$ # Remove the lockfile, quit
$ # (incase previous process didn't close correctly)
$ cmusd -q

$ # Write log to specific file
$ cmusd <filename>

$ # Write log to file in folder
$ cmusd <folder>
```

* Lock file: `<os-tmp-dir>/cmus-dir/.lock`
* Album Art cache folder: `<os-tmp-dir>/cmus-dir/`
* Default log folder: `<os-tmp-dir>/cmus-dir/logs/`

# Screenshots
## `Simple Command`
![CMUS-D Simple Command](./screenshots/cmusd.png "CMUS-D Simple Command")
## `Basic Run, spawns cmus within (if not already running)`
![cmus in terminal, spawned from cmusd](./screenshots/cmusd-spawn.png "CMUS-D Spawning a cmus process within itself (if not already running)")
## `Media player instance`
![KDE Media Player displaying cmus music data](./screenshots/mpris-player.png "KDE Media Player displaying cmus music data")

# Connect to an actively running cmus process
![CMUS-D Basic Use](./screenshots/cmusd-connect.png)

## `Already running CMUS`
![CMUS running on another terminal window](./screenshots/cmus-solo.png)

## `CMUS-D Connected and logging`
![CMUS-D connected and logging](./screenshots/cmusd-logs.png)

## `Media player instance`
![KDE Media Player displaying cmus music data](./screenshots/mpris-connect.png)


## Development
### Building
Use in adherance to the [license][license], feel free to send some pull requests
```
$ git clone https://github.com/Miraclx/cmusd.git
$ cd cmusd
$ npm install
$ # hack on code
$ npm run build
```

## About
License: [Apache 2.0][license]

Miraculous Owonubi: [[email]](mailto:omiraculous@gmail.com) <https://github.com/Miraclx>

[npm]:  https://github.com/npm/npm "The Node Package Manager"
[cmus]:  https://github.com/cmus/cmus "C* Music Player"
[license]:  LICENSE "Apache 2.0 License"
