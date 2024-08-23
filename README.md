# etc1tool

A command line tool for converting between the PNG and
[ETC1](https://registry.khronos.org/DataFormat/specs/1.3/dataformat.1.3.html#ETC1)
image formats. ETC1 is a lossy, fixed-rate (4 bits per texel; 64 bits = 8 bytes
per 4×4 texel block) texture compression format.

## Android Source

This source code was extracted on August 2024 from the Android Open Source
Project. The original source file paths within AOSP:

- `development/tools/etc1tool/etc1tool.cpp`
- `frameworks/native/opengl/include/ETC1/etc1.h`
- `frameworks/native/opengl/libs/ETC1/etc1.cpp`

## Local Modifications

- Added `--encodeETC1S` flag.
- Added `mk.sh` simple build script.

## ETC1S

ETC1S is a subset of the ETC1 format, reducing the number of meaningful bits
per block by 14 (21.875%), from 64 (100%) to 50 (78.125%). If you're already
familiar with ETC1, here's the entirety of the
[ETC1S](https://registry.khronos.org/DataFormat/specs/1.3/dataformat.1.3.html#ETC1S)
specification:

> The ETC1S format is a subset [of] ETC1, simplified to facilitate image
> compression. The blocks use differential encoding (diff bit = 1); Color
> deltas Rd = Gd = Bd = 0, so the two subblocks share base colors. The Table
> codeword for each subblock is identical. Finally, the flip bit is encoded as
> 0 — the subsets are identical anyway.

Where ETC1 splits each 4×4 block into two halves (either 4×2 or 2×4) of
different base colors, ETC1S assigns a single base color to the whole block.
The 4×4 block boundaries are therefore more clearly visible with ETC1S.

[Basis Universal](https://github.com/BinomialLLC/basis_universal) texture
compression uses ETC1S (and another format called UASTC, a subset of ASTC).

## License

Apache 2.
