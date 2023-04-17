---
layout: post
title:  "Installing OctoPrint on MacOS"
date:   2023-04-17 11:00:00 +0000
categories:  printing
---

This post is primarily a collection of notes that I have from installing [OctoPrint](https://octoprint.org/) on a Mac Mini I had laying around. It's not meant as an exhaustive use guide. More a single point of reference for all of the pieces I had to go find or bridge gaps.

## What is OctoPrint?

From their [GitHub](https://github.com/OctoPrint/OctoPrint)...

> OctoPrint provides a snappy web interface for controlling consumer 3D printers. It is Free Software and released under the [GNU Affero General Public License V3](https://www.gnu.org/licenses/agpl-3.0.html).

More practically, it's a slick way to manage your 3d printer remotely. It also gives you neat features like time lapses. It also makes it so you're not always shuffling MicroSD cards from one side of the room (or room to room) to make small prints or after you've made changes when you realized you had the slicer settings for your kid's printer and not yours...

## Hardware Involved

* Late 2014 Mac Mini
  * macOS Monterey (12.6.5)
  * 3 GHz Dual-Core Intel Core I7
  * 16 GB RAM
* Creality Ender 3 V2
  * Firmware 1.0.8
  * Completely Stock (*At the time of writing.*)

## Setup

This is all much easier if you already have the [Mac setup to be used headless](https://www.imore.com/how-set-your-new-mac-mini-use-without-monitor), if that's how you're going to use it, I'm not going to detail that here though. 

### Install Homebrew

This should just be a default on everyone's Mac, but if you don't already have it...install it now and thank me later. 

```console
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Xcode CLI Tools

Just to make sure that you have all of the tools required for Git, we'll make sure they're installed and that you've accepted the licensing agreement.

```console
xcode-select --install && sudo xcodebuild
```

### Install Python

Python should be installed by default. You can check by grabbing the version of Python currently installed. 

```console
python3 --version
```

Which will either fail miserably or give you a something like: `Python 3.11.2`

If it fails miserably, use Homebrew to install Python. 

```console
brew install python
```

### Install pip

There seems to be an assumption that `pip` is installed by default, but it wasn't the case for me. 

You can check for `pip` on your machine. 

```console
pip -V
```

Again, if it's installed you'll receive a response like: `pip 23.1 from /usr/local/lib/python3.11/site-packages/pip (python 3.11)`

If it's not present, we'll download a helper file and install it. 

```console
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3 get-pip.py
```

### Install virtualenv

`virtualenv` provides an isolated environment for the Python application to run. At some point, I may go back and re-think this part, but it works really well right now so I'll go with it until I figure something else out/am not currently printing parts for my printer.

```console
pip install virtualenv
```

## Running OctoPrint

Alright, now that everything is in place, let's run the dang thing. 

First, create a directory to hold all of the files. 

```console
mkdir OctoPrint && cd OctoPrint
```

Second, we'll create the virtual environment.

```console
virtualenv venv
```

Now that it's created, we'll jump into that environment and install the actual OctoPrint package inside of it. 

```console
source venv/bin/activate && pip install -U pyobjc && pip install OctoPrint
```

Lastly, we need to do is run the application. 

```console
octoprint serve
```

If all has gone to plan, you should now be able to open a browser and go to localhost:5000 and you'll be greeted with the OctoPrint setup page. 

### Autostart

**I have not tested this bit yet, but there are instructions in the sources. I'll come back and update this once I've validated it works.** 

## Closing

I'll save the tutorials and how to use for OctoPrint.org (I don't know that I could do it justice). You should only be a USB cable away from hitting "connect to printer" and enjoying all of the features. 

## Sources
* [Brew.sh](https://brew.sh/)
* [Setting up OctoPrint on MacOS](https://community.octoprint.org/t/setting-up-octoprint-on-macos/13425)
* [pip documentation](https://pip.pypa.io/en/stable/installation/)
