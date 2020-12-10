## Suckless ST

***Original fork of [juliusHuelsmann/st](https://github.com/juliusHuelsmann/st) see the [README](https://github.com/juliusHuelsmann/st/blob/full_0.8.4/README.md) for more***

### Extra Patches

**[Font2](https://st.suckless.org/patches/font2)** This patch allows to add spare font besides default. Some glyphs can be not present in default font. For this glyphs st uses font-config and try to find them in font cache first. This patch append fonts defined in font2 variable to the beginning of font cache. So they will be used first for glyphs that absent in default font.

## Build process

```bash
# If required: Install Build dependencies (if you're on Arch)
sudo pacman -S make git picom
# Clone
git clone https://github.com/juliusHuelsmann/st.git
cd st
# Optional: Use my xresources 
xrdb -merge .Xresources
# Build
rm config.h
make clean
make
```

## Launch st:
After building, make sure that you launch your compositor if you want to enable
transparency.
```bash
picom -b # optional, for the alpha focus patch; can be replaced by different
         # compositor
./st
```

# install
After building, you can install this `st` build via
```
sudo make install
```

In case you want to install this `st` build and use the shipped `.Xresources` 
(color scheme and opacity), be sure to copy  them into your home directory,
```bash
cp -i .Xresources $HOME/.Xresources
```
and to merge them after booting
```bash
xrdb -merge $HOME/.Xresources
```

You also need to make sure that your composite manager is launched on startup.

