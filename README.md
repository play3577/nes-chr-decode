# nes-chr-decode
Converts NES CHR (graphics) data to a PNG file.

Note: requires the [**PyPNG** module](http://github.com/drj11/pypng).

## Command line arguments
Syntax: [*options*] *input_file* *output_file*

### *options*
* `--color0`=*color*
  * What color in the PNG image should correspond to color 0 in the CHR data.
  * *color*: see below.
  * The default is `000000`.
* `--color1`=*color*
  * What color in the PNG image should correspond to color 1 in the CHR data.
  * *color*: see below.
  * The default is `555555` (dark gray).
* `--color2`=*color*
  * What color in the PNG image should correspond to color 2 in the CHR data.
  * *color*: see below.
  * The default is `aaaaaa` (light gray).
* `--color3`=*color*
  * What color in the PNG image should correspond to color 3 in the CHR data.
  * *color*: see below.
  * The default is `ffffff` (white).

*color* is an HTML-style color code (six hexadecimal digits, `RRGGBB`, case insensitive).

### *input_file*
* The NES CHR data file to read.
* The file size must be a multiple of 256 bytes and greater than zero.
* Note: iNES ROM files (extension `.nes`) are *not* supported.
* Hint: the CHR-ROM data can be extracted from an iNES ROM file with my [`ines-split`](http://github.com/qalle2/ines-split).

### *output_file*
* The PNG image file to write.
* The file must not already exist (it will not be overwritten).

## Example

Convert `smb.chr` to `smb-chr.png`:
```
python nes_chr_decode.py smb.chr smb-chr.png
```
