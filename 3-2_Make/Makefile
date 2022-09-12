# Demonstration Makefile for the Multifile sources in Module 1
# Make format
# target(should be filename, unless phony): prerequisites
#	recipe (action(s) to take)

.PHONY: all static_lib shared_lib

MULTIFILE_SRC = multifile_func.c
MULITFUNC = multifile_func

MULTIFILE_SRCS = multifile_main.c multifile_func.c

STATIC_LIBFLAGS := fPIC
SHARED_LIBFLAGS := rcs
SHARED := shared


# 'all' will have every target we want to be built by make as a prerequisite
all: multifile_program static_lib shared_lib

multifile_program: $(MULTIFILE_SRCS)
	# Building multifile_program
# Using automatic variables
# $^ corresponds to all the prerequisites with file extensions with spaces between them
# $@ corresponds to the target for the given rule
	$(CC) $^ -o $@

static_lib: $(MULTIFILE_SRC)
	$(CC) -c $^ -o $(MULITFUNC).o
	$(AR) $(SHARED_LIBFLAGS) lib$(MULITFUNC).a $(MULITFUNC).o

shared_lib: $(MULTIFILE_SRC)
	$(CC) -$(STATIC_LIBFLAGS) -c $^ -o $(MULITFUNC)_pic.o
	$(CC) -$(SHARED) $(MULITFUNC)_pic.o -o libmultifile_func_dyn.so

# Creating a phony target
# First step is to declare the target as a prerequisite of .PHONY
.PHONY: clean

clean:
	$(RM) *.o *.a *.so
	$(RM) multifile_program
# rm -f multifile_program multifile_func.o libmultifile_func_dyn.so libmultifile_func.a multifile_func_pic.o

