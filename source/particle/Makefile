######################################################################
# Particle System API
#
# Copyright 1998 by David K. McAllister.
#
######################################################################

C++ = g++

GLUT_HOME  =/usr/local/contrib/unmoderated

MP = #-mp -DPARTICLE_MP

# Make it real fast on an Origin 2000.
#LNO =-LNO:opt=1:fusion=2:fission=2:fusion_peeling_limit=2048:cs1=32K:cs2=8M
COPT = $(MP) -O3 $(LNO)  -fPIC

CFLAGS = $(COPT) $(COMPFLAGS) -I. -I.. -I$(GLUT_HOME)/include -I/usr/include/c++/4.8/

POBJS =action_api.o actions.o opengl.o system.o

ALL = libparticleMP.a SPDir

all: $(ALL)

# following line needed for c++ .cc files
.SUFFIXES	: .cpp

.cpp.o:
	$(C++) $(CFLAGS) -c $<

libparticleMP.a: $(POBJS)
	rm -f $@
	ar clq $@ $(POBJS)

SPDir:
	(cd SP ; smake)

clean:
	(cd SP ; smake clean)
	rm -f libpar*
	rm -f *.o
	rm -rf *ii_files
