enable_testing()

add_executable(FacilityAdminTests
    ${CMAKE_SOURCE_DIR}/tests/test_main.cpp
)

target_include_directories(FacilityAdminTests PRIVATE
    ${CMAKE_SOURCE_DIR}/src
)

target_link_libraries(FacilityAdminTests PRIVATE
    Qt6::Test
    corelib
)

add_test(NAME FacilityAdminTests COMMAND FacilityAdminTests)
