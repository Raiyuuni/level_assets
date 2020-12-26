# LDmod4 but it's expanded by someone who's not an actual coder
(LDmod4-Rai-online.swf; LDmod4-Rai-offline.swf)

---
## Newest Update: 26/12/2020 19:00 GMT -3
- Added moving and circle green platforms.
- Edited command for touch-n-go green platforms.

---

This project is the byproduct of a split second idea for the Snow MDC. The level, Arise, is not an entry anymore, but I still intend in seeing it through.

To load this file in your level, open its code in a text editor (Notepad, Notepad++) and paste one of the following strings at the very end, after your level name.

Online version: `%3Cimg%20src%3D%22https%3A%2F%2Fgithub.com%2FRaiyuuni%2Flevel_assets%2Fraw%2Fmaster%2FArise%2FLDmod4-Rai-online.swf%22%3E`

Offline version: `%3Cimg%20src%3D%22%2E%5C63ModDirectory%5CLDmod4%2DRai%2Doffline%2Eswf%22%3E`

It is important that you do name your level. It (likely) won't load if it doesn't have a name.

---

## Why are there two versions?

This mod uses two different methods to recolor in-game objects. The first one, **setTransform**, works without limitations, but has limited capabilities. It can only manipulate existing colors in the image by channel percentages and absolute offsets. The second one, **ColorMatrixFilter**, is the same method used for Hue-Saturation-Lightness filters in advanced image editing software (GIMP, FireAlpaca) and allows for limitless color manipulation. However, this command doesn't work online, as it's called from an external class package which I cannot add to the repository or the mod itself.

You can read more about these commands [here](http://homepage.divms.uiowa.edu/~slonnegr/flash/ActionScript2Reference.pdf).

---

## How to use the offline version?

The image source in the offline title end string is a **relative path** starting from your local copy of Super Mario 63. Navigate to your game folder, create a new folder there named `63ModDirectory` and put the file `LDmod4-Rai-offline.swf` there. You can also reassign your file reference using a [URL encoder](https://www.url-encode-decode.com/).

---

## Compatibility

This mod is **NOT COMPATIBLE** with the following files:

- [**graphics.swf**](https://github.com/Runouw-Modders/SM63-Mods/blob/master/dev/graphics.swf) by Jynji. His mod can still make the original object transparent and place a custom image over it, but the image doesn't follow the object.

The following mods have not been cross-tested yet:

- The rest of Jynji's gallery.
- LDmod4 by Forgotten.
- LDmodOrig by Hydreigon.

---

## Functions

This mod can perform [all of LDmod4's functions](https://github.com/XnKradst/63LDMods/blob/master/LDmod.md), as well as:

### Colored Platforms

No longer a Last Legacy exclusive feature! Useful for Purpura Hall shenanigans.

This level has a significant amount of tags. You should edit a vanilla platform to your liking first, then replace it with a mod object. `**This program** converts your level code right away! **TO-DO**`

**Tags:**
- `<colorplat>` Moving Green Platform
- `<colorplatgo>` Touch-n-Go Moving Platform
- `<colorplatcircle>` Circle Green Platform

**Variables:**
1. **Moving Platform**
- `<scale:x>` Platform size. **{1, 2, 3}** **Default:** 2
- `<disapearcount:x>` Disappearing count. **Touch-n-Go platforms only.** **Default:** 32 
- `<DirectionX:x>` **"Right"** or **"Left"**. **Default:** "Right"
- `<DirectionY:x>` **"Up"** or **"Down"**. **Default:** "Up"
- `<distanceX:x>` Horizontal distance. **Default:** 25
- `<distanceY:x>` Vertical distance. **Default:** 0
- `<accelX:x>` Horizontal acceleration, absolute value. **Default:** 1
- `<accelY:x>` Vertical acceleration, absolute value. **Default:** 0
- `<speedX:x>` Horizontal speed, absolute value. **Default:** 2
- `<speedY:x>` Vertical speed, absolute value. **Default:** 0
- `<Xoffstart:x>` Horizontal offset. **Default:** 0
- `<Yoffstart:x>` Vertical offset. **Default:** 0


2. **Circle Platform**
- `<scale:x>` Platform size. **{1, 2, 3}** **Default:** 2
- `<speed:x>` Speed. Positive values yield clockwise spin. **Default:** 2
- `<radius:x>` Platform radius. **Default:** 50
- `<offset:x>` Starting angle offset, in degrees. **Default:** 0
- `<dotdistance:x>` Distance between dots, in degrees. A value of 360 of above omits all dots. **Default:** 20

Platform arms are unavailable.
Since the circle platform sign yields multiple objects, the circle platforms were moved to the very top of item layering to prevent ID/depth collision.


3. **Color (Online - setTransform)**
- `<redperc:x>` Red channel, percentage. **[0, 100]** **Default:** 100
- `<redoffset:x>` Red channel, absolute value offset. **[0, 255]** **Default:** 0
- `<greenperc:x>` Green channel, percentage. **[0, 100]** **Default:** 100
- `<greenoffset:x>` Green channel, absolute value offset. **[0, 255]** **Default:** 0
- `<blueperc:x>` Blue channel, percentage. **[0, 100]** **Default:** 100
- `<blueoffset:x>` Blue channel, absolute value offset. **[0, 255]** **Default:** 0
- `<alphaperc:x>` Alpha channel, percentage. **[0, 100]** **Default:** 100
- `<alphaoffset:x>` Alpha channel, absolute value offset. **[0, 100]** **Default:** 0

**Example:** `<colorplat><redperc:90><redoffset:255><greenperc:100><greenoffset:255><blueperc:90><blueoffset:130>`

[**Parameters for all preset colors.**](https://docs.google.com/spreadsheets/d/1n8EjU3Qe3UCEi0wm-RzcDASyxRoX2fLD8vLJjcDPKpE/edit?usp=sharing)

![](https://i.imgur.com/sbU0yjf.png "")

4. **Color (Offline - ColorMatrixFilter)**
`**TO-DO**`


### Area Tags

#### Fog

**Tags:** `<fog1area>` `<fog2area>` `<fog3area>`
Higher numbers give a thicker fog effect.

![](https://i.imgur.com/EeMEBR2.png "")

#### Wind (now with customizable particles!)

**Tag:** `<airarea>`

**Variables:**
- `<speed:x>` Maximum speed. Use a negative number for leftward wind. **Default:** 3
- `<timer:x>` The time it takes to switch directions. Use -1 if you don't want the wind direction to ever change. **Default:** 100
- `<particle:x>` Wind particles. Use 1 for leaves and 2 for snow. **Default:** 1

**Example:** `<airarea><speed:1><timer:120><particle:2>`

- Warning: High numbers can cause Mario/Luigi to glitch through walls or out of bounds!
- Using this function will replace one layer of some backgrounds with the particle effect. LDmod4 limitation.

![](https://i.imgur.com/p5JMX9R.png "")


---

## Credits
- **Forgotten**, for creating the original LDmod. None of this coding blasphemy would be possible without his work.
- **Hydreigon** and **Jynji**, for providing lots of feedback over at the mods channel.

---

## External links

- [**Jynji**'s mod library.](https://github.com/Runouw-Modders/SM63-Mods)
- [**Forgotten**'s LDmod4.](https://github.com/XnKradst/63LDMods)

---

## Changelog

- **26/12/2020 19:00 GMT -3**
Added moving and circle green platforms.
Edited command for touch-n-go green platforms.
