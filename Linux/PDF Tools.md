## Merge PDFs

In Linux you can use the CLI tool `convert`

```bash
convert file_1.pdf file_2.pdf merged.pdf
```

There is another tool called `pdfunite`

```bash
pdfunite file_1.pdf file_2.pdf merged.pdf
```
## Compress PDF

Using `ghostscript` we can compress the files from the command line. Example: 

```bash
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.3 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf
```

`-dPDFSETTINGS` Options are: `screen` , `ebook`, `prepress`, `printer`, `default`

Here is a link for more info [Link](https://www.digitalocean.com/community/tutorials/reduce-pdf-file-size-in-linux)

## Splite PDF

The CLI Tool `pdfseparate` should be available or easy to install.

Example to separate each page into a Separate File:

```bash
pdfseparate input.pdf output-page%d.pdf
```

Example to extract the first five pages of a file

```bash
pdfseparate -f 1 -l 5 input.pdf output-page%d.pdf
```
