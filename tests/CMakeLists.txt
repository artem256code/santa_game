cmake_minimum_required(VERSION 3.5)

project(tests LANGUAGES CXX)

add_definitions(-DGTEST_LANGUAGE_CXX11)

find_package(Threads REQUIRED)

set(GOOGLETEST_DIR ../googletest)
set(GTestFiles ${GOOGLETEST_DIR}/googletest/src/gtest-all.cc)
set(GTestIncludes ${GOOGLETEST_DIR}/googletest/ ${GOOGLETEST_DIR}/googletest/include)

include_directories(${GTestIncludes})

add_executable(add      main.cpp
                        ${GTestFiles})

target_link_libraries(add PRIVATE Threads::Threads)

