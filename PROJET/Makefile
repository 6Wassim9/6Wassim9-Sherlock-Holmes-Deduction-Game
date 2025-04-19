## Makefile

# Compilateur et options
CC      := gcc
CFLAGS  := -Wall -Wextra -g `sdl2-config --cflags`
LDLIBS  := `sdl2-config --libs` -lSDL2_image -lSDL2_ttf -lpthread

# Binaires cibles
TARGETS := server sh13

# Règle par défaut : tout
all: $(TARGETS)

# Compilation de server
server: server.c
	$(CC) $(CFLAGS) -o $@ $< $(LDLIBS)

# Compilation de sh13
sh13: sh13.c
	$(CC) $(CFLAGS) -o $@ $< $(LDLIBS)

# Nettoyage des fichiers générés
clean:
	rm -f $(TARGETS)

.PHONY: all clean

