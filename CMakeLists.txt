cmake_minimum_required(VERSION 3.15)
project(RoomCorrector VERSION 1.0.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# JUCE Configuration
add_subdirectory(JUCE)

juce_add_plugin(RoomCorrector
    COMPANY_NAME "RoomCorrector"
    IS_SYNTH FALSE
    NEEDS_MIDI_INPUT FALSE
    NEEDS_MIDI_OUTPUT FALSE
    IS_MIDI_EFFECT FALSE
    EDITOR_WANTS_KEYBOARD_FOCUS FALSE
    COPY_PLUGIN_AFTER_BUILD TRUE
    PLUGIN_MANUFACTURER_CODE "Room"
    PLUGIN_CODE "Rcor"
    FORMATS VST3 Standalone
    PRODUCT_NAME "RoomCorrector")

target_sources(RoomCorrector PRIVATE
    PluginProcessor.cpp
    PluginProcessor.h
    PluginEditor.cpp
    PluginEditor.h
    DSP.h
)

target_compile_features(RoomCorrector PRIVATE cxx_std_17)

target_link_libraries(RoomCorrector PRIVATE
    juce::juce_audio_basics
    juce::juce_audio_devices
    juce::juce_audio_formats
    juce::juce_audio_plugin_client
    juce::juce_audio_processors
    juce::juce_audio_utils
    juce::juce_core
    juce::juce_data_structures
    juce::juce_events
    juce::juce_graphics
    juce::juce_gui_basics
    juce::juce_gui_extra
    juce::juce_dsp
)
