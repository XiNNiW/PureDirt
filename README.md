# PureDirt
pure dirt is a sound engine for tidalcycles written in pure data.

## Usage

Open the pure-dirt-main.pd patch and start pd's audio. PureDirt should now be listening on tidalcycle's port.

Currently PureDirt only supports sounds that it synthesizes itself. This means that it will not read samples from folders the way Dirt and PureDirt do.
It supports the following sounds:
`bd sn hh bass`
And the following standard dirt parameters:
` #note #gain #room #delay #delaytime #delayfeedback #shape #attack #sustain #decay #release `
Currently, all synth voices are monophonic. Polyphonic synthvoices will be implemented soon.

## Goal
The goal of this project is to make a dirt implementation that can be used like a big modular synthesizer that knows how to speak to tidal. 
Ideally, this would allow easy hacking and customizing of synthesizers so that the synths in PureDirt could be reconfigured per song or per session (much in the same way that a modular synthesizer can be reconfigured per session.) 
It would also allow the synthesizer to feel like it exists in between the notes, with smooth expressive changes in parameters that cross events and envelope decays that go beyond the end of events. 

## Installation
requirements:
1. Pure Data
1. Tidalcycles
1. Faust or [The Faust Online Editor](https://faust.grame.fr/tools/editor/) (on non-linux machines)

PureData lacks good bandlimited oscillators out of the box. Faust is being used to generate pure data externals that cover this missing functionality. The linux externals are checked in with this repository and no building should be required. However, for use on Windows and Mac, you may need to build the externals yourself. To do so, install faust. Then, run the command `faust2puredata <FILENAME.dsp>` on each of the files in the "faust" directory. Place the resulting artifacts in the lib folder. This step will soon be automated. 

Alternatively, for MacOS users, the online editor that the faust project provides may be used to build the externals.

If you wish to skip this step, most of Pure Dirt will work anyway. What will be missing is the oscillators that power the `bass` voice.
