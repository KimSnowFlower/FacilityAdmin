cmake_minimum_required(VERSION 3.21)
project(FacilityAdmin LANGUAGES CXX)

# Qt 자동 처리
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

# src/ui/ 에 있는 .ui를 uic가 찾도록
set(CMAKE_AUTOUIC_SEARCH_PATHS
    ${CMAKE_SOURCE_DIR}/src/ui
)

# C++ 표준
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Qt 모듈
find_package(Qt6 REQUIRED COMPONENTS Widgets Network Sql Test)

# 하위 디렉토리
add_subdirectory(src)
#add_subdirectory(tests)
