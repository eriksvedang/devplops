# Makefile

```
CFLAGS=
LDFLAGS=
LDLIBS=
FILES=main.c
EXECUTABLE=main

all: main.o
	clang $(FILES) -Wall -g -o $(EXECUTABLE) $(CFLAGS) $(LDFLAGS) $(LDLIBS)

run:
	./$(EXECUTABLE)
```


