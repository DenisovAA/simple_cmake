project(BasicCmake)

cmake_minimum_required(VERSION 3.4 FATAL_ERROR)

set(CMAKE_CONFIG_DIR ${PROJECT_SOURCE_DIR}/config)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)

add_compile_options("-Wall" "-O0")

include_directories(${PROJECT_SOURCE_DIR}/include)

file(GLOB PROJECT_SOURCES "${PROJECT_SOURCE_DIR}/src/*.c")

add_executable(${CMAKE_PROJECT_NAME} ${PROJECT_SOURCES})

# set(PROJECT_LIBRARIES ${PROJECT_SOURCE_DIR}/lib)
# target_link_libraries(${CMAKE_PROJECT_NAME} ${PROJECT_LIBRARIES})

#[[
if(DOCS)
        find_package(Doxygen REQUIRED)

        add_custom_target(
            docs
            COMMAND ${DOXYGEN_EXECUTABLE} ${PROJECT_SOURCE_DIR}/docs/Doxyfile
            WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/docs
            COMMENT "Generating API documentation with Doxygen"
            VERBATIM
        )
endif() ]]
