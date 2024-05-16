This plugin for the IPE editor allows you to export clean and customizable TikZ code from a selection of graphics, directly to the clipboard.

It is a fork of Joseph Rabinoff's project github.com/QBobWatson/ipe2tikz

- **No tienes que volver a calcular coordenadas o ángulos en TikZ**. Si tienes que hacer muchos gráficos para tu proyecto, esto puede suponer un gran carga de trabajo, 
- **Es más fácil de mantener que el código**. Si no estás trabajando en un proyecto de manera continua, lo normal es que te olvides de cómo hiciste cierto gráfico, y entonces tienes que ponerte a leer todo el código. Simplemente abre tu proyecto en IPE y sigue editándolo.
- **Las curvas que no son arcos de circunferencia son muy dificiles de imaginar en TikZ**; sin embargo, en el editor puedes manejar los nodos de control y dibujas las curvas a tu antojo.
- **El código es fácilmente importable en LaTeX, directamente desde el portapapeles**; a diferencia del proyecto ipe2tikz, no hace falta lidiar con archivos o cajas de texto, este plugin copia directamente el código limpio de TikZ en el portapapeles, para que lo lleves a tu proyecto en LaTeX como tú prefieras.
- **Si llegas a necesitar modificar el código, puedes hacerlo!**; el código sigue siendo limpio e intuitivo.

# Installation

## How to install in Mac OS X

Download _ipetikzmod.lua_ and _ipetikzmod.isy_ above from this repository.

In **Finder**, press **Cmd+Alt+G** and go to **Users/{your-username}/.ipe/** or simply **~/.ipe/**

Create the folders _styles_ and _ipelets_ if they do not exist.

Copy the .lua file you just downloaded into Users/{your-username}/.ipe/ipelets/

and the .isy file into Users/{your-username}/.ipe/styles/

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

# Usage

## A simple case

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

Click on **Copy preamble to clipboard** to get the the necessary code for compiling the exported codes into your LaTeX project.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Also, you can customize the preamble on the .lua file!

## Some useful rules and features

### Feature #1. Create new colors

In some occasions, we will want to change the names of the colors for others.

By default, the colors found with these addons are the ones defined by the package _xcolor_ with the option _dvipsnames_.

I chose ... among the following, but you can include more if you want or even define new ones.

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/xcolordvips.png?raw=true" width="500"/>
</p>

### Feature #2. Avoid certain drawings to be exported

On other occasions, especially with complex drawings, it is common to help yourself by creating guide lines or grids to help you draw.

However, many times we do not want to get rid of those guide lines in case we need to fix a drawing in the future.

Therefore, you can also designate certain forbidden colors in the code, so that objects with those colors will not be exported to the TikZ code.

For example, I have assigned the color "NotExportable" to the forbidden colors. In this way, no lines with the color NotExportable will appear in the exported TikZ code.

### Feature #3. Text positioning and scaling

This add-on sets to have default the following properties for text: **horizontal alignment** to **center** and **vertical alignment** to **center**.

That makes the origin of the textbox to be the center and _not_ the lower left corner, which is the default one with the IPE Editor.

### Feature #4. Load beamer layout

....

# Some examples

<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/example1.png?raw=true" width="600"/>
</p>

    \begin{tikzpicture}[scale=1]
        \draw[black] (0.96, 1.652) .. controls (0.96, 0.798) and (1.387, 0.372) .. (2.24, 0.372);
        \draw[mydarkorange, myDash_dashed] (0, 1.012) .. controls (0.64, 0.585) and (1.28, 0.585) .. (1.92, 1.012);
        \node[myNode, myNode_disk, myNode_large, myviolet] at (0.32, 1.332) {};
        \node[myNode, myNode_box, myNode_large] at (1.6, 1.332) {};
        \node[myNode, myNode_fdisk, myNode_large, fill=mylightgreen] at (0.32, 0.052) {};
        \draw[virtual, myDash_heavier] (0.752, 0.13) .. controls (1.164, 0.436) and (1.685, 0) .. (1.89, 0.129);
    \end{tikzpicture}
