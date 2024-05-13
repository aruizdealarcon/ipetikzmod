This project consists of an add-on for the IPE editor that exports clean and customizable TikZ code from a selection of graphics, directly to the clipboard.

It is a fork of Joseph Rabinoff's add-on in https://github.com/QBobWatson/ipe2tikz

# Installation

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

In your file explorer, go to the path **~/.ipe/ipelets/**

Create the folder _ipelets: if it does not exist.

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE and run it again**.


If you prefer the terminal, simply execute:

    mkdir -p ~/.ipe/ipelets/ && cp -f ~/Downloads/tikzmod.lua ~/.ipe/ipelets/

## How to install in Microsoft Windows

Download tikzmod.lua

In the File Explorer, go to **$USERPROFILE\Ipelets**

Copy the .lua file you just downloaded into that folder.

**Close all instances of IPE and run it again**.

# Usage

## How to use it

### Step 1. Select the drawings you want to export to TikZ code.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/selection.png?raw=true" width="600"/>
</p>

### Step 2. Click on the tab named _Ipelets_ and then go to _Export TikZ code_
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/menu.png?raw=true" width="600"/>
</p>

Now, we have different options

### Step 3. Option 1.

Click on **Export selection to clipboard** to transform the figures into a tex

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A key shortcut for this option is _Cmd+Shift+T_.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Note that you can customize it on the .lua file, see below.
    
### Step 3. Option 2.

Click on **Export selection to clipboard (nodes first)** to first reorganize all \nodes to the top layer and export the code.


### Step 3. Option 3.

Click on **Copy preamble to clipboard** to get the the necessary code for compiling the exported codes into your LaTeX project.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Also, you can customize the preamble on the .lua file!

## Some useful rules and features

### Feature #1. Change some color names to others

In some occasions, we will want to change the names of the colors for others.

By default, the colors assigned by this add-on to the predefined ones in IPE are preceded by the word "my".

For example, when selecting "lightgreen" in IPE, in the TikZ code it will be specified as "mylightgreen".

However, this can be further customized by editing the .lua file.

### Feature #2. Avoid certain drawings to be exported

On other occasions, especially with complex drawings, it is common to help yourself by creating guide lines or grids to help you draw.

However, many times we do not want to get rid of those guide lines in case we need to fix a drawing in the future.

Therefore, you can also designate certain forbidden colors in the code, so that objects with those colors will not be exported to the TikZ code.

For example, I have assigned the color "turquoise" to the forbidden colors. In this way, no lines with the color turquoise will appear in the exported TikZ code.

### Feature #3. Text positioning and scaling

When you put text in the figures, the exported result may not be scaled correctly. _You must fix this manually_ in the IPE Editor as follows:

Select the textbox and go to the **Properties** tab, there, set **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one.

## How to customize it further?

You can easily edit the following settings:

The following variable is the number by which the original coordinates of the drawing are divided. Note that the original coordinates may be too large for Latex to handle. The larger the number, the smaller the Latex drawings are compared to IPE drawings.
    
    resFactor = 50

The following variable contains the precision in numbers of decimal places with which coordinates, angles, etc. are calculated. By default, we consider three decimal places.

    roundPrec = 3

For all new styles that will be defined the program will add the following prefix. Here, we have chosen the word "my", so that, for example, all lines that have color blue, will receive the color myblue. We believe this is convenient so that anyone can individually customize their styles and the names do not coincide with default TikZ styles.

    myPrepend = "my"

The following is a delimiter that separates a style and a sub-style. For example, a node having the style myNode may also have a sub-style myNode_cross, which specifies that it is a particular cross.

    delimStyle = "_"

    dashPrepend = "Dash"

-- style added to every \node markings, except for text

    nodeStyleName = "Node"

The following is a list of pairs of two color codes (in string format), which dictate how you should replace the color codes you find with other codes of your choice. For example, the following, which is the default, makes the exporter rename the colors "gold" and "red" with the style "virtual", but you can add and change it as you wish.

    substitutionColors = { { "gold", "virtual" }, { "red", "virtual" } }

-- the drawings with this color will be discarded; use them as axis, rules...
-- do not replace them in the previous setting!

    forbiddenColors = { "turquoise" }

-- new line append for "\draw" use "\n" in that case for more readability, otherwise for more compact code, leave empty ""

    drawNewLine = ""

-- ...

    drawIndent = ""


# Some examples



    \begin{tikzpicture}[scale=1]
        \draw[black] (0.96, 1.652) .. controls (0.96, 0.798) and (1.387, 0.372) .. (2.24, 0.372);
        \draw[myseagreen, myDash_dotted] (0, 1.012) .. controls (0.64, 0.585) and (1.28, 0.585) .. (1.92, 1.012);
        \node[myNode, myNode_disk, myNode_large, myviolet] at (0.32, 1.332) {};
        \node[myNode, myNode_box, myNode_large] at (1.6, 1.332) {};
        \node[myNode, myNode_fdisk, myNode_large, fill=mylightgreen] at (0.32, 0.052) {};
        \draw[virtual, myDash_heavier] (0.752, 0.13) .. controls (1.164, 0.436) and (1.685, 0) .. (1.89, 0.129);
    \end{tikzpicture}
