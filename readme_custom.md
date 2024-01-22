# MY PERSONAL NOTES ON HOW TO WORKS WITH ALL THAT STUFF

This fork of SonixQMK/qmk_firmware is dedicated to DesignedByGG keyboards, with a SN32F248B chip.
Credits for the hard work goes to Christophe and Dexter.

For my own sanity, I removed other vendor (too much files in the file tree) and Ironclad V1/V2 (lack of physical whoops-switch).

## Setup

### Compiling
1. Install QMK MSYS, from the last tag here : https://github.com/qmk/qmk_distro_msys/releases
2. Open QMK MSYS, and run `qmk setup`. Just answer Y if it asks something.
3. Continuing in QMK MSYS, test the setup with the command correponding to your DbGG keyboard :
   * For Ironclad V3 : `qmk compile -kb designedbygg/ironclad/icl03 -km via`
   * For Berserker : `qmk compile -kb designedbygg/berserker -km via`
  If it's successful, you should have a `.build` directory in the project, with a `designedbygg_ironclad_icl03_via.bin` file (eg. for Ironclad V3).
  
### Flashing
1. Get the lastest Sonix Flasher there : https://github.com/SonixQMK/sonix-flasher/releases
2. Unplug the keyboard, and push the bootloader switch to the right, replug the keyboard.
3. Launch Sonix Flasher.
4. Make sure SN32F24x is checked, SN32F248B (bootloader) is in the choicelist, and 0x00 is selected in QMK offset.
5. Click on Flash QMK, and fetch the .bin compiled at the end of the third step.
6. IT'S FLASHIN TIME ! (please don't touch anything)
7. When it says "Finished", you can put back the bootloader switch to the left.

### Checking
1. Open a Chromium browser on https://usevia.app (sad firefox privacy enjoyer noise)
2. Click on the huge central "Authorize device" button, and select your keyboard.
3. Go on "Design tab", and click on the "Load definitions" button.
4. Select the json keymap file relevant to your keyboard, ex : `keyboards\designedbygg\ironclad\icl03\keymaps\via\ironclad3_via.json` for the Ironclad V3
5. Have fun setting lights and macros !
