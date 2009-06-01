# $Id: GNUmakefile,v 1.12 2008/06/11 13:12:16 vnivanch Exp $
# --------------------------------------------------------------
# GNUmakefile for examples module.  Gabriele Cosmo, 06/04/98.
# --------------------------------------------------------------

name := test30
G4TARGET := $(name)
G4EXLIB := true

ifndef G4INSTALL
  G4INSTALL = ../../
endif

.PHONY: all 

all: lib bin

ifdef AHSYTEM
  CPPFLAGS += -pg -q
endif

ifdef G4ANALYSIS_USE_ROOT
  CPPFLAGS += -DG4ANALYSIS_USE_ROOT
endif

include $(G4INSTALL)/config/architecture.gmk

ifdef G4ANALYSIS_USE_ROOT
  CPPFLAGS += $(shell root-config --cflags) 
  LDFLAGS  += $(shell root-config --glibs)
else
  CPPFLAGS += $(shell root-config --cflags)
  LDFLAGS  += $(shell root-config --glibs)
endif

include $(G4INSTALL)/config/binmake.gmk

histclean:
	rm -f $(G4WORKDIR)/tmp/$(G4SYSTEM)/$(G4TARGET)/Histo.o
