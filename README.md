# ps3-midi

A tool that converts input from a Playstation 3 controller to MIDI control change messages. ps3-midi is built with [Pure Data](https://puredata.info/), a visual/dataflow programming language.

Currently, getting input data from the buttons, throttles and joysticks on the ps3 controller is supported.

## Requirements

- A working installation of Pd (see link above for installation instructions)
- The Pd external [hid], which pulls the data from the ps3 controller ([hid] can be installed from inside Pd with the _deken_ package manager).

## Usage

To use ps3-midi, first a ps3 controller has to be paired and connected via bluetooth to the machine that is running Pd. Then open the ps3-midi.pd either from 'File' -> 'Open' in a Pd window or from a terminal: `pd ps3-midi.pd`

When the patch has opened, click the light red button in the top of the patch. This should allow Pd to pull sensor data from the ps3 controller. Instructions for automating this step is included with the patch.

## Settings

The patch will emit MIDI control messages on MIDI channel 1 by default. MIDI channel can be changed from within the patch.

Each button, joystick and throttle on the ps3 controller will emit MIDI control changes on different controller numbers. The defaults can be changed by editing the ps3-midi.pd patch. For each [throttle], [button], [stick] and [stickInv] object, the MIDI controller number can be changed by editing the object and changing the number after the object name.

The GUI elements in ps3-midi.pd mainly serve to deliver visual feedback for quick verification that everything is connected correctly. These can thus be safely deleted for optimization in headless contexts etc.
