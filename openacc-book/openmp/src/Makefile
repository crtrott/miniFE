#-----------------------------------------------------------------------

MINIFE_TYPES =  \
        -DMINIFE_SCALAR=double   \
        -DMINIFE_LOCAL_ORDINAL=int      \
        -DMINIFE_GLOBAL_ORDINAL=int

MINIFE_MATRIX_TYPE = -DMINIFE_CSR_MATRIX
# MINIFE_MATRIX_TYPE = -DMINIFE_ELL_MATRIX

#-----------------------------------------------------------------------

CFLAGS = -O3 -g
LDFLAGS = 
CFLAGS += -xMIC-AVX512
LDFLAGS += -xMIC-AVX512
CXXFLAGS = $(CFLAGS)
CPPFLAGS = -I. -I../utils -I../fem $(MINIFE_TYPES) $(MINIFE_MATRIX_TYPE) \
	-DMINIFE_REPORT_RUSAGE

CPPFLAGS += -fopenmp
LDFLAGS += -fopenmp
#IBM XL OpenMP 4.5 flags
#CPPFLAGS += -qsmp=omp -qoffload -qnoeh
#LDFLAGS+=-qsmp=omp

LIBS=

CXX=icpc
CC=icc

include make_targets

