# Temporary Makefile just to handle early testing
C_FILES = mkstr.c
C_FLAGS = -I../../../include
CLEAN_FILES = ${O_FILES} cidr_mkstr *core .depend

L_FLAGS = -g -pipe -L../.. -lcidr

.ifdef USE_DMALLOC
C_FLAGS += -w -I/usr/local/include -DUSE_DMALLOC
L_FLAGS += -L/usr/local/lib -ldmalloc
.endif

.include "../../Makefile.inc"

# This need to be after the include
all build: cidr_mkstr

LCIDR = ../../libcidr.so

cidr_mkstr: ${O_FILES} ${LCIDR}
	${CC} ${L_FLAGS} -o ${@} ${O_FILES}

${LCIDR}:
	(cd ../.. && make)
