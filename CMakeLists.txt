cmake_minimum_required(VERSION 3.1)
project(<project-name> VERSION 0.1.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 14)

### Project options
#option(<project-name>_BUILD_SHARED_LIBS "Build shared libraries" OFF)

### Link third parties here

file(GLOB_RECURSE sources "src/[a-zA-Z]*.cpp")
file(GLOB_RECURSE test_sources "test/[a-zA-Z]*.cpp")

if(VERBOSE)
  message(STATUS "sources: ${sources}")
  message(STATUS "test_sources: ${test_sources}")
endif()

#if (<project-name>_BUILD_SHARED_LIBS)
#  add_library(<lib-name> SHARED ${sources})
#else()
#  add_library(<lib-name> STATIC ${sources})
#endif()

add_executable(<lib-name> ${sources})

target_include_directories(wbc2
  PUBLIC ${PROJECT_SOURCE_DIR}/include
)

#target_link_libraries(<lib-name> ${XXX_LIBRARIES})

#set_target_properties(<project-name> PROPERTIES
#  VERSION "{<project-name>_VERSION}"
#)

###
### Extras
###
add_subdirectory(test)
