CC:=gcc
CFLAGS:=-Wall
LIB_FLAGS:= -shared

BIN:=main
BIN_SRC:=main.c
BIN_OBJ:=$(BIN_SRC:.c=.o)

LIB:=file_reader.so
LIB_SRCS:= file_reader.c
LIB_OBJS:=$(LIB_SRCS:.c=.o)
PREFIX?=/usr

.PHONY: all clean

all: $(LIB) $(BIN)

$(LIB):$(LIB_OBJS)
	$(CC) $(CFLAGS) $(LIB_FLAGS) -o $(LIB) $^

$(BIN): $(BIN_SRC) 
	$(CC) $(CFLAGS) -c $(BIN_SRC)
	$(CC) $(CFLAGS) -o $(BIN) $(BIN_SRC) $(LIB_OBJS)

lib: $(LIB_OBJS)
	$(CC) $(CFLAGS) $(LIB_FLAGS) -o $(LIB) $^
#sioje uzduotyje install nereikejo nes naudojamos include " " bet jei butu naudojami < > butu reikeja
install:
	install -d $(PREFIX)/lib $(PREFIX)/include $(PREFIX)/bin
	install -m 644 $(LIB) $(PREFIX)/lib
	install -m 644 file_reader.h $(PREFIX)/include

uninstall:
	$(RM) $(PREFIX)/lib/$(LIB)
	$(RM) $(PREFIX)/include/file_reader.h


clean:
	rm -f $(LIB) $(LIB_OBJS) $(BIN_OBJ) $(BIN)

