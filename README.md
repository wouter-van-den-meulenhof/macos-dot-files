# MacOS dot- & configuration files

Personal collection of dot- and configuration files that I use when configuring a new MacBook.

## Description

This repository contains a collection of dot- and configuration files that I use when configuring a new MacBook. Please note that this repository is intentionally opinionated and tailored to my specific workflow.

### Files

I use the `homebrew` package manager to install and update the software. My preferred text editor is `Vim` and `Ghostty` is my terminal emulator of choice. The files in the `/macos` directory contain the configuration files for these apps.

| File | Path | Description |
| --- | --- | --- |
| Homebrew bundle | `macos/Brewfile` | Installs the software and applications used on the workstation. |
| Shell config | `macos/.zshrc` | Zsh shell configuration, aliases, and customizations. |
| Git config | `macos/.gitconfig` | Git user settings and defaults. |
| Vim config | `macos/.vimrc` | Vim editor preferences. |
| Oh My Posh theme | `macos/.oh-my-posh.json` | Prompt theme configuration. |
| Shell startup | `macos/.hushlogin` | Disables the default shell welcome message. |
| App config directory | `macos/.config/` | Additional application-specific configuration files, including Ghostty terminal settings. |
| Ghostty config | `macos/.config/ghostty/config.ghostty` | Terminal configuration for Ghostty. |
| Ghostty themes | `macos/.config/ghostty/themes/` | Custom Ghostty color themes. |

## Usage

First install [homebrew](https://brew.sh/) by running their installation script.

Then, extract the contents of the `/macos` directory verbatim to the root of your home home directory by running the following one liner (note that MacOS ships with jq installed by default):

```zsh
curl -sL https://api.github.com/repos/wouter-van-den-meulenhof/dot-files/contents/macos \
   | jq -r '.[] | .download_url'                                                        \
   | xargs -n1 curl -sLO
```

Finally, run the following command to install tools and apps:

```zsh
brew bundle --file="~/Brewfile"
```

After installing and running the bundle command, follow [beerisgood's](https://github.com/beerisgood) [MacOS hardening guide](https://github.com/beerisgood/macOS_Hardening) and apply the recommended hardenings, bar the one telling you not to use Homebrew.

Lastly I install Podman using the (recommended) Installer method. It kan be found on the Podman project's [website](https://podman.io/docs/installation).

## Author

Wouter van den Meulenhof [noneya@business.com]
