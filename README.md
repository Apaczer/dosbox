
How to compile DosBox for Miyoo:

./autogen.sh
./configure --host=arm-linux --disable-x11 --enable-core-inline \
CPPFLAGS="-DDINGUX -DLOWMEM" \
CXXFLAGS="-g -O2 -march=armv5te -mtune=arm926ej-s -pipe -fno-builtin -fno-common -ffast-math -fomit-frame-pointer -fexpensive-optimizations -frename-registers" \
LIBS="$(pkg-config --libs sdl SDL_gfx SDL_image)"

---
for SDL_sound to work (needed for "gus"?), you have to add following libs & edit config.h
LIBS+="-lSDL_sound -lspeex -logg"

----
edit dosbox.conf & add default mapper

mapperfile=mapper.txt