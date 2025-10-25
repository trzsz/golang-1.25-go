LIB_DST := /usr/lib

all: bin/go

bin/go:
	cd src && ./make.bash

clean:
	cd src && ./clean.bash || echo ignore

install: all
	mkdir -p ${DESTDIR}${LIB_DST}/go-1.25
	cp -r api bin misc pkg src test VERSION ${DESTDIR}${LIB_DST}/go-1.25/
