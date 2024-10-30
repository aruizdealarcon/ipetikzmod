# The plug-in

This is a plugin for the <a href="https://ipe.otfried.org/">IPE editor</a> that exports clean TikZ code from a selection of graphics to the clipboard.

This project is a fork of Joseph Rabinoff's <a href="https://github.com/QBobWatson/ipe2tikz">ipe2tikz</a>.

Some advantages on using IPE together with this plug-in are the following:


## There is no need to calculate coordinates, distances nor angles in TikZ

If you need to create many graphics, this plug-in can save you a significant amount of time and effort.



**(ii) It is easier to maintain than code.**

If you are not working on a project continuously, you might forget how you created a particular figure and need to go through the code.

With this plugin, you can simply open your project in the IPE editor and continue editing it.


**(iii) Writing TikZ code for curves can be challenging.**

However, within the IPE editor, you can manage control nodes and draw the curves as you want.


**(iv) The code can be easily imported into LaTeX, directly from the clipboard.**

There is no need to handle files nor other elements (compared to the original plug-in ipe2tikz).

This plugin exports clean and formatted TikZ code directly to the clipboard.

If you need to modify the TikZ code, you can do so: the code remains clean and readable.


**(v) The preamble needed in LaTeX is extremely small and is obtained with just two clicks.**

This plug-in makes the IPE editor to load adapting it to TikZ's defaults, unlike IPE's stylesheet.

Additionally, all color definitions match those in the _xcolor_ package. Other parameters, such as line thickness, arrow styles and many more adapt to the _tikz_ package predefined ones.

# Installation

## How to install in OSX and Linux

Download _ipetikzmod.lua_ and _ipetikzmod.isy_ above from this repository.

In **Finder** or your file explorer, go to...

    ~/.ipe/

(In OSX, use press Cmd+Alt+G to specify a path on Finder)

Create the folders _styles_ and _ipelets_ if they do not exist.

**Copy the file _ipetikzmod.lua_** you just downloaded into

    ~/.ipe/ipelets/

and **copy the file _ipetikzmod.isy_** into
    
    ~/.ipe/styles/

**Close all instances of IPE** (in OSX use Cmd+Q on it) **and run it again**.

## How to install in Windows

Download tikzmod.lua from this repository.

In the File Explorer, go to **$USERPROFILE\Ipelets**

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE and run it again**.

# A simple case of usage

### Step 0. Prepare the drawings in the IPE editor.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_1.png?raw=true" width="800"/>
</p>

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

Therefore, we have included a color named _DoNotExport_. No figures with this color will appear in the exported TikZ code.

### Feature #3. Text positioning and scaling

This add-on sets to have default the following properties for text: **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one with the IPE Editor.

### Feature #4. Load a 1080p beamer layout

In many cases, we do not want to have the original layout, which is very large, but it is much more comfortable to have the layout in the form 1920x1080, i.e. the standard for computer screens.

Therefore, if you select this option, the layout will be loaded with these dimensions, adapted to the actual size of the beamer layout with this aspect ratio.

