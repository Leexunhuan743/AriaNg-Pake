# AriaNg-Pake

> **每周自动用 Pake 打包 AriaNg 为 Windows 可安装版本**

[![License](https://img.shields.io/github/license/mayswind/AriaNg.svg?style=flat)](https://github.com/mayswind/AriaNg/blob/master/LICENSE)
[![Build Status](https://github.com/Leexunhuan743/AriaNg-Pake/actions/workflows/build-release.yml/badge.svg)](https://github.com/Leexunhuan743/AriaNg-Pake/actions/workflows/build-release.yml)

## 📖 本项目说明（中文）

**AriaNg-Pake** 是 [AriaNg](https://github.com/mayswind/AriaNg)（aria2 的现代化 Web 前端）的一个衍生分支。

本项目的核心特点：**每周自动使用 [Pake](https://github.com/tw93/Pake) 将 AriaNg 打包成一个可直接安装的 Windows 桌面客户端（.msi），并发布 Release。**

[Pake](https://github.com/tw93/Pake) 是一款基于 Rust + Tauri 的网页打包工具，打包出的桌面应用仅 ~5MB，比 Electron 小近 20 倍，内存占用更低、启动更快。

### 自动化流水线

| 时间 | 任务 |
|---|---|
| 每周一 **00:00 UTC** | 自动检测 [mayswind/AriaNg](https://github.com/mayswind/AriaNg) 上游更新，有变化则创建 PR |
| 每周一 **06:00 UTC** | 自动构建并发布三个版本到 Release |

### 本次构建产出的三个版本

| 版本 | 文件 | 说明 |
|---|---|---|
| **Standard** | `AriaNg-Standard.zip` | 标准 Web 版，适用于部署到 Web 服务器，按需加载 |
| **All-In-One** | `AriaNg-AllInOne.zip` | 单文件版，解压后双击 `index.html` 即可在浏览器中使用 |
| **Pake Desktop** | `AriaNg.msi` | 🎯 **Windows 桌面客户端**（双击安装，含系统托盘、独立窗口、深色模式） |

### 下载

前往 [Releases](https://github.com/Leexunhuan743/AriaNg-Pake/releases) 页面下载最新版本。

---

# AriaNg

[![License](https://img.shields.io/github/license/mayswind/AriaNg.svg?style=flat)](https://github.com/mayswind/AriaNg/blob/master/LICENSE)
[![Lastest Build](https://img.shields.io/circleci/project/github/mayswind/AriaNg.svg?style=flat)](https://circleci.com/gh/mayswind/AriaNg/tree/master)
[![Lastest Release](https://img.shields.io/github/release/mayswind/AriaNg.svg?style=flat)](https://github.com/mayswind/AriaNg/releases)

## Introduction

AriaNg is a modern web frontend making [aria2](https://github.com/aria2/aria2) easier to use. AriaNg is written in pure html & javascript, thus it does not need any compilers or runtime environment. You can just put AriaNg in your web server and open it in your browser. AriaNg uses responsive layout, and supports any desktop or mobile devices.

## Features

1. Pure Html & Javascript, no runtime required
2. Responsive design, supporting desktop and mobile devices
3. User-friendly interface
    * Sort tasks (by name, size, progress, remaining time, download speed, etc.), files, bittorrent peers
    * Search tasks
    * Retry tasks
    * Adjust task order by dragging
    * More information of tasks (health percentage, client information of bt peers, etc.)
    * Filter files by specified file types (videos, audios, pictures, documents, applications, archives, etc.) or file extensions
    * Tree view for multi-directory task
    * Download / upload speed chart for aria2 or single task
    * Full support for aria2 settings
4. Dark theme
5. Url command line api support
6. Download finished notification
7. Multi-languages support
8. Multi aria2 RPC host support
9. Exporting and Importing settings support
10. Less bandwidth usage, only requesting incremental data

## Screenshots

#### Desktop
![AriaNg](https://raw.githubusercontent.com/mayswind/AriaNg-WebSite/master/screenshots/desktop.png)
#### Mobile Device
![AriaNg](https://raw.githubusercontent.com/mayswind/AriaNg-WebSite/master/screenshots/mobile.png)

## Installation

AriaNg now provides three versions, standard version, all-in-one version and [AriaNg Native](https://github.com/mayswind/AriaNg-Native). Standard version is suitable for deployment in the web server, and provides on-demand loading. All-In-One version is suitable for local using, and you can download it and just open the only html file in browser. [AriaNg Native](https://github.com/mayswind/AriaNg-Native) is also suitable for local using, and is no need for browser.

#### Prebuilt release

Latest Release: [https://github.com/mayswind/AriaNg/releases](https://github.com/mayswind/AriaNg/releases)

Latest Daily Build (Standard Version): [https://github.com/mayswind/AriaNg-DailyBuild/archive/master.zip](https://github.com/mayswind/AriaNg-DailyBuild/archive/master.zip)

#### Building from source

Make sure you have [Node.js](https://nodejs.org/), [NPM](https://www.npmjs.com/) and [Gulp](https://gulpjs.com/) installed. Then download the source code, and follow these steps.

##### Standard Version

    $ npm install
    $ gulp clean build

##### All-In-One Version

    $ npm install
    $ gulp clean build-bundle

The builds will be placed in the dist directory.

#### Usage Notes

Since AriaNg standard version loads language resources asynchronously, you may not open index.html directly on the local file system to run AriaNg. It is recommended that you can use the all-in-one version or deploy AriaNg in a web container or download [AriaNg Native](https://github.com/mayswind/AriaNg-Native) that does not require a browser to run.

## Translating

Everyone is welcome to contribute translations. All translations files are put in `/src/langs/`. You can just modify and commit a new pull request.

If you want to translate AriaNg to a new language, you can add language configuration to `/src/scripts/config/languages.js`, then copy `/i18n/en.sample.txt` to `/src/langs/` and rename it to the language code to be translated, then you can start the translation work.

Currently available translations:

| Tag | Language | Contributors |
| --- | --- | --- |
| cz-CZ | Čeština | [@vorm04](https://github.com/vorm04) |
| de-DE | Deutsch | [@Malonsow](https://github.com/Malonsow) |
| en | English | / |
| es | Español | [@castillofrancodamian](https://github.com/castillofrancodamian) |
| fr-FR | Français | [@Valaraukar86](https://github.com/Valaraukar86) |
| it-IT | Italiano | [@ale-saglia](https://github.com/ale-saglia) |
| ja-JP | 日本語 | [@massangoDa](https://github.com/massangoDa) |
| pl-PL | Polski | [@Pirania3680](https://github.com/Pirania3680) |
| ru-RU | Русский | [@gazizovemil](https://github.com/gazizovemil) |
| zh-Hans | 简体中文 | / |
| zh-Hant | 繁體中文 | [@zhtw2013](https://github.com/zhtw2013) [@ChiaYen-Kan](https://github.com/ChiaYen-Kan) |

Don't see your language? Help us add it!

## Documents

1. [English](http://ariang.mayswind.net)
2. [Simplified Chinese (简体中文)](http://ariang.mayswind.net/zh_Hans)

## Demo

Please visit [http://ariang.mayswind.net/latest](http://ariang.mayswind.net/latest)

## Third Party Extensions

There are some third-party applications based on AriaNg, so you can use AriaNg in more scenarios or devices. Please visit [Third Party Extensions](http://ariang.mayswind.net/3rd-extensions.html) for more information.

## License

[MIT](https://github.com/mayswind/AriaNg/blob/master/LICENSE)
