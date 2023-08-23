To Produce a recording of the terminal there are two steps: Recording and then converting to gif

## Recording
To record a session in the terminal we can use `asciinema` . This app record the sessions in it's own format which can be edited after that as a text too.

```bash
asciinema rec tjournal.cast
```

## Covert to GIF
To convert the recording to gif there are many tools. The best one currently is [agg](https://github.com/asciinema/agg) 
```bash
agg --font-family 'Fira Code' --font-size 16 --speed 2.7 --theme monokai tjournal.cast tjournal.gif
```

## Convert .webm to mp4
Converting using ffmpeg has a great results and it's available 

```bash
ffmpeg -fflags +genpts -i input.webm -r 24 output.mp4
```
