# bottom

[![Build Status](https://travis-ci.com/ClementTsang/bottom.svg?token=1wvzVgp94E1TZyPNs8JF&branch=master)](https://travis-ci.com/ClementTsang/bottom) [![crates.io link](https://img.shields.io/crates/v/bottom.svg)](https://crates.io/crates/bottom)

A top clone, written in Rust. Inspired by both [gtop](https://github.com/aksakalli/gtop) and [gotop](https://github.com/cjbassi/gotop)

![Quick demo recording](assets/recording_1.gif)

## Installation

### Linux

You can install by cloning and using `cargo build --release`, or download the pre-compiled binary in Releases.

### Windows

You can currently install by cloning and building yourself using `cargo build --release`. You may need to install a font like [FreeMono](https://fonts2u.com/free-monospaced.font) and use a terminal like cmder for font support to work properly, unfortunately.

### macOS

macOS support will hopefully come soon<sup>TM</sup>.

## Usage

Note that all options and keybindings on GitHub may reflect the current development build, and not that of the current releases. For now, refer to the [crate](https://crates.io/crates/bottom) README for documentation as of time of release.

### Command line options

- `-h`, `--help` shows the help screen and exits.

- `-a`, `--avgcpu` enables also showing the average CPU usage in addition to per-core CPU usage.

- `-m`, `--dot-marker` uses a dot marker instead of the default braille marker.

- `-c`, `--celsius` displays the temperature type in Celsius. This is the default.

- `-f`, `--fahrenheit` displays the temperature type in Fahrenheit.

- `-k`, `--kelvin` displays the temperature type in Kelvin.

- `-v`, `--version` displays the version number and exits.

- `-d`, `--debug` enables debug logging.

- `-r <RATE>`, `--rate <RATE>` will set the refresh rate in _milliseconds_. Lowest it can go is 250ms, the highest it can go is 2<sup>128</sup> - 1. Defaults to 1000ms, and lower values may take more resources due to more frequent polling of data, and may be less accurate in some circumstances.

### Keybindings

#### General

- `q`, `Ctrl-c` to quit.

- `Ctrl-r` to reset the screen and reset all collected data.

- `f` to freeze the screen from updating with new data. Press `f` again to unfreeze. Note that monitoring will still continue in the background.

- `Ctrl+Up/k`, `Ctrl+Down/j`, `Ctrl+Left/h`, `Ctrl+Right/l` to navigate between panels.

- `Up` and `Down` scrolls through the list if the panel is a table (Temperature, Disks, Processes).

- `Esc` to close a dialog window.

- `?` to get a help screen explaining the controls. Note all controls except `Esc` to close the dialog will be disabled while this is open.

#### Processes panel

- `dd` to kill the selected process - **I would highly recommend you to be careful using this, lest you accidentally kill the wrong process**.

- `c` to sort by CPU usage. Sorts in descending order by default. Press again to reverse sorting order.

- `m` to sort by memory usage. Sorts in descending order by default. Press again to reverse sorting order.

- `p` to sort by PID. Sorts in ascending order by default. Press again to reverse sorting order.

- `n` to sort by process name. Sorts in ascending order by default. Press again to reverse sorting order.

### Mouse actions

[* Scrolling either scrolls through the list if the panel is a table (Temperature, Disks, Processes), or zooms in and out if it is a chart.]: <>

- Scrolling currently only scrolls through the list if the panel is a table (Temperature, Disks, Processes). This will change in the future.

## Thanks, kudos, and all the like

- As mentioned, this project is very much inspired by both [gotop](https://github.com/cjbassi/gotop) and [gtop](https://github.com/aksakalli/gtop) .

- This application was written with the following libraries:
  - [chrono](https://github.com/chronotope/chrono)
  - [clap](https://github.com/clap-rs/clap)
  - [crossterm](https://github.com/TimonPost/crossterm)
  - [failure](https://github.com/rust-lang-nursery/failure)
  - [fern](https://github.com/daboross/fern)
  - [futures-rs](https://github.com/rust-lang-nursery/futures-rs)
  - [futures-timer](https://github.com/rustasync/futures-timer)
  - [heim](https://github.com/heim-rs/heim)
  - [log](https://github.com/rust-lang-nursery/log)
  - [sysinfo](https://github.com/GuillaumeGomez/sysinfo)
  - [tokio](https://github.com/tokio-rs/tokio)
  - [tui-rs](https://github.com/fdehau/tui-rs)
  - [winapi](https://github.com/retep998/winapi-rs)
