﻿# OoT_Compressor

---

This is a compressor for The Legend of Zelda: Ocarina of Time. It takes a decompressed OoT ROM and a table (Use tableExtract for this), and creates a compressed version of the ROM. From what I've noticed, emulators don't seem to like decompressed ROMs very much, and they occasionally crash when trying to pause. This problem goes away\* with compressed ROMs. Also, if you're trying to inject a game into a .wad file for a Virtual Console, it won't accept decompressed ROMs, so you'll want to compress it.

This program will probably make your CPU fans run very loud, as it pins every core in your processor to 100% for a while. This is done to make it much faster than other compressors, at the cost of a bit of noise.

\*Results may vary

---

Although you shouldn't need to compile, here's what you'll need to use to do so

Compiling the compressor (Mac/Linux): gcc -g -O3 -o Compress.out compressor.c

Compiling the compressor (Windows): gcc -g -O3 -o Compress.exe compressor.c -lws2_32

Compiling the table extractor (Mac/Linux): gcc -g -O3 -o TabExt.out tableExtractor.c

Compiling the table extractor (Windows): gcc -g -O3 -o TabExt.exe tableExtractor.c -lws2_32

I got this to compile on Windows, but I needed a specific version of minGW to do it. I downloaded msys2 (https://www.msys2.org/) then used *pacman -S mingw-w64-x86_64-gcc* to get a version that could compile it, so hopefully that will work.

---

Compressor Usage: Compress.exe [Input ROM]

Table Extractor usage: TabExt.exe [Input ROM]

Compressor Notes: The compressor relies on a file called *table.bin* being in the same directory as the compressor executable. This file is created by the table extractor, so if you need one, just run that. The compressor will take whatever name you gave it as an argument, and add "-comp" to the end. So for example, if you gave it Zelda.z64, it would produce Zelda-comp.z64, which is the compressed ROM.

Table Extractor Notes: The table extractor takes a compressed ROM, and extracts the file table that's in the ROM for the compressor to use

General Notes: I've only tested this compressor for NTSC 1.0 ROMs, because this was made to complement the OoT Item Randomiser so that it would be easier to make VC injects of the randomised ROMs. It may work with other versions, but I make no guarantees.


