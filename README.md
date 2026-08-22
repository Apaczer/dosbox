
## DOSBox SVN (for MiyooCFW)

This is a downstream fork of SVN code-0 trunk (r4494)

## How to build

- Cross-Compile for Miyoo
  - configure
  
  		./autogen.sh
		./configure --host=arm-linux --disable-x11 --enable-core-inline \
		CPPFLAGS="-DMIYOO -DDINGUX -DLOWMEM" \
		CXXFLAGS="-g -O2 -march=armv5te -mtune=arm926ej-s -pipe -fno-builtin -fno-common -ffast-math -fomit-frame-pointer -fexpensive-optimizations -frename-registers" \
		LIBS="$(pkg-config --libs sdl SDL_gfx SDL_image)"

  - compile

		make -j$(nproc)

- Native DIGNUX test build
  - configure

  		./autogen.sh
		./configure \
		CPPFLAGS="-DDINGUX" \
		LIBS="$(pkg-config --libs sdl SDL_gfx SDL_image)"

  - compile

		make -j$(nproc)


---
for SDL_sound to work (needed for "gus"?), you have to add following libs & edit config.h
LIBS+="-lSDL_sound -lspeex -logg"

----
edit dosbox.conf & add default mapper

mapperfile=mapper.txt