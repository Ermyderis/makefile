CC:=gcc
CFLAGS:=-Wall
LDFLAGS = -shared   
LIB:=calculator.so

SRCS = math_functions.c
OBJS = $(SRCS:.c=.o)
PREFIX?=/usr

all: $(LIB)

$(LIB): $(OBJS)
	$(CC) $(LDFLAGS) -o $@ $^

install: $(LIB)
	install -m 644 math_functions.h $(DESTDIR)/$(PREFIX)/include
unistall:
	$(RM) $(PREFIX)/include/math_functions.h 

clean:
	rm -f $(LIB) $(OBJS)
