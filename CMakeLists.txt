project(pvr.tvmosaic)

cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(mrmc REQUIRED)
find_package(mrmcplatform REQUIRED)
find_package(platform REQUIRED)
find_package(TinyXML2 REQUIRED)

include_directories(${mrmcplatform_INCLUDE_DIRS}
                    ${platform_INCLUDE_DIRS}
                    ${KODI_INCLUDE_DIR}
                    ${TINYXML2_INCLUDE_DIRS}
                    ${PROJECT_SOURCE_DIR}/lib)

add_definitions(-D__STDC_FORMAT_MACROS)

set(DVBLINK_SOURCES src/base64.cpp
                    src/client.cpp
                    src/DVBLinkClient.cpp
                    src/HttpPostClient.cpp
                    src/RecordingStreamer.cpp
                    src/TimeShiftBuffer.cpp)

add_subdirectory(lib/libdvblinkremote)
set(DEPLIBS ${platform_LIBRARIES} dvblinkremote ${TINYXML2_LIBRARIES})
build_addon(pvr.tvmosaic DVBLINK DEPLIBS)

include(CPack)
