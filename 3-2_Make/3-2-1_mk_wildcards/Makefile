.PHONY: all

OBJ_FILES = *.o

all: *.o

# Rule to compile all .c files into .o (object) files using wildcards
OBJ_FILES : %.c
	$(CC) -c $*.c -o $@.o

clean:
	$(RM) *.o
