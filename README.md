# Image to Base64 command line tool

This is simple `bash` script, that converts images to `base64` css background, inline `<img />` or svg `<image />` tags, or to `:before` pseudo element.

Also it will compress your images before converting them, if you have [image_optim](https://github.com/toy/image_optim) installed.

## Install

If you don't need compression, then install will be trivial: just clone the repo.

``` bash
git clone repo
```

If you want compression too, you'll need to install `image_optim` first: go to their [repo](https://github.com/toy/image_optim) and follow the instructions there. It's pretty straightforward too.

## Usage

``` bash
./i2b64 --help

Usage: i2b64 [options] <images ...>
     -h                      Show help options.
     -v                      Print version info.
     -n, --no-imageoptim     Disable image optimising **(WARNING: optimising done in place)**.
     -i, --img               Print '<img  />'.
     -b, --bg                Print 'background: ;'. (Default one, if nothing else choosen)
     -p, --pseudo            Print :pseudo-element
     -s, --svg-image         Print an SVG <image />
     -c, --include-class     Set class for <img /> and <image /> to filename
```

Please note warning: `image_optim`, as far as I know, do not have option to optimise images on the fly and keep the old ones, so **do backups first**! If you want to disable it, use `-n` option.

`-c` will add `class="*FILENAME*"` to the `<img />` and `<image />` tags.

You can choose the output types you need with the `-i, -b, -p, -s` flags, if none choosen, it'll be the `backgound` one.

## Examples

To generate `pseudo element` based on `image.png` with compression use this:

`./i2b64 -p image.png`

An `img` tags from `image0.png`, `image1.png` and `image2.png` *without compression* and with classes use:

`./i2b64 -i -n image0.png image1.png image2.png`

## Contacts

Please feel free to contact me directly, or trough tickets.