# Temporary Makefile just to handle early testing
C_FILES = cidrcalc.c
C_FLAGS = -I../../../include
CLEAN_FILES = ${O_FILES} cidrcalc *core .depend

L_FLAGS = -g -pipe -L../.. -lcidr

.include "../../Makefile.inc"

# This need to be after the include
all build: cidrcalc

LCIDR = ../../libcidr.so

cidrcalc: ${O_FILES} ${LCIDR}
	# this doesn't work on Ubuntu Precise???
	# ${CC} ${L_FLAGS} -o ${@} ${O_FILES}
	${CC} -o cidrcalc cidrcalc.c ${C_FLAGS} ${L_FLAGS}

${LCIDR}:
	(cd ../.. && make)
