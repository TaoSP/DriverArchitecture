# #####################################################################
# Makefile
# Author : Huangtao
# Version: V1.0.0  2020-01-01 Create
# #####################################################################

MAIN_ROOT = $(shell pwd)

CFLAGS := -I$(PROJ_ROOT)/Include/osa
CFLAGS += -I$(PROJ_ROOT)/Include/pdc
CFLAGS += -I$(PROJ_ROOT)/Include/app
CFLAGS += -c -o

AFLAGS := -rc

SRCS := $(wildcard *.cpp)
OBJS := $(SRCS:%.cpp=%.o)
LIB := $(MAIN_ROOT)/libmain.a

.PHONY: clean all
default: all

%.o: %.cpp
	$(CPP) $(CFLAGS) $@ $<

$(LIB): $(OBJS)
	$(AR) $(AFLAGS) $@ $^

app:
	$(MAKE) -C $(PROJ_ROOT)/Src/App/hello


all: app $(LIB)
	$(CP) $(LIB) $(PROJ_LIB)

clean:
	$(MAKE) -C $(PROJ_ROOT)/Src/App/hello clean
	@-$(RM) $(OBJS) $(LIB)
