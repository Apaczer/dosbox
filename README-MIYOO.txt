
How to compile DosBox for Miyoo:

./autogen.sh
./configure --host=arm-linux --enable-core-inline \
CXXFLAGS="-g -O2 -march=armv5te -mtune=arm926ej-s -pipe -fno-builtin -fno-common -ffast-math -fomit-frame-pointer -fexpensive-optimizations -frename-registers" \
LIBS="$(pkg-config --libs sdl SDL_gfx SDL_image)"

---
for SDL_sound to work, you have to add following libs & edit config.h
LIBS+="-lSDL_sound -lspeex -logg"

----
ovewrite default in config.h

OLD="\/\* #undef C_DYNREC \*\/"
NEW="#define C_DYNREC 1"
sed -i "s/$OLD/$NEW/g" config.h

OLD="#define C_TARGETCPU UNKNOWN"
NEW="#define C_TARGETCPU ARMV4LE"
sed -i "s/$OLD/$NEW/g" config.h

----
edit dosbox.conf

mapperfile=mapper.txt