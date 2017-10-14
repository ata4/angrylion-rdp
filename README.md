# Angrylion RDP Plus

This is a conservative fork of angrylion's RDP plugin that aims to improve performance add new features while retaining the accuracy of the original plugin.

### Current features
* More maintainable code base by dividing the huge n64video.cpp into smaller pieces.
* Improved portability by separating the emulator plugin interface and window management from the RDP emulation core.
* Multi-threaded rendering support, which increases performance on multi-core CPUs significantly.
* Replaced deprecated DirectDraw interface with a modern OpenGL 3.3 implementation.
* Added manual window sizing.
* Added fullscreen support.
* Added BMP screenshot support.
* Added settings GUI.
* Added Mupen64Plus support.

Tested with Project64 2.3+. May also work with Project64 1.7 with a RSP plugin of newer builds (1.7.1+).

The Mupen64Plus plugin was tested with Mupen64Plus 2.5 using the [mupen64plus-rsp-cxd4](https://github.com/mupen64plus/mupen64plus-rsp-cxd4) plugin.

### Building

To build the project with Visual Studio (2015+), you currently need to have Python 3 installed, which is used to fetch Git metadata and write it to `version.h`.
You can also build without, but then you have to copy `version.h.in` to `version.h` and disable the custom build event in the core project.

The glLoadGen files (`gl_core_3_3` and `wgl_ext`) were generated using the following parameters:

    lua\lua5.1.exe LoadGen.lua core_3_3 -style=noload_c -spec=gl -version=3.3 -profile=core -stdext=gl_ubiquitous.txt -stdext=gl_core_post_3_3.txt
    lua\lua5.1.exe LoadGen.lua ext -style=noload_c -spec=wgl -ext WGL_EXT_swap_control

Building with CMake is also possible, but currently supports the mupen64plus plugin and the retracer only.

### WIP builds

WIP builds can be found [here](https://github.com/ata4/angrylion-rdp-plus/issues/29) for those who don't want to or can't compile the project on your own.

WIP builds have the latest features and fixes, and are generally stable, but may introduce bugs.

They are compatible with Project64 1.7 and the newer 2.x versions.

### Credits
* Angrylion, Ville Linde, MooglyGuy and others involved for creating an awesome N64 RDP reference software.
* theboy181 - Testing. Lots of testing.
* fallaha56 - Donator.
* loganmc10 - Mupen64Plus plugin implementation.
