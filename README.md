# HMD

Simple shell script to fetch notes from hackmd and render them in the terminal.

## Features

- Simple readable bash shell script.
- Support alias of note id.
- Support caching to reduce API usage.

## Install

Dependencies

- [jq](https://jqlang.github.io/jq/) for json parsing.
- [glow](https://github.com/charmbracelet/glow) for rendering markdown in the terminal.

Since it is a single shell script, just copy or sym-link the hmd file to any directory in your $PATH and give it executable permission.

```sh
cp ./hmd ~/.local/bin/
chmod +x ~/.local/bin/hmd
```

## Configuration

hmd has 2 configuration files in `~/.config/hmd/`. The first is the file called `token`. Follow this [guide](https://hackmd.io/@hackmd-api/how-to-issue-an-api-token) to obtain the API token and store it in `~/.config/hmd/token`. (Note: Do not share your token with others!)

The other configuration file is `~/.config/hmd/config`, here is the example config:

```
Foo xNFcp4o-SuSd7CFu3uxfkA
```

Each line in the config consists of 2 columns separated by a space. The first column is the alias, the second is the note id. With the configuration file, you can invoke hmd like this: `hmd Foo`. It will fetch the note `https://hackmd.io/xNFcp4o-SuSd7CFu3uxfkA`
