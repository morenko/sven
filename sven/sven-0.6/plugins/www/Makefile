CC=gcc

OPT=-O2
DEBUG=-g


CFLAGS=$(OPT) $(DEBUG) -fPIC -Wall `../../script/sven-config --cflags`
LIBS= -L../../libsven/.libs -lsven


PLUGIN=www.so
PLUGINDIR= `../../script/sven-config --plugin-dir`

all : $(PLUGIN)

install : $(PLUGIN)
	mkdir -p $(DESTDIR)$(PLUGINDIR)
	install $(PLUGIN) $(DESTDIR)$(PLUGINDIR)


$(PLUGIN) : www.o
	$(CC) -shared $^ -o $@ $(LIBS)


.c.o: $(SRCS)
	$(CC) $(CFLAGS) -c $^ -o $@

distclean :
	rm -f $(PLUGIN) *.o   *.so
	
clean :
	rm -f $(PLUGIN) *.o  *.so


