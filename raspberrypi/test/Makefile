# glestest makefile
# Global definitions

CC        = gcc
OBJS      = ../gles_video.o test.o
BIN       = glestest

# Platform specific definitions 
VPATH     += ../
CFLAGS    +=  -D_LINUX
LIBS      += -L$(SDKSTAGE)/opt/vc/lib/ -lbrcmGLESv2 -lbrcmEGL -lopenmaxil -lbcm_host -lvcos -lvchiq_arm -lpthread -lrt 
INCLUDES  += -I$(SDKSTAGE)/opt/vc/include -I$(SDKSTAGE)/opt/vc/include/interface/vcos/pthreads
INCLUDES  += -I$(SDKSTAGE)/opt/vc/include/interface/vmcs_host/linux

# Compilation:

all:	$(BIN)

%.o: %.c
	$(CC) $(CFLAGS) $(INCLUDES) -c -o $@ $<

$(BIN): $(OBJS)
	$(CC) $(OBJS) $(LIBS) -o $(BIN)

clean:
	rm -f *.o $(BIN)

