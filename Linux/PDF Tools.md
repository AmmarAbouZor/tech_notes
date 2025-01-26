## PDF Mix Tool
Is a GUI tool to merge and split PDFs. It's simple the provide great results
```bash
sudo dnf instal pdfmixtool   # install on fedora
```

## PDFs Merge & Split:

The bundle `poppler_utils` provide the tools `pdfunite`, `pdfseparate` for merging and splitting PDFs.


```bash
# pdfunite:
pdfunite file_1.pdf file_2.pdf merged.pdf

# pdfseparate:
pdfseparate input.pdf output-page%d.pdf
pdfseparate -f 1 -l 5 input.pdf output-page%d.pdf
```

## Compress PDF

Using `ghostscript` we can compress the files from the command line. Example: 

```bash
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.3 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf
```

`-dPDFSETTINGS` Options are: `screen` , `ebook`, `prepress`, `printer`, `default`

Here is a link for more info [Link](https://www.digitalocean.com/community/tutorials/reduce-pdf-file-size-in-linux)

## Sign PDF

To sign PDF files we can use the program **Xournal++** which can be used to draw on the documents and the pictures too.
