This project consists of an add-on for the IPE editor.

It is a fork of Joseph Rabinoff's add-on in https://github.com/QBobWatson/ipe2tikz.

The two main differences are that:
(1) there are more options to customize the output, and
(2) you can **directly export it to the clipboard**, so you don't have to work with files, text-boxes, but you can directly copy the code into your LaTeX project.

## How to install in Mac OS X

Download tikzmod.lua

In Finder, click on Go > Go to folder (or use Cmd + Alt + G) and go to Users/{your-username}/.ipe/Ipelets/

Copy the .lua file into that folder.

Close all instances of IPE (use e.g. Cmd + Q) and restart it.

## How to install in GNU/Linux


## How to install in Microsoft Windows


## How to use it

1. Select the drawings you want to export to TikZ code.
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/selection.png?raw=true" width="600"/>
</p>

3. Click on the tab named _Ipelets_ and then go to _Export TikZ code_
<p align="center">
<img src="https://github.com/aruizdealarcon/ipetikzmod/blob/main/readme_files/menu.png?raw=true" width="600"/>
</p>

Now, we have different options

2.1 Click on _Export selection to clipboard_ to transform the figures into a tex

    A nice key shortcut for this option is _Cmd + Alt + T_ (in OSX), or _Win + Alt + T_ (in GNU/Linux and MS Windows).
    
2.2 Click on _Export selection to clipboard (nodes first)_ to first reorganize all \nodes to the top layer and export the code.


2.3 Click on _Copy preamble to clipboard_ to 

    By the way, you can customize the preamble on the .lua file!

## Some useful rules

**Rule 1. Change some color names to others**

**Rule 2. Avoid certain drawings to be exported**

## How to customize it
