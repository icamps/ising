In Ubuntu 19.04 (Disco) 64bits.

1-) Install PLplot:
sudo apt install libplplot-dev libplplot16 libplplotfortran0 libplplotwxwidgets1 plplot-doc plplot-driver-cairo plplot-driver-qt plplot-driver-wxwidgets 

2-) Export PKG_CONFIG_PATH=/usr/lib/x86_64-linux-gnu/pkgconfig/

3-) Change Makefile:
From:
FFLAGS += $(shell pkg-config --cflags plplotd-f95)
LDFLAGS = 
LIBS = $(shell pkg-config --libs plplotd-f95)


To:
FFLAGS += $(shell pkg-config --cflags plplot-fortran)
LDFLAGS = 
LIBS = $(shell pkg-config --libs plplot-fortran)

