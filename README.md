# swsh-overworld-shiny-patch
## Updates moved to https://github.com/Lincoln-LM/swsh-mods-exl
Patches/Cheats enabling shiny pokemon to be visible in the overworld in pokemon sword and shield.

https://github.com/Lincoln-LM/swsh-overworld-shiny-patch/assets/73306575/b6e18bf4-1099-4fe1-af4c-284bdf19a505

# Please do not re-share without crediting me !


# [Download](https://github.com/Lincoln-LM/swsh-overworld-shiny-patch/releases/)

# Installation
## Patches
### Atmosphère
- Extract the zip to the root of your sd card and it should create ``sdmc://atmosphere/exefs_patches/swsh-overworld-shiny-patch/A16802625E7826BF83B6F9708E475B912A9AB7DF000000000000000000000000.ips`` (shield) and ``sdmc://atmosphere/exefs_patches/swsh-overworld-shiny-patch/A3B75BCD3311385AEED67FBEEB79CBB7BF02F471000000000000000000000000.ips`` (sword)
- You can remove the .ips file for the game you do not want to patch if you would only like to install the patch for one version
- The ``boosted.zip`` file contains patches that include a boosted shiny rate for overworld pokemon (~63%) for testing that the shiny models work
- The ``regular.zip`` patches contain only whats needed to display shiny models when a overworld spawn is shiny
### Emulator
- Place the patches in the appropriate folder for exefs patches in your emulator of choice
- The same notes about ``boosted.zip`` and ``regular.zip`` from above apply here
## Cheats
### Atmosphère
- Extract the zip to the root of your sd card and it should create ``sdmc://atmosphere/contents/{TitleID}/cheats/{BuildID}.txt`` for TitleID:01008DB008C2C000 BuildID:A16802625E7826BF (shield) and TitleID:0100ABF008968000 BuildID:A3B75BCD3311385A (sword)
- Install a cheat manager like [Edizon-SE](https://github.com/tomvita/EdiZon-SE)
- The cheats file contains a cheat for boosted shiny rate for overworld pokemon (~63%) for testing & the cheat that allows shiny models to work
### Emulator
- Place the cheat files in the appropriate folder for your emulator of choice

### Alternatively you may install with [IP-Switch](https://github.com/3096/ipswitch) and the *.pchtxt files in the repo


# Notes
- This patch is possible because shininess of overworld pokemon is pre-determined and generated prior to their model (or "PokemonObject") being made visible
- PokemonObject's can already appear shiny (they are what's used for partner pokemon in IoA and CT)
- Overworld spawns specifically set a flag that tells the game to never show them shiny even when they are pre-determined to be
- The patch is surprisingly non-intrusive as it just needs to overwrite a single instruction to force this flag to show proper shininess
- It is unclear why the developers decided not to display shinines in the overworld, but it is possible PokemonObject's could not account for shininess prior to IoA/CT and they wanted to maintain parity with older versions
- The shiny odds boosting patch works by overwriting the "shiny rolls" parameter of pokemon generation to a constant value of 4095.
  - This results in the game always performing the 1/4096 check for shininess 4095 times, resulting in a roughly 63% chance of shininess
