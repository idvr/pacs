BASE	= $(PWD)
CPP   	= g++

CXXFLAGS = -Wall -g
# -g       generate code suitable for the debugger
# -p       generate code suitable for the profiler
# -O       attemp code optimizations

SRCS	= $(wildcard *.cpp)
HDRS 	= $(wildcard *.hpp)
OBJS 	= $(SRCS:.cpp=.o)

LIBDIR  = $(PWD)/../lib

LIBNAME = $(LIBDIR)/librootfinding.a

DEPEND= makedepend $(CFLAGS)

.PHONY : default clean depend

default: $(LIBNAME)($(OBJS))

clean:
	for dustfile in $(OBJS); do \
	!( test -e $$dustfile ) || rm $$dustfile; \
	done

depend: $(SRCS)
	$(DEPEND) -Y. $(SRCS)

# DO NOT DELETE THIS LINE -- make depend depends on it.

bisection.o: bisection.hpp iterativeMethod.hpp rootfinding.hpp
iterativeMethod.o: iterativeMethod.hpp rootfinding.hpp
newton.o: newton.hpp iterativeMethod.hpp rootfinding.hpp
robust.o: robust.hpp iterativeMethod.hpp rootfinding.hpp bisection.hpp
robust.o: newton.hpp
