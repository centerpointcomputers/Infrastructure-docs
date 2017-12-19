## Implementing AKAI VIP 3.0 Inside of Ableton

There are actually a gazillion ways to do this, but there is one specific method that allows you to separate the MIDI track from the Audio track.

Normally, when you drop an instrument plugin onto a track in Ableton Live both the MIDI messages and the audio output are controlled by that track.  They are not independent.  In order to split them up, a bit of creative routing needs to take place.  

Here is how we do that, specifically for the Advance 61 Keyboard:

- Create 2 new MIDI tracks in Ableton Live.
- The purpose of one of the tracks is to receive inbound MIDI messages from a specific device, such as the Advance 61 Keyboard.  
- Set the MIDI **_From_** in the I/O section of this track's channel strip to ADVANCE Input.  (Note: The term "Advance Input" is determined by the MIDI settings in Ableton Live Preferences under the Link MIDI tab. Your device may be described differently depending on how it was installed and configured.  Either way, it's the USB input device for your keyboard or controller.)
- Select the channel that the instrument is sending on.  Some instruments, like the Advance 61 Keyboard, using VIP, can operate on multiple channels at the same time.  It's your call if you want to make it more complicated.  
- Set Monitor to 'IN'.  By doing this, you're telling the track to _always_ recognize incoming MIDI signals.  If you set it to 'AUTO' the signal will _only_ come in when that track is armed.  Off is obviously off.
- Set the MIDI To section to No Output.  This may seem strange, but it's not.  We will be telling another track to _go get_ the MIDI information in that track.
- Give this track a clear identifying name that you'll recognize.  In mine, I call it the AKAI 61 Keyboard because that's the _only_ device that this track is receiving information from.
- Make sure this track isn't muted.  Now, move on to the next track.

#### The next track is where the magic happens.

Here's the concept.  This track will contain an instrument rack containing one or multiple chains of External Instruments, which is a tool in Ableton Live to route MIDI data to Virtual Instruments that support this function.  Not every plug-in supports it, but VIP 3.0 _DOES_ support it, and thus, any plugin that doesn't support it that is being called up by VIP will in essence also adopt VIP's functionality.  This is a great way to turn a non-external instrument into one.  By having more than one chain, the MIDI data that is being received by a given device can be routed on the fly to another VST, group of VST's or external instrument using the chain selector.

- Label the next track 'Key Chain' or 'Instrument Chain.'  I chose 'Key Chain' because it will be only a collection of MIDI controllers that are keyboards.  Your descriptor can be whatever you want.
- In the channel strip of this track, select the name of the first track you creates as the MIDI Input.  This is where you're "tuning in" to the MIDI data arriving on the first track.
- Set the Monitor selection to 'IN' just like the other track.  We don't want MIDI messages to be dependent upon arming the track.  We always want to allow them through.  We'll use an external instrument inside of this track to route where the MIDI messages go next.
- Drag an Instrument Rack into this track from the file browser under "Instruments."
- Next, make sure that the "Show/Hide chain list" button is on in the Instrument Rack details at the bottom of Ableton Live.
- Drag an External Instrument into the Instrument Rack from the file browser under Instruments.
- Click the Chain button in the Instrument Rack settings above the "Drop and Instrument or Sample Here" section so you can see which zones the External Instrument is assigned to.  Adjust the zone bar to only be located in slot 1 of the chain selector.  We ignore "0" because it's just easier to start at 1 and because 0 can be a location that disables all keyboard routing.

You'll now need to create a 3rd track that contains the VST that you want to control.  In this case it will be VIP 3.0.

- From the Plug-Ins in the File Browser, Drag VIP to a new track in Ableton Live.
- Give this track a name.
- Set MIDI From to "No Input."  We aren't routing MIDI through this channel strip.  We're routing MIDI to the device inside of the channel strip, which Ableton Live sees as an external instrument.  It's almost like it's another keyboard sitting across the room ready to receive MIDI data.
- Route the Audio from this track to Sends Only, or somewhere else that's not going to your main output or any other output.  We're going to treat this like we did the MIDI track(s) and "tune in" to the audio from the plugin using yet another track.
- The track we just created serves one major purpose.  It holds the VST that we want to control.  It can also contain MIDI clips that will work in tandem with the signals coming from the keyboard controller, firing off another part, or automating parameters inside of VIP.  
- Create an audio track in Ableton and give it a name.
- Set the Audio From to the name of the track that contains the VST.  We're "tuning in" to the audio being produced there and forcing it to come into this new track.
- Again, set Monitor to IN so it's always on.
- Send the audio to a group, or to any of your outputs on your system.
- Go back to the 2nd track you created, which has the Instrument Rack and the External Instrument(s) in the chain.  Select the External Instrument you want to route to the VST.  In the External Instrument, select the track name containing the External Instrument and from the MIDI To selection list, select that instrument.

(Note:  If your track does not show up here, then the VST you chose to control does not support external instrument mode.  VIP does not have this problem.)

- The next selection list down is the list of channels inside of the external instrument.  If you have configured VIP to have a Multi with slots on different channels, this is one of the ways you can route the MIDI data to the right slots.  This makes creating Multi patches extremely versatile.  Imagine in VIP, you have 4 slots all with the same piano sound but each one set to a different midi channel.  Then, the remaining 4 slots contain other instruments.  You could setup Ableton to send MIDI to Channel 1 on song 1 which would play the piano in slot one and the violin in slot 5.  Then, you could have Ableton send MIDI to channel 2 which would be a combination of slot 2 and slot 6.  Basically, you could make one multi in VIP be a combination of patches that are on different channels that would be setup for more than one song.  One song may have piano and violin.  One song may have Piano and Organ.  By simply switching the chain selector in Ableton from one chain slot to the other, it would address only the External Instruments that are dropped into the Instrument Rack that are enabled for that chain's zone.

Now you should have 4 tracks.

Track 1 is dedicated to listening to the input on one of your keyboards.
Track 2 is an instrument rack with external instruments that route that MIDI data to the appropriate external instrument.
Track 3 contains the instrument you want to trigger.
Track 4 receives the audio from track 3 and sends it to the master output, or a group which then in turn sends it to the master output.
