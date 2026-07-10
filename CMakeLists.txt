cmake_minimum_required(VERSION 3.20)

project(lingmo-apps-common VERSION 1.0.0 DESCRIPTION "Lingmo Apps Common" LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Quick)

add_library(lingmo-apps-common SHARED
    src/main.cpp
)
target_compile_definitions(lingmo-apps-common PRIVATE LINGMO_APPS_COMMON_LIBRARY)

target_link_libraries(lingmo-apps-common PUBLIC
    Qt6::Core
    Qt6::Quick
)

install(TARGETS lingmo-apps-common
    EXPORT lingmo-apps-commonTargets
    LIBRARY DESTINATION 
    ARCHIVE DESTINATION 
)

install(DIRECTORY include/lingmo-apps-common
    DESTINATION 
)
