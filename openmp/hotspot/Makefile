# C compiler
CC = g++
ICC = gcc
CC_FLAGS = -g -fopenmp -O2 -I../../common -DENABLE_RODINIA_HOOKS
OFFLOAD_CC_FLAGS = -offload-option,mic,compiler,"-no-opt-prefetch"

all: hotspot hotspot_offload 


hotspot: hotspot_openmp.cpp Makefile 
	$(CC) $(CC_FLAGS) hotspot_openmp.cpp -o hotspot 

hotspot_offload: hotspot_openmp.cpp Makefile
	$(ICC) $(CC_FLAGS) $(OFFLOAD_CC_FLAGS) -DOMP_OFFLOAD hotspot_openmp.cpp -o hotspot_offload

clean:
	rm -f hotspot hotspot_offload
