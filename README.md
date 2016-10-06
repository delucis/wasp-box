# wasp-box

:violin: Sample playback for Clara Iannotta’s [_dead wasps in the jam-jar (ii)_](http://claraiannotta.com/works/orchestra/dead-wasps-in-the-jam-jar-ii-2016/).

## Instructions

1. Download the [__latest version__](https://github.com/delucis/wasp-box/archive/master.zip).

2. Unzip it to your packages directory:    
`~/Documents/Max/Packages` for Max 6 or `~/Documents/Max 7/Packages` for Max 7.

3. In Max, select **Wasp Box** from the **Extras** menu.

## wasp-data.json

The JSON file (located in the `patchers/` directory) stores all of the cue data and several global parameters.

### Global parameters

The data file stores information about the default output volume, and instrument panning.

```json
"mastervol" : "0.",
"panning" : {
  "perc1" : "-50",
  "perc2" : "50"
}
```

The default output volume, i.e. `mastervol`, is set in dB, so a value of, for example, `-12` will set an output gain of -12dB.

Panning is set on a scale of `-50.` to `50.`, where `-50.` is panned completely to the left, `50.` is panned completely to the right, and `0.` is centred.

### Cues

A cue can be declared as follows:

```json
"43" : {
  "perc1" : "play wb.cue043-perc1.aif",
  "perc2" : "stop"
}
```

The cue name, e.g. `43`, refers to the bar number, and cues will be triggered in ascending order.

Within each cue, the names of instruments, e.g. `perc1`, indicate which instrument to target. A cue can either `stop` an instrument’s playback, or instruct it to `play` in which case a file name must be provided. All audio must be stored in the `media/` directory.
