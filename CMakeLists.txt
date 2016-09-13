cmake_minimum_required(VERSION 2.8.11) 

project(mpiavconvert)

# Build FFmpeg
include(ExternalProject)
ExternalProject_Add(ffmpeg
    SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/FFmpeg
    CONFIGURE_COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/FFmpeg/configure --prefix=${CMAKE_BUILD_DIR}/ffmpeg --enable-libass --enable-libfdk-aac --enable-libfreetype --enable-libmp3lame --enable-libopus --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libx265 --enable-libxvid --enable-nonfree --enable-gpl
    PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/FFmpeg
    BUILD_COMMAND make
    BUILD_IN_SOURCE 1
)

# Build avTranscoder
set(AVTRANSCODER_DISABLE_APPS 1)
set(AVTRANSCODER_DISABLE_BINDINGS 1)
add_subdirectory(avTranscoder)
