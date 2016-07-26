# Lytro Image Exporter
Lytro Image Exporter is a command-line tool to batch export Lytro images as
TIFF images with everything in focus and correct EXIF metadata.

When using the Lytro Desktop application to export TIFF files, the exported
images do not have EXIF metadata set correctly. It is also labor intensive to
get images which have everything in focus.

The resulting images can be useful as thumbnails or indexes of your Lytro
library without having to manually edit every photograph.

## Usage
```text
Usage: lytro-image-exporter [OPTIONS] LFRS...

Creates TIFF images from LFR files. The resulting TIFF files will have everything in the scene in focus and will
correctly preserve EXIF data.

Options:
-c / --calibration CALIBRATION Path to the calibration data. See `cameratool pull-cal-data --help`.
-h / --help                    Print this help message
-j / --jobs NJOBS              Process NJOBS LFRs in parallel. Default: 7 (number of cores - 1)
-o / --out-dir DIRECTORY       The directory to output the TIFF files to. Default: current directory
-q / --quiet                   Suppress warning messages
-v / --verbose                 Print additional messages
```

## Example
Convert all `.lfr` files in the current directory to `.tiff` and put the
resulting tiffs in a directory called `outdir`.
```sh
$ lytro-image-exporter *.lfr -o outdir -c cameras
```

## Dependencies
 * [ZSH](http://www.zsh.org/) (included in OSX and many Linux distributions)
 * [ExifTool](http://www.sno.phy.queensu.ca/~phil/exiftool/)
 * [Lytro Power Tools Beta](https://www.lytro.com/imaging/power-tools)
