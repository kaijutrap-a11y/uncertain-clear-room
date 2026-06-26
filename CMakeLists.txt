cmake_minimum_required(VERSION 3.15)
project(RoomCorrector VERSION 1.0.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Create a dummy library/executable for now
# This is just to make the build work
add_library(RoomCorrector STATIC
    PluginProcessor.cpp
    PluginEditor.cpp
)

target_include_directories(RoomCorrector PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_compile_features(RoomCorrector PRIVATE cxx_std_17)

# If JUCE is available, we can add it
# include(FetchContent)
# FetchContent_Declare(JUCE
#     GIT_REPOSITORY https://github.com/juce-framework/JUCE.git
#     GIT_TAG latest
# )
# FetchContent_MakeAvailable(JUCE)
