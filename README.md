# Friday Night Funkin v0.2.8 (Newgrounds Exclusive)

This is the repository for Friday Night Funkin' v0.2.8, a game in which lies on a singular web page on the internet with no open-source code.

This project is the result of reverse engineering the transpiled JavaScript code into readable Haxe code, which can now be built upon with ease.

# Our goals

This project aims to bring v0.2.8 back into Haxe as close as possible to the original.

This means bugs and other issues with v0.2.8 in general are not being fixed.

Any issues regarding these types of bugs (e.g. Cutscenes not working on desktop) will receive a `wontfix` label and be immediately closed.

Any errors on my part though will be fixed as soon as I notice them. If you catch something before I do, [please open an issue regarding the error](../../issues).

# Important notes

To not mess with any of the integrations Ninjamuffin had in place, I have decided to completely remove them from the project.

What's missing? Logins, awards, and a check to see if the game is outdated or not. Other than that though, the repo should be mostly accurate to how to game is shown on the website.

If demand is high enough, I may make a separate branch for you to enter in your own Newgrounds API keys and bring these features back. We'll see.

# Support Friday Night Funkin'

Play the Ludum Dare prototype here: https://ninja-muffin24.itch.io/friday-night-funkin

Play the Newgrounds one here: https://www.newgrounds.com/portal/view/770371

Support the project on the itch.io page: https://ninja-muffin24.itch.io/funkin

Support the project on the Kickstarter page: https://www.kickstarter.com/projects/funkin/friday-night-funkin-the-full-ass-game

## Credits / shoutouts

- [ninjamuffin99](https://twitter.com/ninja_muffin99) - Programmer
- [PhantomArcade3K](https://twitter.com/phantomarcade3k) and [Evilsk8r](https://twitter.com/evilsk8r) - Art
- [Kawaisprite](https://twitter.com/kawaisprite) - Musician
- [AngelDTF (me!)](https://github.com/AngelDTF) - Reverse engineering

## Build instructions

THESE INSTRUCTIONS ARE FOR COMPILING THE GAME'S SOURCE CODE!!!

IF YOU WANT TO JUST DOWNLOAD AND INSTALL AND PLAY THE GAME NORMALLY, [GO TO THE RELEASES PAGE](../../releases) AND DOWNLOAD PRECOMPILED PACKAGES FROM THERE!

IF YOU WANT TO COMPILE THE GAME YOURSELF, CONTINUE READING!!!

### Installing the Required Programs

First you need to install Haxe and HaxeFlixel. I'm too lazy to write and keep updated with that setup (which is pretty simple). 
1. [Install Haxe](https://haxe.org/download/) (If you're having issues installing libraries on latest, try using [Haxe 4.1.5](https://haxe.org/download/version/4.1.5/) instead)
2. [Install HaxeFlixel](https://haxeflixel.com/documentation/install-haxeflixel/) after downloading Haxe

Other installations you'd need is the additional libraries, a fully updated list will be in `Project.xml` in the project root. Currently, these are all of the things you need to install:
```
flixel
flixel-addons
flixel-ui
hscript
```
So for each of those type `haxelib install [library]` so shit like `haxelib install flixel`

You'll also need to install a couple things that involve Gits. To do this, you need to do a few things first.
1. Download [git-scm](https://git-scm.com/downloads). Works for Windows, Mac, and Linux, just select your build.
2. Follow instructions to install the application properly.
3. Run `haxelib git polymod https://github.com/larsiusprime/polymod.git` to install Polymod.
4. Run `haxelib git discord_rpc https://github.com/Aidan63/linc_discord-rpc` to install Discord RPC.

At the moment, you can optionally fix some bugs regarding the engine:
1. A transition bug in songs with zoomed out cameras
- Run `haxelib git flixel-addons https://github.com/HaxeFlixel/flixel-addons` in the terminal/command-prompt.
2. A text rendering bug (mainly noticeable in the story menu under tracks)
- Run `haxelib git openfl https://github.com/openfl/openfl` in the terminal/command-prompt.

You should have everything ready for compiling the game! Follow the guide below to continue!

### Compiling game

Once you have all those installed, it's pretty easy to compile the game. You just need to run 'lime test html5 -debug' in the root of the project to build and run the HTML5 version. (command prompt navigation guide can be found here: [https://ninjamuffin99.newgrounds.com/news/post/1090480](https://ninjamuffin99.newgrounds.com/news/post/1090480))

To run it from your desktop (Windows, Mac, Linux) it can be a bit more involved. For Linux, you only need to open a terminal in the project directory and run 'lime test linux -debug' and then run the executable file in export/release/linux/bin. I'll add instructions for Mac once I get my hands on a macOS device. For Windows, you need to install [Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/?q=Build+Tools) (you'll need to scroll down a bit to find the download). While installing, don't click on any of the options to install workloads. Instead, go to the individual components tab and choose the following:
* MSVC C++ x64/x86 build tools (Tested with `MSVC v143 - VS 2022 C++ x64/x86 build tools (v14.33-17.3)`)
* Windows SDK (Tested with `Windows 10 SDK (10.0.19041.0)`)

This will install about 4GB of crap, but once that is done you can open up a command line in the project's directory and run `lime test windows -debug`. Once that command finishes (it takes forever, even on a higher end PC), you can run FNF from the .exe file under export\release\windows\bin
As for Mac, 'lime test mac -debug' should work, if not the internet surely has a guide on how to compile Haxe stuff for Mac.

### Additional guides

- [Command line basics](https://ninjamuffin99.newgrounds.com/news/post/1090480)
