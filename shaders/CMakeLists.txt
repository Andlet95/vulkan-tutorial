cmake_minimum_required(VERSION 4.0)

configure_file(shader.frag shader.frag COPYONLY)
configure_file(shader.vert shader.vert COPYONLY)
configure_file(compile.sh compile.sh COPYONLY)

execute_process(COMMAND ./compile.sh WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})
