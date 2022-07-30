# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/pgm/pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(logic-analyser C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(logic-analyser logic-analyser.cpp )

pico_set_program_name(logic-analyser "logic-analyser")
pico_set_program_version(logic-analyser "0.1")

pico_enable_stdio_uart(logic-analyser 1)
pico_enable_stdio_usb(logic-analyser 1)

# Add the standard library to the build
target_link_libraries(logic-analyser pico_stdlib)

# Add any user requested libraries
target_link_libraries(logic-analyser
        hardware_dma
        hardware_pio
        hardware_timer
        hardware_watchdog
        hardware_clocks
        )

pico_add_extra_outputs(logic-analyser)

