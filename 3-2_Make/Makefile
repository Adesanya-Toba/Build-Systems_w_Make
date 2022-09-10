# Demonstration Makefile for the Multifile sources in Module 1
# Make format
# target(should be filename, unless phony): prerequisites
#	recipe (action(s) to take)

.PHONY: all

# 'all' will have every target we want to be built by make as a prerequisite
all: multifile_program

multifile_program: multifile_main.c multifile_func.c
	# Building multifile_program
	cc multifile_main.c multifile_func.c -o multifile_program

# Creating a phony target
# First step is to declare the target as a prerequisite of .PHONY
.PHONY: clean

clean:
	rm -f multifile_program

