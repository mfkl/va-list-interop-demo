cmake_minimum_required(VERSION 3.5)
project(nativeLibrary)
if (MSVC)
	add_library(nativeLibrary SHARED library.c)
endif (MSVC)

if (UNIX)
	add_library(nativeLibrary.x64 SHARED library.c)
	add_library(nativeLibrary.x86 SHARED library.c)
    set_target_properties(nativeLibrary.x86 PROPERTIES COMPILE_FLAGS "-m32" LINK_FLAGS "-m32")
endif (UNIX)

