#Makefile unmilione fattoriale

CFLAGS= -Wall -pedantic-errors -std=gnu99 -O3
FILE= fact.c
LIBS= -lm
RESULT=unmilione
CHECKFILE=unmilione.sha
CC=gcc

.PHONY: clean test

EXE= fattoriale


$(EXE)	: fact.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

clean:
	-rm -f *.o $(EXE) $(RESULT)


test:	clean
	make $(EXE)
	time ./$(EXE) > $(RESULT)
	shasum -a512 -c $(CHECKFILE) $(RESULT)
