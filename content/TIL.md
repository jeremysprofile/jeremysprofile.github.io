----
title: Today I Learned
description: A list of facts that interested or surprised me.
---


# PNG images have a physical size
PNG images can also specify a DPI, meaning a PNG file can have a physical height and width associated with it.
This information is stored in the metadata for the image.
Here's how to retrieve it:
```bash
xxd ~/dl/image.png | head
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 2ee0 0000 1194 0802 0000 0010 bf81  ................
00000020: ca00 0000 0173 5247 4201 d9c9 2c7f 0000  .....sRGB...,...
00000030: 0009 7048 5973 0000 5c46 0000 5c46 0114  ..pHYs..\F..\F..
```
According to [the spec](http://www.libpng.org/pub/png/spec/1.2/PNG-Chunks.html#C.pHYs):

> The pHYs chunk specifies the intended pixel size or aspect ratio for display of the image. It contains:

   Pixels per unit, X axis: 4 bytes (unsigned integer)
   Pixels per unit, Y axis: 4 bytes (unsigned integer)
   Unit specifier:          1 byte

The following values are defined for the unit specifier:

   0: unit is unknown
   1: unit is the meter

When the unit specifier is 0, the pHYs chunk defines pixel aspect ratio only; the actual size of the pixels remains unspecified.

Conversion note: one inch is equal to exactly 0.0254 meters. 
