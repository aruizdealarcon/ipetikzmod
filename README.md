# The ipetikzmod plugin


This plug-in for the <a href="https://ipe.otfried.org/">IPE editor</a> allows you to export **clean, well-structured TikZ code** directly from selected graphics.
Derived from <a href="https://github.com/QBobWatson/ipe2tikz">ipe2tikz</a>, it introduces improvements that make the generation and editing of LaTeX-compatible figures more efficient.

**First**, design your figure in the IPE editor:
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/intro1.jpg?raw=true" width="800"/>
</p>

**Second**, select the elements you wish to export and press `Ctrl+Shift+T` (or `Cmd+Shift+T` on macOS).
The corresponding TikZ code is automatically copied to your clipboard.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/intro2.jpg?raw=true" width="800"/>
</p>

**Third**, paste the copied TikZ code directly into your LaTeX document and compile it.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/intro3.jpg?raw=true" width="800"/>
</p>

When using the plug-in for the first time, include a short TikZ preamble in your LaTeX document.

To obtain it automatically, open the tab _Ipelets_ → _Export TikZ code_ → _Copy preamble into clipboard_.

Then paste it into your LaTeX file between `\documentclass{...}` and `\begin{document}`.

## Why using it?

Some advantages on using IPE together with this plug-in are the following:

**No need to learn TikZ or compute coordinates manually.**
The plug-in eliminates the need to calculate coordinates, distances, or angles. If you produce a large number of graphics, it can save a considerable amount of time and effort.

**Improved maintainability compared to code.**
When returning to a project after some time, it is often difficult to recall how a specific figure was generated. With this plug-in, you can simply reopen the figure in IPE and continue editing it directly, without inspecting or rewriting code.

**Simplified creation of curves.**
Writing TikZ code for curves can be tedious. In IPE, you can easily manipulate control nodes to draw curves with the desired shape.

**Automatic adaptation to TikZ defaults.**
The plug-in configures IPE to use parameters consistent with TikZ’s default settings. Color definitions match those of the xcolor package, and other parameters—such as line thickness and arrow styles—follow TikZ conventions.

**Compact LaTeX preamble.**
The necessary LaTeX preamble is minimal and can be generated automatically with just two clicks.

**Seamless integration with LaTeX.**
The generated TikZ code can be copied directly from IPE into your LaTeX document, ensuring a smooth workflow.

# Installation

## How to install in OSX and Linux

**Step 1: Download the files**

Obtain the files `ipetikzmod.lua` and `ipetikzmod.isy` from this repository.

**Step 2: Locate your IPE configuration directory**

In Finder (macOS) or your file explorer (Linux), navigate to: `~/.ipe/`

**Step 3: Create the necessary folders**

If they do not already exist, create the following subdirectories inside `~/.ipe/`:

`~/.ipe/ipelets/`
`~/.ipe/styles/`

**Step 4: Copy the files**

Place the downloaded file `ipetikzmod.lua` in `~/.ipe/ipelets/`

Place the downloaded file `ipetikzmod.isy` in `~/.ipe/styles/`

**Step 5: Restart IPE**

Close all running instances of IPE (on macOS, use `Cmd + Q`) and then relaunch it.

**Note for macOS users**

If the IPE editor cannot locate MacTeX, you can specify its path manually.

Create a configuration file named ipe.conf in `~/.ipe/` with the following content:

`IPELATEXPATH=/usr/local/texlive/2025/bin/universal-darwin`

## How to install in Windows

Download `ipetikzmod.lua` and `ipetikzmod.isy` from this repository.

In the File Explorer, go to `$USERPROFILE\Ipelets`

Copy `ipetikzmod.lua` file into that folder.

In the File Explorer, go to `$USERPROFILE\Styles`

Copy `ipetikzmod.isy` file into that folder.

**Close all instances of IPE and run it again**.

# A simple case of usage

### Step 0. Prepare the drawings in the IPE editor.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_01.jpg?raw=true" width="800"/>
</p>

### Step 1. Select the drawings you want to export to TikZ code.

You can do this by simply mantaining the Cmd/Win key pressed and clicking the mouse.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_02.jpg?raw=true" width="800"/>
</p>

### Step 2. Click on the tab named _Ipelets_ and then go to _Export TikZ code_


Click on **Export selection to clipboard** to transform the figures into a tex

A key shortcut for this option is **Cmd+Shift+T**.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_03.jpg?raw=true" width="800"/>
</p>


### Step 3. Paste into your LaTeX project and compile it

For the first time, you will need to copy the preamble include the tikz package and some styles.

The following is the corresponding example of piece of code and compiled output.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_04.jpg?raw=true" width="800"/>
</p>

## A few useful rules and features

### Feature #1. New colors

By default, the colors found with these addons are the ones defined by the package _xcolor_ with the option _dvipsnames_.

We have chosen the following colors, replacing and extending the original ones from the IPE editor:

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/paleta.png?raw=true" height="300"/>
</p>

### Feature #2. Avoid certain drawings to be exported

On other occasions, especially with complex drawings, it is common to help yourself by creating guide lines or grids to help you draw.

However, many times we do not want to get rid of those guide lines in case we need to fix a drawing in the future.

Therefore, we have included a color named _DoNotExport_. No figures with this color will appear in the exported TikZ code, even if they are selected.

For example, in the following setting, the diagonal lines are set up with the DoNotExport color, and therefore will not appear in the final TikZ code:

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_05.jpg?raw=true" width="800"/>
</p>


### Feature #3. Text positioning and scaling

This add-on sets to have default the following properties for text: **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one with the IPE Editor.

### Feature #4. Load a 1080p beamer layout

In many cases, we do not want to have the original layout, which is very large, but it is much more comfortable to have the layout in the form 1920x1080, i.e. the standard for computer screens.

Therefore, if you select this option, the layout will be loaded with these dimensions, adapted to the actual size of the beamer layout with this aspect ratio.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example_06.jpg?raw=true" width="800"/>
</p>
