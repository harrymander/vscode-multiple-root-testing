cmake_minimum_required(VERSION 3.25 FATAL_ERROR)

project(Gtest1 LANGUAGES CXX)

enable_testing()

include(FetchContent)

fetchcontent_declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG b796f7d44681514f58a683a3a71ff17c94edb0c1
)
fetchcontent_makeavailable(googletest)

include(GoogleTest)

add_executable(test-example1 test.cpp)
target_link_libraries(test-example1 PRIVATE GTest::gtest_main)
gtest_discover_tests(test-example1)
