cmake_minimum_required(VERSION 3.22)
if(APPLE)
  set(CMAKE_OSX_ARCHITECTURES "arm64;x86_64" CACHE STRING "")
  set(CMAKE_OSX_DEPLOYMENT_TARGET "10.13" CACHE STRING "")
endif()
project(Sandwalker VERSION 1.0.0)
set(CMAKE_CXX_STANDARD 17)

include(FetchContent)
FetchContent_Declare(JUCE
  GIT_REPOSITORY https://github.com/juce-framework/JUCE.git
  GIT_TAG 8.0.4
  GIT_SHALLOW ON)
FetchContent_MakeAvailable(JUCE)

juce_add_plugin(Sandwalker
  COMPANY_NAME "YourName"
  IS_SYNTH TRUE
  NEEDS_MIDI_INPUT TRUE
  PLUGIN_MANUFACTURER_CODE Yrnm
  PLUGIN_CODE Swlk
  FORMATS VST3
  PRODUCT_NAME "Sandwalker")

target_sources(Sandwalker PRIVATE
  Source/PluginProcessor.cpp
  Source/PluginEditor.cpp)

target_compile_definitions(Sandwalker PUBLIC
  JUCE_WEB_BROWSER=0 JUCE_USE_CURL=0 JUCE_VST3_CAN_REPLACE_VST2=0)

target_link_libraries(Sandwalker
  PRIVATE juce::juce_audio_utils juce::juce_dsp
  PUBLIC juce::juce_recommended_config_flags juce::juce_recommended_lib_flags)
