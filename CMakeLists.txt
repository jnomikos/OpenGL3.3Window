cmake_minimum_required(VERSION 3.2)
project(OpenGLPractice)

# set project variables
set(ldir ${CMAKE_CURRENT_SOURCE_DIR}/libs)

# find packages here

# includes
include_directories(${ldir})
include_directories(${ldir}/glfw/include)
include_directories(${ldir}/glad/include)

# find header & source
file(GLOB_RECURSE HEADER "include/*.h")
file(GLOB_RECURSE SOURCE "src/*.cpp")

add_executable(${PROJECT_NAME}
    ${SOURCE}
    ${HEADER}
)

source_group("Header include" FILES ${HEADER})
source_group("Source src"     FILES ${SOURCE})

# link libs
target_link_libraries(${PROJECT_NAME}
    PRIVATE
    ${ldir}/glfw/src/libglfw.so
)