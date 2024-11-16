# Odin Color Buffer

A very basic example of implementing a color buffer on the CPU on submitting it as a dynamic texture to the GPU using the awesome `sokol` library. Heavily inspired by [Pikuma's 3D Computer Graphics Course](https://pikuma.com/courses/learn-3d-computer-graphics-programming).

## Prerequisites 
Make sure you have [Odin](https://odin-lang.org/) installed. Next you have to compile the Sokol libraries for your operating system. For that just execute the build scripts (depending on your operating system)

```bash
cd src/sokol
./build_clibs_macos.sh # Compiling Sokol Libs for MacOS
./build_clibs_linux.sh # Compiling Sokol Libs for Linux 
./build_clibs_windows.cmd # Compiling Sokol Libs for Windows 
```

## Running the example
With the prerequisites in place it should be as simple as running

```bash
odin run src/
```

## Acknowledgments
I strugled a bit due to an endianess related issue in my pixel format. Turns out MacOS is `little endian` and therefore even when the pixel_format is specified as `RGBA8` the hex values are interepreted in the `ABGR8` format. See also the comment in the [source code](https://github.com/floooh/sokol/blob/2c6fc7470e9b9121a178e6e68c55f2f06fac4647/sokol_app.h#L898). Thanks a lot for `NobodySpecial` and the awesome [Odin Forum](https://forum.odin-lang.org/t/rendering-pixel-buffer-with-sokol-to-screen/402/3) for pointing me in the right direction.

Secondly thanks a lot for the awesome [Sokol Example Gallery](https://floooh.github.io/sokol-html5/index.html). The `quad` example provided a great starting point.

