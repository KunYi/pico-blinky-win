
cmake_minimum_required(VERSION 3.13)

# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake)

project(blinky)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

add_executable(blinky
        blinky.c
        )

# pull in common dependencies
target_link_libraries(blinky pico_stdlib)

# create map/bin/hex file etc.
pico_add_extra_outputs(blinky)
