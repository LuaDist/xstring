# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(xstring C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

ADD_LUA_MODULE(xstring xstring.c xstring.def)

#2DO-improve: possibly easier if these built Lua modules rather than executables
#IF(BUILD_TESTING)
#		ADD_EXECUTABLE(testxs testxs.c xstring.c) # or use built xstring shared library
#		ADD_EXECUTABLE(xsperf xsperf.c xstring.c)
#		TARGET_LINK_LIBRARIES(testxs ${LUA_LIBRARY})
#		TARGET_LINK_LIBRARIES(xsperf ${LUA_LIBRARY})
#ENDIF(BUILD_TESTING)

INSTALL (TARGETS xstring LIBRARY DESTINATION ${INSTALL_CMOD})
INSTALL (FILES CHANGES LICENSE README DESTINATION ${INSTALL_DATA})
INSTALL (FILES testxs.lua xsperf.lua DESTINATION ${INSTALL_TEST})
