cmake_minimum_required(VERSION 3.10)

# Set the project name
project(mmwave)

# Add the source files
file(GLOB_RECURSE SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/ti/mmwavelink/src/*.c
                          ${CMAKE_CURRENT_SOURCE_DIR}/ti/ethernet/src/*.c
                          ${CMAKE_CURRENT_SOURCE_DIR}/ti/mmwave/*.c
                          ${CMAKE_CURRENT_SOURCE_DIR}/opt/*.c
                          ${CMAKE_CURRENT_SOURCE_DIR}/toml/*.c
                          ${CMAKE_CURRENT_SOURCE_DIR}/mimo_ros.cpp
                          )

# Create the executable
add_executable(mmwave ${SOURCES})

# Set additional compiler flags if needed
# target_compile_options(mmwave PRIVATE ...)

# Set additional include directories if needed
# target_include_directories(mmwave PRIVATE ...)

# Set additional linker flags if needed
# target_link_options(mmwave PRIVATE ...)

# Set additional libraries if needed
# target_link_libraries(mmwave PRIVATE ...)

#add pthread and math library
target_link_libraries(mmwave pthread m)

# Set the output directory for the executable
set_target_properties(mmwave PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/output)

# Optional: Install the executable to /usr/bin
# install(TARGETS mmwave DESTINATION /usr/bin)

# Optional: Clean the build artifacts
# add_custom_target(clean COMMAND ${CMAKE_COMMAND} -E remove_directory ${CMAKE_CURRENT_SOURCE_DIR}/output)
