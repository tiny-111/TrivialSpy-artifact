SHELL=/bin/sh
CLASS=C
VERSION=
SFILE=config/suite.def

default: header is

IS: is		       
is: header	       
	cd IS; $(MAKE) CLASS=$(CLASS)

# It would be nice to make clean in each subdirectory (the targets
# are defined) but on a really clean system this will won't work
# because those makefiles need config/make.def
clean:
	- rm -f core *~ */core */*~
	- rm -f */*.o */*.obj */*.exe */*.mod */npbparams.h */blk_par.h
	- rm -f sys/setparams sys/makesuite sys/setparams.h
	- rm -rf */rii_files

veryclean: clean
	- rm -f config/make.def config/suite.def 
	- rm -f bin/sp.* bin/lu.* bin/mg.* bin/ft.* bin/bt.* bin/is.*
	- rm -f bin/ep.* bin/cg.* bin/ua.* bin/dc.* bin/ADC.*

header:
	@ sys/print_header



