
## DOSBox SVN (for MiyooCFW)

This is a downstream fork of SVN code-0 trunk (r4494)

## How to build

- Cross-Compile for Miyoo
  - configure
  
  		./autogen.sh
		./configure --host=arm-linux --disable-x11 --enable-core-inline --enable-platform=miyoo

  - compile

		make -j$(nproc)

  - pkg distribute

		gm2xpkg src/platform/miyoo/pkg.cfg

- Native DINGUX test build
  - configure

  		./autogen.sh
		./configure --enable-platform=dingux

  - compile

		make -j$(nproc)

---
for SDL_sound to work (needed for "gus"?), you have to add following libs
LIBS+="-lSDL_sound -lspeex -logg" (due to may be missing pkg-config macro in SDL_sound repo) & edit config.h by adding define

----
edit dosbox-*.conf & add mapper-*.txt file for your needs

## How to cross-compile on MINGW64 for win32

- Configure & Build  
There is no i686 libs of libphysfs so you have to build it yourself, but 3.2 src is using old cmake (which also need to be installed manually), 
you can however download archive release of i686 from https://github.com/msys2/msys2-archive/releases#release-2022-12-16-mingw32 

		export ACLOCAL_PATH=/mingw32/share/aclocal
		export PATH="/mingw32/bin:$PATH"
		./configure   --build=x86_64-w64-mingw32   --host=i686-w64-mingw32   CC=i686-w64-mingw32-gcc
		make -j$(nproc)

- Install  
Copy necessary libs from "/mingw32/bin" to workdir of `dosbox.exe`

## CREDITS
- @dmitrysmagin for first DINGUX port (to GCW0) and Virtual Keyboard implementation and TBH base src for MIYOO port which ppl used for years unknowingly.
- ppl from vogons.org forum and their original patches for PhysFS archive (Moe) and savestate (ZenJu)
- dosbox-staging team for their work on cleaning up of DOSBox source code.
- original authors & maintainers of upstream DOSBox svn