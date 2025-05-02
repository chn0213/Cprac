cmake_minimum_required(VERSION 3.30)
project(Cprac C)

set(CMAKE_C_STANDARD 11)

set(UHASH_INCLUDE_DIR "D:/Clibs/Uthash/uthash/src")
include_directories(${UHASH_INCLUDE_DIR})

file (GLOB_RECURSE files *.c)
foreach (file ${files})
    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})
    add_executable (${exe} ${file})
    target_include_directories(${exe} PRIVATE ${UHASH_INCLUDE_DIR})
    message (\ \ \ \ --\ src/${exe}.c\ will\ be\ compiled\ to\ bin/${exe})
endforeach ()