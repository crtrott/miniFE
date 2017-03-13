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
#KNL
#CFLAGS += -xMIC-AVX512
#LDFLAGS += -xMIC-AVX512
#Power8
CFLAGS += -mcpu=power8 -mtune=power8
LDFLAGS += -mcpu=power8 -mtune=power8
CXXFLAGS = $(CFLAGS)
CPPFLAGS = -I. -I../utils -I../fem $(MINIFE_TYPES) $(MINIFE_MATRIX_TYPE) \
	-DMINIFE_REPORT_RUSAGE

#Intel compiler and GCC
#CPPFLAGS += -fopenmp
#LDFLAGS += -fopenmp
#KNL
#CPPFLAGS += -DMINIFE_NUM_TEAMS=64 -DMINIFE_TEAM_SIZE=4
#CXX=icpc
#CC=icc

#IBM XL OpenMP 4.5 flags
CPPFLAGS += -DMINIFE_NUM_TEAMS=1024 -DMINIFE_TEAM_SIZE=128 -qsmp=omp -qoffload -qnoeh
LDFLAGS+=-qsmp=omp
CXX = xlc++
CC = xlc

LIBS=


include make_targets

