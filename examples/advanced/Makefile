# For Mac.
CFLAGS += -I/opt/homebrew/opt/sqlite/include
LDFLAGS += -L/opt/homebrew/opt/sqlite/lib

all:
	env LIBS="-lsqlite3" CFLAGS="$(CFLAGS)" LDFLAGS="$(LDFLAGS)" mys run
