This project consists of an add-on for the IPE editor that exports clean and customizable TikZ code from a selection of graphics, directly to the clipboard.

It is a fork of Joseph Rabinoff's add-on in https://github.com/QBobWatson/ipe2tikz

## How to install in Mac OS X

Download tikzmod.lua

In **Finder**, press **Cmd+Alt+G** and go to **Users/{your-username}/.ipe/ipelets/**

Create the folder ipelets if it does not exist.

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE** (use e.g. Cmd+Q on it) **and run it again**.

If you prefer the terminal, simply execute:

    mkdir -p ~/.ipe/ipelets/ && cp -f ~/Downloads/tikzmod.lua ~/.ipe/ipelets/


## How to install in GNU/Linux

Download tikzmod.lua

In your file explorer, go to **~/.ipe/ipelets/**

Create the folder ipelets if it does not exist.

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE** (use e.g. Cmd+Q on it) **and run it again**.


If you prefer the terminal, simply execute:

    mkdir -p ~/.ipe/ipelets/ && cp -f ~/Downloads/tikzmod.lua ~/.ipe/ipelets/

## How to install in Microsoft Windows

?

## How to use it

**Step 1.** Select the drawings you want to export to TikZ code.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/selection.png?raw=true" width="600"/>
</p>

**Step 2.** Click on the tab named _Ipelets_ and then go to _Export TikZ code_
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/menu.png?raw=true" width="600"/>
</p>

Now, we have different options

**Step 3.A** Click on _Export selection to clipboard_ to transform the figures into a tex

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A key shortcut for this option is _Cmd+Shift+T_.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Note that you can customize it on the .lua file, see below.
    
**Step 3.B** Click on _Export selection to clipboard (nodes first)_ to first reorganize all \nodes to the top layer and export the code.


**Step 3.C** Click on _Copy preamble to clipboard_ to get the the necessary code for compiling the exported codes into your LaTeX project.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Also, you can customize the preamble on the .lua file!

## Some useful rules to take into account before using it!

**Rule 1. Change some color names to others**

In some occasions, we will want to change the names of the colors for others.

By default, the colors assigned by this add-on to the predefined ones in IPE are preceded by the word "my".

For example, when selecting "lightgreen" in IPE, in the TikZ code it will be specified as "mylightgreen".

However, this can be further customized by editing the .lua file.

**Rule 2. Avoid certain drawings to be exported**

On other occasions, especially with complex drawings, it is common to help yourself by creating guide lines or grids to help you draw.

However, many times we do not want to get rid of those guide lines in case we need to fix a drawing in the future.

Therefore, you can also designate certain forbidden colors in the code, so that objects with those colors will not be exported to the TikZ code.

For example, I have assigned the color "turquoise" to the forbidden colors. In this way, no lines with the color turquoise will appear in the exported TikZ code.

**Rule 3. Text positioning and scaling**

When you put text in the figures, the exported result may not be scaled correctly. _You must fix this manually_ in the IPE Editor as follows:

Select the textbox and go to the **Properties** tab, there, set **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one.

## How to customize it further!
