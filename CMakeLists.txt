cmake_minimum_required(VERSION 3.0)
project(Elegy LANGUAGES CXX)

# Main functionality
add_library(elegy_core SHARED source/core.cpp)

# Elegy daemon
add_executable(elegy_daemon source/daemon.cpp)
target_link_libraries(elegy_daemon PUBLIC elegy_core)

# Communication with the Elegy daemon, running standalone requests, indexing
add_executable(elegy source/interface.cpp)
target_link_libraries(elegy PUBLIC elegy_core)

# Telegram daemon, communication between TDlib and the Elegy daemon
find_package(Td)
if (Td_FOUND)
    add_executable(elegy_telegram_daemon source/telegram_daemon.cpp)
endif()