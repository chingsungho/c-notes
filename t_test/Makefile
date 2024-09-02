CFLAGS += -I. -fPIC -O2 -DNDEBUG $(OPTFLAGS)
LDFLAGS += -lm $(OPTLIBS)

all: t

dev: CFLAGS = -I. -fPIC -g -O2 -rdynamic $(OPTFLAGS)
dev: all

.PHONY: clean
clean:
	-rm t