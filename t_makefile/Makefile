SHELL := /usr/bin/bash
srcs0 = $(shell shopt -s globstar && ls **/*.c)

srcs := $(wildcard *.c)
srcs += $(wildcard sub1/*.c)
srcs += $(wildcard sub1/sub2/*.c)

objs := $(patsubst %.c,%.o,$(srcs))

CFLAGS += -I. -Isub1 -Isub1/sub2 -fPIC -O2 -DNDEBUG $(OPTFLAGS)
LDFLAGS += -lm $(OPTLIBS)

#
# -Lsopath -lmyso -Wl,-rpath=sopath:sopath1
#

all: hello

dev: CFLAGS = -I. -Isub1 -Isub1/sub2 -fPIC -g -O2 -rdynamic $(OPTFLAGS)
dev: all

hello: $(objs)
# 	cc -o $@ $(objs)

.PHONY: clean
clean:
	-rm hello $(objs)
