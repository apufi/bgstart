cmake_minimum_required (VERSION 3.21)

project("bgstart")

add_executable (bgstart "bgstart.c" )

set_property(TARGET bgstart PROPERTY C_STANDARD 17)

target_compile_options(bgstart PUBLIC "/TC")
target_compile_options(bgstart PUBLIC "/MT")
target_compile_options(bgstart PUBLIC "/D _WINDOWS")
target_compile_options(bgstart PUBLIC "/D UNICODE")
target_compile_options(bgstart PUBLIC "/D _UNICODE")

#target_link_options(simple PRIVATE -mwindows)

target_link_options(bgstart PRIVATE "/SUBSYSTEM:WINDOWS")
target_link_options(bgstart PRIVATE "/OPT:REF")
#target_link_options(bgstart PRIVATE "/INCREMENTAL:NO")
set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/INCREMENTAL:NO")


