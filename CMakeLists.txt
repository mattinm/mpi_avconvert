cmake_minimum_required(VERSION 2.8.11) 

project(AvTranscoder)

# Define AvTranscoder default path to profiles
add_definitions(-DAVTRANSCODER_DEFAULT_AVPROFILES="${CMAKE_INSTALL_PREFIX}/share/avprofiles")

# Build avTranscoder
set(AVTRANSCODER_DISABLE_APPS 1)
set(AVTRANSCODER_DISABLE_BINDINGS 1)
add_subdirectory(avTranscoder)
