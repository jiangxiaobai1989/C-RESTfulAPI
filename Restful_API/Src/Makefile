CFLAGS := -MD -g -Wall -O2 
OUTPUTDIR := $(TOPDIR)/Objs
INCLUDE := $(TOPDIR)/Inc
LIBDIR := $(TOPDIR)/Lib
LIB := $(LIBDIR)/libosAdaption.a
SRC := $(wildcard *.c)
OBJS := $(patsubst %.c, $(OUTPUTDIR)/%.o,$(notdir $(SRC)))

all : $(OBJS) $(LIB)

$(LIB) :
	$(MAKE) -C osAdaption

$(OUTPUTDIR)/%.o : %.c
	$(CC) $(CFLAGS) -L$(LIBDIR) -I$(INCLUDE) -MD -c $< -o $@ -lm -losAdaption

sinclude $(OBJS:.o=.d)

.PHONY : all clean

clean :
	rm -rf $(OBJS) $(OBJS:.o=.d)
	$(MAKE) clean -C osAdaption

