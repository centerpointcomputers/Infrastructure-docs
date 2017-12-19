## A log of changes in reverse chronological order.

### 12-18-2017

Added a log entry as a new user to test the collaborative features of GitHub in order to sync to a WIKI.

### 12-11-2017

- Soldered a female 5-Pin DMX connector to the CAT5 cable that runs from the Leviton Digital DS8 Dimmer to the FOH and subsequently to the DMXIS D-Split and DMXIS USB Controller.  [Lighting Layout Reference](https://newvalleychurch.slack.com/files/U75QP3JLU/F8BRWFCU8/lighting_system_layout_overview.pdf)  

- Each dimmer (1 - 7) on the DS8 was previously set to Maximum _and_ minimum values of FULL 100%.  It has been re-programmed to have a range of a maximum of 100% and a minimum of 0%.  The upper and lower limits of the lighting can be set in more than one place.  The dimming control can control this, or the range of dimming can be set on the DMXIS controls inside of Ableton Live.

- Both Electrics (the two white lights) above the stage had reset themselves to a default channel on the DMX chain for some reason.  Perhaps the circuit that these lights were on was shut off for a period of time long enough to force the lights to re-set. Both have been re-assigned the correct values of 80 for stage right and 90 for stage left. 

- Connected House lights to DMXIS D-Split module.  Reconfigured DMXIS channel mappings.  House lights are designated to be DMX channels 0-8 and 8 is currently unused, but is reserved for a logo sign in the lobby.

- Created a new template for Ableton Live on the Media workstation.  Ableton Live opens with this template selected as the default.  In the template, there is provision for 3 recording channels (all pastor mics) and a group to handle the DMXIS lighting.

### 12-10-2017

- Reconfigured the Ableton Live default template at the FOH media workstation.  Previous configuration was a single audio track in Ableton with the QU32 USB source as channel 25.

#### Here is the current configuration:

- There are 3 grouped audio tracks to handle all wireless microphone inputs as they are currently configured on the QU32, one for each wireless device.  Each track is set to Monitor IN instead of AUTO, which removes the requirement to have the track ARMED with the red dot.  Now, while recording, all audio coming into the board on 25, 26, and 27 (as currently configured) will be recorded.  Each track produces an individual audio file.  Exporting can mix down individual tracks into a single master file for publishing.
- There is a Lighting group.  This group contains a single track for the DMXIS lighting control.  This is a temporary configuration as a more advanced configuration will be created over time.  The DMXIS plugin is dropped into the DMXIS track.  All 9 Front of House (FOH) lights are mapped via MIDI to a single fader (channel strip #1) on the QU32 Custom Layer.  The fader maps to the RGBA "Amber" lamp and the Masters for each RGBA lamp, and the remaining 4 White unicolor cans.

When Ableton Live is started, provided none of the Audio/MIDI settings on the MAC have been altered, and none of the Link settings for MIDI in Ableton Live have been altered, the template will connect to the QU32 and be ready for recording and remote light control.

Currently the only light configuration is a simple fader that brings all of the lights on the stage up with as close to a natural lighting color as possible.

### 12-7-2017

- Wiring up the house lights to the DMXIS.  We still need a female connector for the connection at the DS8 light dimmer control.  DMXIS was moved to the right side of the QU32.  D-SPLIT installed with power.  Connector on sound booth side soldered and connected to D-SPLIT.  Connector on DS8 side soldered but it's the wrong connector.

- Adjusted the angle of some of the FOH lights.

- Created a wiring diagram overview of the lighting system based upon current setup.
