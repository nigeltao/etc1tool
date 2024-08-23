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

- Added `mk.sh` simple build script.

## License

Apache 2.
