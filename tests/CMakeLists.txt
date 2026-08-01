#-----------------------------------------------------------------------------------------------------------------------
# Google Test
#-----------------------------------------------------------------------------------------------------------------------
include(GoogleTest)
enable_testing()

#-----------------------------------------------------------------------------------------------------------------------
# Target: cpp_forward_list_test
# Alias: collections::cpp_forward_list_test
# Type: Executable
# Dependencies: GTest::gtest_main, GTest::gmock_main, collections::cpp_forward_list_headers
#-----------------------------------------------------------------------------------------------------------------------
# Target definition
add_executable(cpp_forward_list_test)

# Target alias
add_executable(collections::cpp_forward_list_test ALIAS cpp_forward_list_test)

# Target sources
target_sources(cpp_forward_list_test
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/cpp_forward_list_test.cpp
)

# Target dependencies
target_link_libraries(cpp_forward_list_test
    PRIVATE
        collections::cpp_forward_list_headers
        GTest::gtest_main
        GTest::gmock_main
)

# Test discovery
gtest_discover_tests(cpp_forward_list_test)