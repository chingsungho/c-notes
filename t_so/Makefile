CFLAGS += -I. -fPIC -O2 -DNDEBUG $(OPTFLAGS)
LDFLAGS += -lm $(OPTLIBS)

all: use
use: use.o so.o

dev: CFLAGS = -I. -fPIC -g -O2 -rdynamic $(OPTFLAGS)
dev: all

.PHONY: clean
clean:
	-rm use use.o so.o