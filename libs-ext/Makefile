#!/bin/bash

LIB_DIR = libwebsockets 

ALL:
	for dir in $(LIB_DIR); do \
		make -C $$dir; \
	done

install:
ifeq ($(CYGWIN_BUILD),1)
	for dir in $(LIB_DIR); do \
		make -C $$dir install; \
	done
	
	cp libwebsockets/bin/cygwebsockets-8.dll ../build/
else
	cp libwebsockets/lib/libwebsockets.so* ../build/
	sudo cp libwebsockets/lib/libwebsockets.so* /usr/lib/
	for dir in $(LIB_DIR); do \
		sudo make -C $$dir install; \
	done
endif

setup:
	cd libwebsockets/ ;cmake . ;cd ../
	#for dir in $(LIB_DIR); do \
	#	make -C $$dir setup; \
	#done

clean:
	for dir in $(LIB_DIR); do \
		make -C $$dir clean; \
	done

compile:
	for dir in $(LIB_DIR); do \
		make -C $$dir DEBUG=1; \
	done

release:
	for dir in $(LIB_DIR); do \
                make -C $$dir release; \
        done


