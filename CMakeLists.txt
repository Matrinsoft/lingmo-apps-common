cmake_minimum_required(VERSION 3.20)

project(lingmo-apps-common VERSION 1.0.0 DESCRIPTION "Lingmo Apps Common" LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Quick)

add_library(lingmo-apps-common SHARED
    src/main.cpp
)

target_link_libraries(lingmo-apps-common PUBLIC
    Qt6::Core
    Qt6::Quick
)

include(GenerateExportHeader)
generate_export_header(lingmo-apps-common
    EXPORT_MACRO_NAME LINGMO_LINGMO_APPS_COMMON_EXPORT
    EXPORT_FILE_NAME /export.h
)

install(TARGETS lingmo-apps-common
    EXPORT lingmo-apps-commonTargets
    LIBRARY DESTINATION 
    ARCHIVE DESTINATION 
)

install(DIRECTORY include/lingmo-apps-common
    DESTINATION 
)
