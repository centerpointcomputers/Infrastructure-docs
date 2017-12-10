## A chronology of changes, configuration, etc. regarding technology.

### 12-7-2017

- Wiring up the house lights to the DMXIS.  We still need a female connector for the connection at the DS8 light dimmer control.  DMXIS was moved to the right side of the QU32.  D-SPLIT installed with power.  Connector on sound booth side soldered and connected to D-SPLIT.  Connector on DS8 side soldered but it's the wrong connector.

- Adjusted the angle of some of the FOH lights.

- Created a wiring diagram overview of the lighting system based upon current setup.

### 12-10-2017

- Reconfigured the Ableton Live default template at the FOH media workstation.  Previous configuration was a single audio track in Ableton with the QU32 USB source as channel 25.

#### Here is the current configuration:

- There are 3 grouped audio tracks to handle all wireless microphone inputs as they are currently configured on the QU32, one for each wireless device.  Each track is set to Monitor IN instead of AUTO, which removes the requirement to have the track ARMED with the red dot.  Now, while recording, all audio coming into the board on 25, 26, and 27 (as currently configured) will be recorded.  Each track produces an individual audio file.  Exporting can mix down individual tracks into a single master file for publishing.
- There is a Lighting group.  This group contains a single track for the DMXIS lighting control.  This is a temporary configuration as a more advanced configuration will be created over time.  The DMXIS plugin is dropped into the DMXIS track.  All 9 Front of House (FOH) lights are mapped via MIDI to a single fader (channel strip #1) on the QU32 Custom Layer.  The fader maps to the RGBA "Amber" lamp and the Masters for each RGBA lamp, and the remaining 4 White unicolor cans.

When Ableton Live is started, provided none of the Audio/MIDI settings on the MAC have been altered, and none of the Link settings for MIDI in Ableton Live have been altered, the template will connect to the QU32 and be ready for recording and remote light control.

Currently the only light configuration is a simple fader that brings all of the lights on the stage up with as close to a natural lighting color as possible.