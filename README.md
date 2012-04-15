Pdf-renderer improvement branch
=============================

This is a fork of [pdf-renderer](http://java.net/projects/pdf-renderer) (covered by the LGPL-2.1 license) for improvement purposes.

The principal objective of the fork is to improve the original PDF renderer. The original version is able to handle most of the PDF 1.4 features, but has several bugs and missing functionality.

It uses an [improved version of JPedal's JBig2 decoder API](https://github.com/Borisvl/JBIG2-Image-Decoder).

To do:
------
* some colours are displayed incorrect, there seem to be open issues regarding colour space handling
* some fonts can't be rendered and are replaced with built in fonts 
* embedded Type0 font with a CIDType0 font is not supported correctly. Currently there is a hack in the code to fall back to the built in fonts in this case.

Done:
-----
* support function type 3 rendering (stitching functions)
* support function type 4 rendering (subset of the PostScript language, specification taken from http://www.adobe.com/devnet/acrobat/pdfs/adobe_supplement_iso32000.pdf)
* support for shading patterns and radial shading (type 3)
* support link annotations for being able to render links
* handle alternate colour spaces (colour space plus a function to be applied on the colour values)
* fixes transparency issues / transparent masked images (even though transparency is still not completely supported)
* corrected handling of overlapping shapes
* better support Type0 fonts that use embedded CID fonts
* jbig2 image format decoded with (improved) "jpedal" API
* DeviceCMY / DeviceRGB colour spaces are working now, but some PDFs are still displayed in wrong format.
* Improved reading of CMYK images. Some colours are still displayed wrong. (using the ch.randelshofer.media.jpeg.JPEGImageIO API)
* Improved run length decoding (corrected reading of buffer) 
* fixed compression issues
* fixed size of outline fonts 
* fixed several exceptions
* Fixes various font encoding problems (Flex in Type 1, wrong stemhints in Type 1C and inverted presentation of Type 3)
