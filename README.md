# ps3-midi

A tool that converts input from a Playstation 3 controller to MIDI control change messages. ps3-midi is built with [Pure Data](https://puredata.info/), a visual/dataflow programming language.

Currently, getting input data from the buttons, throttles and joysticks on the ps3 controller is supported.

## Requirements

- A working installation of Pd. Instructions can be found at [puredata.info](https://puredata.info/downloads).
- The Pd external [hid], which pulls the data from HIDs - in this case the ps3 controller. [hid] can be installed from inside Pd with Pd's _deken_ package manager if necessary.

## Usage

Steps to get started:

1. Pair and connect a ps3 controller via bluetooth with the machine that will be running ps3-midi.
2. Open the ps3-midi.pd from 'File' -> 'Open' in a Pd window or from a terminal: `pd ps3-midi.pd`
3. When the patch has opened, click the light red button in the top of the patch. Pd should now be pulling data from the ps3 controller, which can be verified in the Pd GUI.

Instructions for automating the last step are included within the patch itself.

## Settings

The patch will emit MIDI control messages on MIDI channel 1 by default. MIDI channel can be changed from within the patch.

MIDI preferences such as which device to send MIDI output to can be set within Pd's preferences.

Each button, joystick and throttle on the ps3 controller will emit MIDI control changes on different controller numbers. The defaults can be changed by editing the ps3-midi.pd patch. For each [throttle], [button], [stick] and [stickInv] object, the MIDI controller number can be changed by editing the object and changing the number after the object name.

The GUI elements in ps3-midi.pd mainly serve to deliver visual feedback for quick verification that everything is connected correctly. These can thus be safely deleted for optimization.
