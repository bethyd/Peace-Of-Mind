cmake_minimum_required (VERSION 3.8)
project(PeaceOfMind)

include_directories(src)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -g")

file (GLOB_RECURSE SRC src/*.cpp)

if (CMAKE_SYSTEM_NAME MATCHES "Windows")
        link_libraries(opengl32 glew32)
endif()
if (CMAKE_SYSTEM_NAME    MATCHES "Linux")
        link_libraries(GL GLEW pthread)
endif()
link_libraries(sfml-system sfml-window sfml-graphics)

add_executable(PeaceOfMind ${SRC})
