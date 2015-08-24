# The new home of this project is https://github.com/kjellmf/svg2tikz #

# Inkscape to TikZ exporter #



An [Inkscape](http://www.inkscape.org) extension for exporting SVG paths as TikZ/PGF paths. Similar to my [Blender to TikZ exporter](http://www.fauskes.net/code/blend2tikz/).

**Note:** This extension is a work in progress.

## Example ##

![http://inkscape2tikz.googlecode.com/svn/trunk/doc/img/example.png](http://inkscape2tikz.googlecode.com/svn/trunk/doc/img/example.png)

Exporting the above path will generate the following code:

```

\documentclass{article}
\usepackage{tikz}

\usepackage[active,tightpage]{preview}
\PreviewEnvironment{tikzpicture}

\begin{document}
\definecolor{cff8080}{RGB}{255,128,128}

\begin{tikzpicture}[y=0.80pt,x=0.80pt,yscale=-1]
\begin{scope}[draw=black,line join=round,miter limit=4.00,line width=3.200pt]
  \path[draw=black,fill=cff8080,line join=round,even odd rule,line cap=butt,miter
    limit=4.00,line width=3.200pt] (91.0455,165.7194) rectangle
    (250.7252,347.8104);
  \path[draw=black,line join=round,even odd rule,line cap=butt,miter
    limit=4.00,line width=3.200pt] (168.0839,258.1656) .. controls
    (169.6992,260.2725) and (166.0408,261.3824) .. (164.5822,260.8503) .. controls
    (160.6293,259.4083) and (160.6636,254.1057) .. (162.7146,251.1621) .. controls
    (166.3833,245.8967) and (174.0594,246.2369) .. (178.5892,250.1116) .. controls
    (185.2369,255.7979) and (184.5602,266.1224) .. (178.8226,272.1726) .. controls
    (171.1753,280.2366) and (158.1221,279.2067) .. (150.5752,271.5890) .. controls
    (141.0782,262.0028) and (142.4690,246.1872) .. (151.9759,237.1551) .. controls
    (163.4900,226.2161) and (182.0854,227.9716) .. (192.5962,239.3729) .. controls
    (204.9828,252.8090) and (202.8604,274.1941) .. (189.5613,286.1796) .. controls
    (174.2071,300.0173) and (150.0257,297.5267) .. (136.5682,282.3277) .. controls
    (121.2770,265.0577) and (124.1368,238.0757) .. (141.2372,223.1481) .. controls
    (160.4213,206.4017) and (190.2069,209.6312) .. (206.6032,228.6342) .. controls
    (224.8061,249.7311) and (221.2064,282.3227) .. (200.3000,300.1866);
\end{scope}

\end{tikzpicture}
\end{document}
```

## Installing ##

Installing is as simple as copying the script (unless it resides in your path) and its INX files to the Inkscape extensions directory.

### Windows ###

Copy the `tikz_extport.py` file and the `tikz_export_effect.inx` and `tikz_export_output.inx` files to your `inkscape/share/extensions` directory.

### Linux and OSX ###

Copy the `tikz_extport.py` file and the `tikz_export_effect.inx` and `tikz_export_output.inx` files to your `home/.inkscape/extensions` directory.
If you are using Inkscape 0.47 the directory is `home/.config/inkscape/extensions`.

Additionally you have to copy the following dependencies to the same directory as above:
  * inkex.py
  * simplestyle.py
  * simplepath.py

The above files should be bundled with Inkscape. Look in the main extensions directory. You can also download them from the [repository](http://inkscape2tikz.googlecode.com/hg/svg2tikz/inkexlib/)

## Usage ##

If the extension has been installed correctly, you will find the exporter in the `Effects -> Export -> Export to TikZ path...` menu. You can also select `Save As` and select `TikZ code` as output format.

If any objects are selected, only the selected objects will be exported. If no objects are selected, every object will be exported.

## Features ##

  * All SVG paths and shapes are exported
  * Text is exported as TikZ nodes
  * All graphical properties, except shading, supported
  * High level output. Easy to modify.

## Limitations ##

  * No support for markers. If markers are needed, convert stroke to path before export.
  * No shadings or patterns yet
  * The generated code is unnecessary complex. Smarter output is a priority.
  * No support for style references yet.

