---
title: How to Rip Sprites From Jetpack Joyride
date: 2021-01-14 10:11:23 +0:500
categories: [Sprites]
tags: [tutorials]
---

# Introduction
Recently, I was interested in ripping sprites from Halfbrick Studios’ popular game Jetpack Joyride. I downloaded the APK file and extracted it, but instead of finding a viewable image such as a PNG, I only found texture files with the extension `.tex`. At first I thought it might be an obscure image file, but could still be opened, however, it turned out that it was a custom format only able to be opened in special programs. I searched around for a while to see if there was a tutorial on how to do this, but there was not, and so I have now made one!

# What to Download
You won’t need much to rip the sprites. Here’s what you do need:

- [GraphicConverter 11](https://www.lemkesoft.info/newsletter/graphicconverter_en_2019.html). (You won’t need the paid version, the free trial will do fine)

- The Jetpack Joyride APK, available online.

# Set Up
Install GraphicConverter 11 on your machine. Rename the Jetpack Joyride APK’s extension from `.apk` to `.zip`, and open it with your archive manager. I use [TheUnarchiver](https://theunarchiver.com/), but most extraction apps will do just fine.

# Let’s Rip Us Some Sprites!
Once you’ve done the set-up steps above, you’re ready to start ripping sprites! It can be a bit difficult at first, but if you follow the steps below you’ll be a pro in no time!

### Step 1:
Navigate into the folder where the textures you wish to rip sprites from are located. They should be within the `YourAPKName/payload/assets/textures/` folder. Right click on the texture you want to open, e.g. `sam0.tex`, and select `Open With`. Click on the option `Other`, and then select GraphicConverter 11. 

### Step 2:
You should see a message that says:
> The file “exampleTexture.tex” is broken, the format is unknown or it
> isn’t a graphic file. So, GraphicConverter can’t open it.

Below that (and a Hex Dump, but you don’t need to pay much attention to that unless you’re curious) you should see two options. The first one is `Try RAW Import`. Select that and you should see a new menu open up.

### Step 3:
You should now see a menu with a lot of options.
Now for the tricky part: For each texture file, you will need to specify a width, height, pallet, offset, number format, and more. Don’t worry though, most of the images are very similar. Below is a list of settings for various files:

- Pallets for almost everything but backgrounds, and `player0.tex`:
> Offset: 0
> Color: 16 Bit, RRRRGGGGBBBB
> Format: ARGB
> Interlaced: Yes
- Pallets for backgrounds:
> Offset: 3
> Color: 32 Bit, RRRRGGGGBBBB
> Format: ARGB
> Interlaced: Yes
- Pallets for `player0.tex` and maybe a few other things:
> Offset: 0
> Color: 32 Bit, RRRRGGGGBBBB
> Format: RGB
> Interlaced: Yes

By now you may have noticed that I never included the image dimensions. This is because they are different for almost every image. However, figuring them out isn’t all that hard. Almost all the texture file dimensions have a width which is a power of two (2, 4, 8, 16, 32, and so on, though mostly on the higher end between 512 and 4096), so simply guess something reasonable and then press the `Guess` button to automatically figure out the height. (Sometimes it won’t get in right, in that case just guess something reasonable. It’s not as big an issue as getting the width right.) In some cases You will notice that with whatever power of two you try for the width, it will still look corrupted (for example, some jetpack stands or the Lil Stomper). To fix this, simply set it as a power of two, and then adjust the number using the up or down arrows till the image looks normal. Once the preview of the image looks normal, press `Ok` and move on to the next step.

### Step 4:
Next, you will need to export the image. This is pretty straight-forward; all you need to do is go into `File → Save as`. (Please note: If you are using the free version of GraphicConverter 11, you will need to press the `Try It` button on the pop-up window before you can interact with the editing window.) Now, in the Save window, simply name the output image what you want and select the PNG file extension, and you’re done!

# Conclusion
Thanks for reading this tutorial all the way to the bottom! If you have any questions or run into any difficulties, feel free to get in touch with me for help. I hope you enjoy your sprites!

_Disclaimer: I did not make or own the rights to either Jetpack Joyride or GraphicConverter 11._
