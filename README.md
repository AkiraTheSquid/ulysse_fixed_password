# Ulysse (Fixed Password Fork)

[![License](https://img.shields.io/badge/license-GPL%20v3%2B-yellow.svg?label=License&style=flat&colorA=2B323B&colorB=1e2329)](https://raw.githubusercontent.com/johackim/ulysse/master/LICENSE.txt)

> This is a fork of [getulysse/ulysse](https://github.com/getulysse/ulysse) with a fix for the password setup bug.

Ulysse is a simple CLI tool for blocking your distracting apps and websites.

Prevent distractions by blocking your most distracting apps and websites, even if you are the administrator of your computer.

## Bug Fix

The original version had a bug where `ulysse shield enable` would not prompt the user to create a password. This meant users could enable shield mode without setting a password, and then be unable to disable it (since it always asks for a password to disable).

**This fork fixes that issue** - you will now be prompted to create a password when enabling shield mode.

> [!WARNING]
> The shield mode block root access to your computer and can block you from disabling Ulysse.
>
> Make sure to remember your password.
>
> If you are blocked, you can still disable Ulysse by running the following commands from a live USB:
>
> ```bash
> rm /etc/sudoers.d/ulysse
> usermod -s /bin/bash root # Or edit /etc/passwd file
> echo 'nameserver 9.9.9.9' | tee /etc/resolv.conf
> ```

## 📋 Requirements

- X11
- Linux
- Systemd
- Node.js >= 14.0.0

## ✨ Features

- [x] Block your distracting apps and websites
- [x] Shield mode (no way to bypass)

## Installation

```bash
npm i -g ulysse-fixed
```

## 📖 Usage

```txt
Usage: ulysse [options] [command]

A simple CLI tool for blocking your distracting apps and websites.

Options:
  -v, --version   Show the version and exit
  -h, --help      Show this help message and exit

Commands:
  daemon          Start the Ulysse daemon
  blocklist       Manage the blocklist
  whitelist       Manage the whitelist
  shield          Enable or disable the shield mode
  help [command]  display help for command

Examples:
  ulysse daemon start
  ulysse blocklist add --app firefox
  ulysse whitelist add --website wikipedia.org
  ulysse blocklist add --website youtube.com -t 8h-20h
  ulysse shield enable
```

## Credits

This is a fork of the original [Ulysse](https://github.com/getulysse/ulysse) by [johackim](https://github.com/johackim). Please consider supporting the original author:

[![Github sponsor](https://img.shields.io/badge/github-Support%20original%20author-lightgrey?style=social&logo=github)](https://github.com/sponsors/johackim/)

## 📜 License

This project is licensed under the GNU GPL v3.0 - see the [LICENSE.txt](https://raw.githubusercontent.com/johackim/ulysse/master/LICENSE.txt) file for details

**Free Software, Hell Yeah!**
