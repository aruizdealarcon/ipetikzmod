This plugin for the IPE editor allows you to export clean TikZ code from a selection of graphics, directly to the clipboard.

It is a fork of Joseph Rabinoff's github.com/QBobWatson/ipe2tikz.

Some advantages on using IPE and this plugin are the following:

**There is no need to calculate coordinates, distances nor angles in TikZ.**

If you need to create many graphics, this plugin can save you a significant amount of time and effort.

**It is easier to maintain than code.**

If you are not working on a project continuously, you might forget how you created a particular figure and need to go through the code.

With this plugin, you can simply open your project in the IPE editor and continue editing it.

**Designing curves that are not arcs of a circle in TikZ can be challenging.**

However, within the IPE editor, you can manage control nodes and draw the curves as you need.

**The code can be easily imported into LaTeX directly from the clipboard.**

There is no need to handle files nor other elements, compared to ip2tikz. This plugin copies the clean TikZ code directly to the clipboard; and if you need to modify the code, you can do so; the code remains clean and intuitive.

**The preamble for including TikZ and style specifications is extremely small and can be obtained with just two clicks.**

When you load the IPE editor with this plugin, the styles adapt to TikZ's defaults, unlike IPE's stylesheet. Additionally, all color definitions match those in the xcolor package.

# Installation

## How to install in Mac OS X

Download _ipetikzmod.lua_ and _ipetikzmod.isy_ above from this repository.

In **Finder**, press **Cmd+Alt+G** and go to

    Users/{your-username}/.ipe/

Create the folders _styles_ and _ipelets_ if they do not exist.

**Copy the file _ipetikzmod.lua_** you just downloaded into

    Users/{your-username}/.ipe/ipelets/

and **copy the file __ipetikzmod.isy_** into
    
    Users/{your-username}/.ipe/styles/

**Close all instances of IPE** (use e.g. Cmd+Q on it) **and run it again**.

## How to install in GNU/Linux

Before installing it, make sure you have xsel or xclip installed.

Download _tikzmod.lua_ from this repository.

In your file explorer, go to the path **~/.ipe/ipelets/**

Create the folder _ipelets_ if it does not exist.

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE and run it again**.

If you prefer the terminal, simply execute:

    mkdir -p ~/.ipe/ipelets/ && cp -f ~/Downloads/tikzmod.lua ~/.ipe/ipelets/

## How to install in Microsoft Windows

Download tikzmod.lua from this repository.

In the File Explorer, go to **$USERPROFILE\Ipelets**

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE and run it again**.

# A simple case of usage

### Step 1. Select the drawings you want to export to TikZ code.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_1.png?raw=true" width="800"/>
</p>

### Step 2. Click on the tab named _Ipelets_ and then go to _Export TikZ code_


Click on **Export selection to clipboard** to transform the figures into a tex

A key shortcut for this option is **Cmd+Shift+T**.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_2.png?raw=true" width="800"/>
</p>


### Step 3. Copy to your LaTeX project and compile it

For the first time, you will need to copy the preamble include the tikz package and some styles.

The following is the corresponding example of piece of code and compiled output.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_3.png?raw=true" width="800"/>
</p>

## A few useful rules and features

### Feature #1. Create new colors

In some occasions, we will want to change the names of the colors for others.

By default, the colors found with these addons are the ones defined by the package _xcolor_ with the option _dvipsnames_.

I chose ... among the following, but you can include more if you want or even define new ones.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/paleta.png?raw=true" height="300"/>
</p>

### Feature #2. Avoid certain drawings to be exported

On other occasions, especially with complex drawings, it is common to help yourself by creating guide lines or grids to help you draw.

However, many times we do not want to get rid of those guide lines in case we need to fix a drawing in the future.

Therefore, I have assigned the color _DoNotExport_ to the forbidden colors. In this way, no lines with this color will appear in the exported TikZ code.

### Feature #3. Text positioning and scaling

This add-on sets to have default the following properties for text: **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one with the IPE Editor.

### Feature #4. Load beamer layout

....

