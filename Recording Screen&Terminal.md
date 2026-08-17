## Recording Terminal with asciinema
To record a session in the terminal we can use `asciinema` . This app record the sessions in it's own format which can be edited after that as a text too.

```bash
asciinema rec tjournal.cast
```

## Covert asciinema to GIF
To convert the recording to gif there are many tools. The best one currently is [agg](https://github.com/asciinema/agg) 
```bash
agg --font-family 'Fira Code' --font-size 16 --speed 2.7 --theme monokai tjournal.cast tjournal.gif
```

## Recording Screen for README Demos
Workflow to get good quality demos with small file sizes.

### Capture with Kooha
[Kooha](https://github.com/SeaDve/Kooha) with these settings:
- Format: `webm`
- Frame rate: `10`

### Convert to mp4
This converts the recording to mp4 and reduces its size considerably.

```bash
ffmpeg -i input.webm -an -c:v libx264 -crf 28 -preset slow -pix_fmt yuv420p -movflags +faststart output.mp4
```
