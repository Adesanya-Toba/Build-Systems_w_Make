# Demonstration Makefile for the Multifile sources in Module 1
# Make format
# target(should be filename, unless phony): prerequisites
#	recipe (action(s) to take)

.PHONY: all static_lib shared_lib

# 'all' will have every target we want to be built by make as a prerequisite
all: multifile_program static_lib shared_lib

multifile_program: multifile_main.c multifile_func.c
	# Building multifile_program
# Using automatic variables
# $^ corresponds to all the prerequisites with file extensions with spaces between them
# $@ corresponds to the target for the given rule
	cc $^ -o $@

static_lib:
	cc -c multifile_func.c -o multifile_func.o
	ar rcs libmultifile_func.a multifile_func.o

shared_lib:
	cc -fPIC -c multifile_func.c -o multifile_func_pic.o
	cc -shared multifile_func_pic.o -o libmultifile_func_dyn.so

# Creating a phony target
# First step is to declare the target as a prerequisite of .PHONY
.PHONY: clean

clean:
	rm -f *.o *.a *.so
	rm -f multifile_program
# rm -f multifile_program multifile_func.o libmultifile_func_dyn.so libmultifile_func.a multifile_func_pic.o

