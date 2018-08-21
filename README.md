# Numark PartyMix MIDI controller mappings for Mixxx

![Image of NuMark PartyMix MIDI Controller](http://rylito.com/media_rylito/content/images/original/numark_party_mix.jpg)

Note: this README is adapted from the [original announcement of this mapping on the Mixxx Community Forums](https://www.mixxx.org/forums/viewtopic.php?f=7&t=9232&start=10#p38408)

# Installation

Put the .xml and the .js file in the user controller mapping folder or the system controller mapping folder of your Mixxx installation. More detailed information about where to place these files is available here in the Mixxx documentation: [Controller Mapping File Locations](https://www.mixxx.org/wiki/doku.php/controller_mapping_file_locations)


# Features

- Figured out Numark's SysEx message. Now when the PartyMix is plugged in and Mixxx loads, the controls in Mixxx should 'snap' to match the state of the controls on the controller surfice
- The headphone/PFL buttons work correctly. These were tricky to map because they are 'stateful' switches on the controller, but the script handles this. UI PFL buttons and controller PFL buttons should always stay in sync now, no matter if the toggle occurs in the UI or controller.
- The Pads work
    - Cue mode is mapped to the hotcue buttons in the UI for each deck
    - Loop mode: pads 1,2,3, and 4 are mapped to the 1,2,4, and 8 beat beatloop controls for each deck
    - Sampler mode:
        - Deck 1 pads are mapped to toggle playback on samplers 1-4 if loaded, or to load the selected track if no track is loaded
        - If using the Deere skin which supports a sample bank, the Deck 2 pads will select the relevant sample bank and the Deck 1 pads will change accordingly
        - The behavior of the LEDs can be changed in the script by setting the USE_FLASH boolean value at the top. The default behavior is for the pad to be dark when no track is loaded, dimly lit when a track is loaded, and brightly lit while a sample is playing. This can be changed to be dimly lit when no track is loaded, brightly lit when a track is loaded, and flashing while a sample is playing
    - Effect mode:
        - Deck 1 pads 1 and 2 toggle effects units 1 and 2 and Deck 2 pads 1 and 2 toggle effects units 3 and 4
        - Pads 3 and 4 are currently mapped to the brake and spinback effects for each respective deck
- The Scratch button can be pressed quickly to 'latch' (toggle). If it is held down, it will stay in scratch mode until released
- The browse rotary control works. A quick press toggles between scrolling the sidepane, or the main browsing pane. Rotating scrolls up/down the list. If focused on the side pane and hovering over an expandable item, a long press of the browse control will toggle expand/collapse of the item.
- The Load 1 and Load 2 buttons work as expected.

## Other Notes:

- If you're not using the Deere skin, the Deck 2 pads will remain dimly lit in Sampler mode since the other skins do not support sample banks. If you would rather disable this feature, so that the Deck 2 pad LEDs remain off in Sampler mode when using other skins, this can be done by setting the **USE_SAMPLE_BANK** boolean setting at the top of the script
- The rate (pitch) sliders for each deck are reversed on this controller. In order for them to move in the same direction on the UI as they do on the physical controller, go into the **Options -> Interface -> Speed Slider Direction** and select **Down Increases Speed (Technics SL-1210)**.
