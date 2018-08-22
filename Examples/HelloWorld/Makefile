#
P = ../../Pokitto
P_SIM = $(P)/POKITTO_SIM
P_CORE = $(P)/POKITTO_CORE
P_LIBS = $(P)/POKITTO_LIBS

POKITTO_SIM = \
	$(P_SIM)/Pokitto_joystick.o \
	$(P_SIM)/PokittoClock.o \
	$(P_SIM)/PokittoSimButtons.o \
	$(P_SIM)/PokittoSimCore.o \
	$(P_SIM)/PokittoSimSound.o \
	$(P_SIM)/PokittoSimulator.o \
	$(P_SIM)/SimSound.o \
	$(P_SIM)/SimEEPROM.o \
	$(P_SIM)/SimLCD.o \
	$(P_SIM)/WriteWav.o

POKITTO_CORE = \
	$(P_CORE)/PokittoCore.o \
	$(P_CORE)/PokittoLogos.o \
	$(P_CORE)/PokittoSound.o \
	$(P_CORE)/PokittoBattery.o \
	$(P_CORE)/PokittoButtons.o \
	$(P_CORE)/PokittoDisplay.o \
	$(P_CORE)/PokittoPalette.o \
	$(P_CORE)/PokittoBacklight.o \
	$(P_CORE)/FONTS/fontC64UIGfx.o \
	$(P_CORE)/FONTS/font5x7.o \
	$(P_CORE)/FONTS/fontC64.o \
	$(P_CORE)/PALETTES/palCGA.o

POKITTO_LIBS = \
	$(P_LIBS)/FileIO/FileIO_SIM.o \
	$(P_LIBS)/Synth/Synth.o \
	$(P_LIBS)/Synth/Synth_oscfuncs.o \
	$(P_LIBS)/Synth/Synth_wavefuncs.o \
	$(P_LIBS)/Synth/Synth_envfuncs.o \
	$(P_LIBS)/Synth/Synth_helpers.o \
	$(P_LIBS)/Synth/Synth_mixfuncs.o

CFLAGS = -DPOK_SIM \
	-Wno-c++11-compat-deprecated-writable-strings \
	-I. \
	-I$(P) \
	-I$(P_CORE) \
	-I$(P_LIBS)/FileIO \
	-I$(P_LIBS)/ImageFormat \
	-I$(P_LIBS)/Synth \
	-I$(P_SIM) \
	-I$(P_SIM)/mbed_sim \
	-I$(P_SIM)/tinydir

HelloWorld: main.o $(POKITTO_SIM) $(POKITTO_CORE) $(POKITTO_LIBS)
	g++ $(LDFLAGS) -o $@ $^ -L/usr/local/Cellar/sdl2/2.0.7/lib -lSDL2

.cpp.o:
	$(COMPILE.cpp) $(CFLAGS) -o $@ $<
