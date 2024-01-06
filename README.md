# Ballance - Modern Setup and configuration (including Steam Deck)

The Steam release of Ballance is pretty vanilla and in-line with the original release, though for modern audiences who are used to QOL features which have become standard since the release of the game, it requires a bit of tinkering. This guide will hopefully help you get the game up and running both on your PC and your Steam Deck and will cover widescreen resolutions, unlocked framerates and mods.

## BallancePlayer (NewPlayerPatch)

First order of business is using the new [BallancePlayer](https://github.com/doyaGu/BallancePlayer). This is a reverse-engineered effort to make an open-source modern launcher binary for the game which includes new features like custom resolutions and aspect ratios, an unlocked framerate, intro logo skipping and some other tidbits.

First acquire a compiled release using [this MEGA link](https://mega.nz/folder/CV5SyapR#LbduTW51xmkDO4EDxMfH9w/folder/2ZxXSaDB) and download `NewPlayerPatch-v0.3.0.zip`.
Then, proceed with extracting the contents of the zip into your game installation folder as shown in the image. Make sure to extract the archive in the base game directory so all of the `Bin` contents are unzipped in the same folder! You will be prompted to overwrite `Player.exe` - confirm overwriting the file.

`Player.ini` is BallancePlayer's configuration file, and we have quite a bit to play around with here. The main order of business is setting `Width`, `Height`, `UnlockWidescreen`, `Fullscreen` and `SkipOpening`. [Here]() I am providing a sample configuration which I personally use on my Steam Deck and for any Deck users should just be copied and with any further tinkering done to taste afterwards.

## Framerate unlocking
By default, Ballance's internal game speed is tied to the framerate, meaning if you increase the framerate limit using the configuration file, the game becomes much faster (and unplayable). BallanceModLoader alleviates this issue. Thankfully that's just a drag and drop process, including on Linux (no need for launch parameters!).

Simply grab [BallanceModLoaderPlusPatch from here](https://mega.nz/folder/CV5SyapR#LbduTW51xmkDO4EDxMfH9w/file/WIgFVQJI) and once again extract its contents in the game directory. That's it!

You will immediately be able to tell if you've installed it correctly when you launch the game and see `BML PLUS 0.2.3` on top of the screen as pictured in my screenshot, as well as the framerate counter on the top left. In my screenshot, the FPS counter maxes out at 164FPS which is my monitor's output refresh rate, meaning the game will now output at a higher framerate and not have its internal clock speed altered because of that. Note that the displayed mod information in-game can be toggled on and off in the game's settings under `Mods/BML`.

## Custom maps
With BallanceModLoader installed, we're now able to play custom maps through the main menu. Clicking on Start reveals the base game level list, as well as a right arrow off to the side. Custom maps are read from the `Ballance/ModLoader/Maps/` directory. Copy any `.NMO` map files in that directory and upon reboot, you will see them in the side menu of the game.

## Level 13 - The Twilight Zone


## Steam Deck input layout
While the official layout for the game will work just fine, I made my own one which binds the camera toggles to both shoulder buttons (left and right respectively), as well as changing some of the face button bindings. As Steam unfortunately doesn't have a good way of sharing Steam Input layouts via URLs that you can save, I recommend looking up "Ballance - Better Deck Layout" in the Steam Input community layouts section. I encourage you to try it out and change anything to your own taste!

## Save file synchronization (TO-DO?)
This is a big one and I'm debating its inclusion in this guide, seeing as Ballance is not a fairly long game to warrant save file synchronization, but I felt it was necessary to adress it anyway.

Ballance's save file is located in the game's base directory and it's called `Database.tdb`. You can use a program like [Syncthing](https://docs.syncthing.net/users/contrib.html#contributions) to create a sync of the file between Windows/Steam Deck, though you have to keep in mind to set up an ignore list so as to exclusively sync that one file as Syncthing by default is set to synchronize full directories and subdirectories. If there is demand for an expansion of this section, I will be happy to include it! So please let it be known in the comments!

## Credits and thanks
Many, many thanks to the [Ballance Discord FAQ](https://yyc12345.github.io/ballance-discord-rules/en/faq/) which my guide borrowed quite a bit of, albeit in a condensed form. Their FAQ goes into a lot more detail than I did and if you want to take things further than I did, I heavily encourage you to dig around there. Thanks to [doyaGu](https://github.com/doyaGu) for their great open-source releases of BallancePlayer and BallanceModLoader!
