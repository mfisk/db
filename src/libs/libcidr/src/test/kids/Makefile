# Temporary Makefile just to handle early testing
C_FILES = kids.c
C_FLAGS = -I../../../include
CLEAN_FILES = ${O_FILES} cidr_kids *core .depend

L_FLAGS = -g -pipe -L../.. -lcidr

.include "../../Makefile.inc"

# This need to be after the include
all build: cidr_kids

LCIDR = ../../libcidr.so

cidr_kids: ${O_FILES} ${LCIDR}
	${CC} ${L_FLAGS} -o ${@} ${O_FILES}

${LCIDR}:
	(cd ../.. && make)
