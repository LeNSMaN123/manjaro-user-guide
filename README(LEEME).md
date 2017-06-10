<!--Original:## Introduction-->
## Introducción

La Guía de usuario nóveles <!--(principiantes o nada ya iré viendo en las correcciones)--> de Manjaro Linux creada con LaTeX (usando LyX).
<!--Original:The Manjaro Linux Beginner's User Guide typeset in LaTeX (using LyX).-->

El estilo usado es [tufte-book](http://wiki.lyx.org/Layouts/Tufte-book). Esto proporciona un diseño muy profesional con mínimo lío. <!-- Menuda traducción xD-->
<!--Original:The style in use is [tufte-book](http://wiki.lyx.org/Layouts/Tufte-book). This provides a very professional layout with minimal fuss.-->

## Descarga
<!--## Download-->

¿Quieres un PDF en vez del código fuente? Cogelo desde el directorio [publicado o release](http://sourceforge.net/projects/manjarolinux/files/release/) asociado en SourceForge. <!-- no si dejar la palabra release en inglés por que en castellano se me hace raro verlo así(correcciones xD)-->
<!--Original:Want a PDF instead of the source? Grab it from the associated [release](http://sourceforge.net/projects/manjarolinux/files/release/) directory on SourceForge.-->

## Instalación
<!--Original:## Installation-->

Para utilizar el diseño de tufte-book dentro de LyX en Manjaro necesitarás instalar los siguientes paquetes: 
<!--Original:To enable the tufte-book layout within LyX on Manjaro you will need to install the following packages:-->

    sudo pacman -S lyx texlive-latexextra texlive-pictures ttf-comfortaa ghostscript

Installing LyX should pick up the base dependencies; tufte-book requires the extra libraries. Remember to reconfigure LyX after installing the new libraries!

## Cover art

Current cover art is created in Inkscape. LyX will neatly insert/append PDF files - to make things easy cover art should therefore be exported as a PDF document.

![Manjaro User Guide cover](https://raw.githubusercontent.com/manjaro/manjaro-user-guide/master/cover.png)

## Generation

To generate the PDF from a command line rather than exporting from within LyX you can use the following:

    lyx --export pdflatex manjaro-user-guide.lyx
    pdflatex manjaro-user-guide
    texindy --language english manjaro-user-guide.idx
    pdflatex manjaro-user-guide
    pdflatex manjaro-user-guide
    gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -sOutputFile=manjaro-user-guide-printer.pdf manjaro-user-guide.pdf

Yes, ```pdflatex``` does require multiple runs.
