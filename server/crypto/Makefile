#*************************************************************#
#
#   Ensemble, 2_00
#   Copyright 2004 Cornell University, Hebrew University
#           IBM Israel Science and Technology
#   All rights reserved.
#
#   See ensemble/doc/license.txt for further information.
#
#*************************************************************#
#*************************************************************#
#
# Main CRYPTO Makefile
#
# Author: Ohad Rodeh 11/2001
# Based on code by Mark Hayden
#
#*************************************************************#
ENSROOT = ../..

include $(ENSROOT)/mk/config.mk
include $(ENSROOT)/mk/preamble.mk

ifdef OPT
include $(ENSROOT)/mk/ocamlopt.mk
else
include $(ENSROOT)/mk/ocaml.mk
endif
#*************************************************************#

all : fake/cryptokit_int.mli real/cryptokit_int.mli 
	cd fake; $(MAKE)
ifdef CRYPTO
	cd real; $(MAKE)
endif

fake/cryptokit_int.mli : cryptokit_int.mli
	$(CP) cryptokit_int.mli fake/

real/cryptokit_int.mli : cryptokit_int.mli
	$(CP) cryptokit_int.mli real/

clean : 
	$(RM) fake/cryptokit_int.mli real/cryptokit_int.mli 
	$(RM) *.cmi
	cd fake; $(MAKE) clean 
	cd real; $(MAKE) clean 

realclean : clean

#*************************************************************#


