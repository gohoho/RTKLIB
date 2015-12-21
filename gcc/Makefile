# makefile for shared lib

TARGET_LIB = librtk.so

BINDIR = /usr/local/bin
SRC    = ../src

# for beagleboard
#CTARGET= -mfpu=neon -mfloat-abi=softfp -ffast-math
CTARGET=

OPTION = -DENAGLO -DENAGAL -DENAQZS -DENACMP -DTRACE \
		 -DNFREQ=3 -DNEXOBS=3
CFLAGS = -fPIC -Wall -O3 -ansi -pedantic \
		 -Wno-unused-but-set-variable \
		 -I$(SRC) $(OPTION) $(CTARGET) -g

LDLIBS  = -lm -lrt -lpthread

LDFLAGS = -shared -Wl,--version-script=export.map

all        	 : $(TARGET_LIB)
$(TARGET_LIB): stream.o rtkcmn.o solution.o sbas.o geoid.o
$(TARGET_LIB): rcvraw.o novatel.o ublox.o ss2.o crescent.o skytraq.o
$(TARGET_LIB): gw10.o javad.o nvs.o binex.o rt17.o rtcm.o rtcm2.o
$(TARGET_LIB): rtcm3.o rtcm3e.o preceph.o streamsvr.o
	$(CC) ${CFLAGS} ${LDFLAGS} -o $@ $^

str2str.o  : ../str2str.c
	$(CC) -c $(CFLAGS) ../str2str.c
stream.o   : $(SRC)/stream.c
	$(CC) -c $(CFLAGS) $(SRC)/stream.c
streamsvr.o: $(SRC)/streamsvr.c
	$(CC) -c $(CFLAGS) $(SRC)/streamsvr.c
rtkcmn.o   : $(SRC)/rtkcmn.c
	$(CC) -c $(CFLAGS) $(SRC)/rtkcmn.c
solution.o : $(SRC)/solution.c
	$(CC) -c $(CFLAGS) $(SRC)/solution.c
sbas.o     : $(SRC)/sbas.c
	$(CC) -c $(CFLAGS) $(SRC)/sbas.c
geoid.o    : $(SRC)/geoid.c
	$(CC) -c $(CFLAGS) $(SRC)/geoid.c
rcvraw.o   : $(SRC)/rcvraw.c
	$(CC) -c $(CFLAGS) $(SRC)/rcvraw.c
novatel.o  : $(SRC)/rcv/novatel.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/novatel.c
ublox.o    : $(SRC)/rcv/ublox.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/ublox.c
ss2.o      : $(SRC)/rcv/ss2.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/ss2.c
crescent.o : $(SRC)/rcv/crescent.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/crescent.c
skytraq.o  : $(SRC)/rcv/skytraq.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/skytraq.c
gw10.o     : $(SRC)/rcv/gw10.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/gw10.c
javad.o    : $(SRC)/rcv/javad.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/javad.c
nvs.o      : $(SRC)/rcv/nvs.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/nvs.c
binex.o    : $(SRC)/rcv/binex.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/binex.c
rt17.o     : $(SRC)/rcv/rt17.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/rt17.c
rtcm.o     : $(SRC)/rtcm.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm.c
rtcm2.o    : $(SRC)/rtcm2.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm2.c
rtcm3.o    : $(SRC)/rtcm3.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm3.c
rtcm3e.o   : $(SRC)/rtcm3e.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm3e.c
preceph.o  : $(SRC)/preceph.c
	$(CC) -c $(CFLAGS) $(SRC)/preceph.c

str2str.o  : $(SRC)/rtklib.h
stream.o   : $(SRC)/rtklib.h
streamsvr.o: $(SRC)/rtklib.h
rtkcmn.o   : $(SRC)/rtklib.h
solution.o : $(SRC)/rtklib.h
sbas.o     : $(SRC)/rtklib.h
geoid.o    : $(SRC)/rtklib.h
rcvraw.o   : $(SRC)/rtklib.h
novatel.o  : $(SRC)/rtklib.h
ublox.o    : $(SRC)/rtklib.h
ss2.o      : $(SRC)/rtklib.h
crescent.o : $(SRC)/rtklib.h
skytraq.o  : $(SRC)/rtklib.h
gw10.o     : $(SRC)/rtklib.h
javad.o    : $(SRC)/rtklib.h
nvs.o      : $(SRC)/rtklib.h
binex.o    : $(SRC)/rtklib.h
rt17.o     : $(SRC)/rtklib.h
rtcm.o     : $(SRC)/rtklib.h
rtcm2.o    : $(SRC)/rtklib.h
rtcm3.o    : $(SRC)/rtklib.h
rtcm3e.o   : $(SRC)/rtklib.h
preceph.o  : $(SRC)/rtklib.h

clean:
	rm -f librtk.so *.o *.out *.trace

