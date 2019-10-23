# ws-cli

[![npm](https://img.shields.io/npm/v/@danhab99/ws-cli)](https://github.com/danhab99/ws-cli)
[![GitHub forks](https://img.shields.io/github/forks/danhab99/ws-cli)](https://github.com/danhab99/ws-cli)
[![GitHub Release Date](https://img.shields.io/github/release-date/danhab99/ws-cli) ![github](https://img.shields.io/github/v/release/danhab99/ws-cli)](https://github.com/danhab99/ws-cli/releases)
[![npm](https://img.shields.io/npm/dw/@danhab99/ws-cli)](https://www.npmjs.com/package/@danhab99/ws-cli)
[![stars](https://img.shields.io/github/stars/danhab99/ws-cli)](https://github.com/danhab99/ws-cli)

An interactive websocket utility suite

- [ws-cli](#ws-cli)
  - [Installation](#installation)
  - [Usage](#usage)
    - [wscli](#wscli)
      - [As a client](#as-a-client)
      - [As a server](#as-a-server)
    - [wstee](#wstee)
      - [Note](#note)

## Installation

```bash
npm i -g @danhab99/ws-cli
```

## Usage

### wscli

wscli provides an interactive websocket client/server

```bash
Usage: wscli [options] [command]

Options:
  -V, --version       output the version number
  -p, --pipe-stdin    Pipe stdin to server and server to stdout
  -t, --tab-size <t>  Set the tab size (default: 2)
  -i, --in <files>    Use files as input (default: [])
  -o, --out <file>    Output to file
  -u, --ugly          No pretty print
  -h, --help          output usage information

Commands:
  listen <port>       Listen for websocket connections on a port
  connect <address>   Connect to a websocket at an address
```

#### As a client

Run `ws-cli connect [host]`. Once you see the `!!! Connected` message, press `h` for help, all further commands are triggered by the correct keypress.

```

      [s] send a message to server

```

#### As a server

Run `ws-cli listen [port]`, press `h` for help

```

      [s] open select prompt, used to select which connections are being displayed and will receive transmit messages. comma seperated numbers
      [S] print selected clients
      [t] transmits message to selected clients
      [b] broadcasts message to all clients
      [k] close selected clients
   
```

### wstee

`wstee` provides a proxy websocket for monitoring websocket connections. By default it will pipe stdio to the websocket although files can be provided as in/output

```
Usage: wstee [options]

Options:
  -V, --version                         output the version number
  -p, --pipe-stdin                      Pipe stdin to server and server to stdout
  -t, --tab-size <t>                    Set the tab size (default: 2)
  -i, --in <files>                      Use files as input (default: [])
  -o, --out <file>                      Output to file
  -u, --ugly                            No pretty print
  -r, --rebroadcast                     Rebroadcasts every client's message to every other client
  --connect-incoming <port or address>  Open a port to allow one client to connect (default: [])
  --connect-outgoing <port or address>  Connect to server  (default: [])
  -h, --help                            output usage information
```

#### Note

When using `-p`, `wstee` will instead display the bitrate of data being transfered
