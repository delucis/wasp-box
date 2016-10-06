# wasp-box [![Build Status](https://travis-ci.org/delucis/wasp-box.svg?branch=master)](https://travis-ci.org/delucis/wasp-box)

:violin: Sample playback for Clara Iannotta’s [_dead wasps in the jam-jar (ii)_](http://claraiannotta.com/works/orchestra/dead-wasps-in-the-jam-jar-ii-2016/).

## Instructions

1. Download the [__latest version__](https://github.com/delucis/wasp-box/releases/latest) (click on `wasp-box.zip`).

2. Unzip it to your packages directory:    
`~/Documents/Max/Packages` for Max 6 or `~/Documents/Max 7/Packages` for Max 7.

3. In Max, select **Wasp Box** from the **Extras** menu.

## wasp-data.json

The JSON file (located in the `patchers/` directory) stores all of the cue data and several global parameters.

### Global parameters

The data file stores information about the default output volume.

```json
"mastervol" : "0."
```

The default output volume, `mastervol`, is set in dB, so a value of, for example, `-12` will set an output gain of -12dB.

### Cues

A cue can be declared as follows:

```json
"43" : {
  "player-1" : "play wb.cue043-player-1.aif",
  "player-2" : "stop"
}
```

The cue name, e.g. `43`, refers to the bar number, and cues will be triggered in ascending order.

Within each cue, the names of instruments, e.g. `player-1`, indicate which instrument to target. A cue can either `stop` an instrument’s playback, or instruct it to `play` in which case a file name must be provided.

All audio must be stored in the `media/` directory. Currently only `player-1` and `player-2` are set up in the main patch.
