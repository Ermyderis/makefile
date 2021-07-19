CC:=gcc
CFLAGS:=-Wall
LDFLAGS = -shared   
LIB:=calculator.so

SRCS = math_functions.c
OBJS = $(SRCS:.c=.o)

all: $(LIB)

$(LIB): $(OBJS)
	$(CC) $(LDFLAGS) -o $@ $^

install: $(LIB)
	install -m 644 math_functions.h $(DESTDIR)/$(PREFIX)/include //pataisyt

unistall:

clean:
	rm -f $(LIB) $(OBJS)
