BINS = sample.elf

EE_CFLAGS = -DUSE_RWOPS
EE_INCS = -I../include -I$(PS2SDK)/ports/include -I$(PS2SDK)/ports/include/SDL
EE_LIBS = -L../lib -L$(PS2SDK)/ports/lib -lsdlmixer -lsdl -lc -lm

all: $(BINS)

install:

%.elf : %.o $(PS2SDK)/ee/startup/crt0.o
	$(EE_CXX) -mno-crt0 -T$(PS2SDK)/ee/startup/linkfile $(EE_LDFLAGS) \
		-o $@ $(PS2SDK)/ee/startup/crt0.o $< $(EE_LIBS)

clean:
	rm -f $(BINS) $(OBJS)

include $(PS2SDK)/Defs.make
include ../../Makefile.eeglobal
