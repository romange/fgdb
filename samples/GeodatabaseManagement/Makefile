# Makefile - GeodatabaseManagement

include ../../include/make.include
CC=$(CC)
CXX=$(CX)
CXXFLAGS=$(CFLAGS)
CFLAGS+=-W -fexceptions -D_CONSOLE $(CXDEF) -I../../include $(CXOTHER)
LD=$(CXX) $(CXXFLAGS)
LDFLAGS+= -L../../lib
LIBS+=-lFileGDBAPI
ifndef TARGET
TARGET=../bin/GeodatabaseManagement
endif
.PHONY: all
all: $(TARGET)

%.o: %.cpp
	$(CXX) $(CXXFLAGS) $(CPPFLAGS) -c $<

SOURCE_FILES= \
	./GeodatabaseManagement.cpp

HEADER_FILES= \

SRCS=$(SOURCE_FILES) $(HEADER_FILES)

OBJS=$(SOURCE_FILES:.cpp=.o)

$(TARGET): $(OBJS)
	$(LD) $(LDFLAGS) -o $@ $(OBJS) $(LIBS)

.PHONY: clean
clean:
	-rm -f -v $(OBJS) $(TARGET)
