# Better ASCII Waifus for Neofetch

While displaying images in your terminal is cool and all, I wanted to use custom ASCII art, but with ANSI color support to specifically support the output from ascii-image-converter. 
This is a fork of Neofetch that adds support for custom ASCII art files with ANSI color codes. 
This isn't the be all and end all, but it's something I use and wanted to share because I couldn't find anything like it that was readily available.

## How I personally use this:

### 1. Setup Waifu Ascii Art:

I use this library to convert my waifu over to ASCII art, you'll need to grab this for my example to work: \[[ascii-image-converter](https://github.com/TheZoraiz/ascii-image-converter/)\]
I'm a gamedev, so I'm on windows. If you want to easily grab this use scoop and run ``scoop install ascii-image-converter`` otherwise you can go through the hell of installing it manually.
If you don't already have scoop, you can grab it here: \[[scoop](https://scoop.sh/)\]

### 2. Edit Neofetch Config:

Next, I add this awful hack into my config file, example is below.
To find where you need to edit the config file ctrl-f for ``image_source`` and you'll find out where to glue in my horrible hack.
It does run the ascii-image-converter every time you run neofetch, so it's not horribly efficient, but you can have fun with it like selecting a random anime babe every time you run neofetch, etc.

```sh
# Image Source
zzTERMINAL_HEIGHT=$(($(tput lines) / 2))
if [ $zzTERMINAL_HEIGHT -lt 20 ]; then
    zzTERMINAL_HEIGHT=20
fi

Waifu=$(ascii-image-converter "C:\Users\nzork\neofetch\rei.jpg" -C -x -H $zzTERMINAL_HEIGHT --complex -m " .-=+#@" -b --dither)
image_source="$Waifu"
```

### 3. Run Neofetch:
    I run ``neofetch`` and it displays my waifu in the terminal with ANSI color codes and somewhat correct formatting.

### Example Image:

![Example](https://i.imgur.com/kp6dYJr.png)

## Conclusion: 

    I pretty much have no plans on future iterations for this, but I figured someone else would find it useful as it took way too much googling to get to this point. This is pretty minimalistic but it works for me and I hope it works for you too. 
    Feel free to submit any PRs, the main edit that was made to neofetch was made in ``print_ascii()`` function. 
    
    Cheers!


### More: 
\[[Dependencies](https://github.com/dylanaraps/neofetch/wiki/Dependencies)\] \[[Installation](https://github.com/dylanaraps/neofetch/wiki/Installation)\] \[[Wiki](https://github.com/dylanaraps/neofetch/wiki)\]
