# ============ 코어 라이브러리 ============
add_library(corelib STATIC
    #${CMAKE_CURRENT_SOURCE_DIR}/domain/Placeholder.cpp
    #${CMAKE_CURRENT_SOURCE_DIR}/app/Placeholder.cpp
    #${CMAKE_CURRENT_SOURCE_DIR}/infra/Placeholder.cpp
)

target_include_directories(corelib PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/domain
    ${CMAKE_CURRENT_SOURCE_DIR}/app
    ${CMAKE_CURRENT_SOURCE_DIR}/infra
)

target_link_libraries(corelib PUBLIC
    Qt6::Core Qt6::Network Qt6::Sql
)

# ============ 실행 파일 ============
set(APP_NAME FacilityAdmin)

add_executable(${APP_NAME}
    ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ui/MainWindow.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ui/MainWindow.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ui/MainWindow.ui
    # ${PROJECT_SOURCE_DIR}/res/resources.qrc
)

target_include_directories(${APP_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/ui
    ${CMAKE_CURRENT_SOURCE_DIR}/domain
    ${CMAKE_CURRENT_SOURCE_DIR}/app
    ${CMAKE_CURRENT_SOURCE_DIR}/infra
)

target_link_libraries(${APP_NAME} PRIVATE Qt6::Widgets corelib)

if (WIN32)
  set_target_properties(${APP_NAME} PROPERTIES WIN32_EXECUTABLE TRUE)
endif()
