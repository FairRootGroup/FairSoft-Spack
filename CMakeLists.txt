project(FAIRSOFT)

cmake_minimum_required(VERSION 3.0)

enable_testing()

set(SPACK_DIR $ENV{SPACK_DIR})
set(FAIRROOT_VERSION $ENV{FAIRROOT_VERSION})
set(SPACK_EXTRA_FLAGS $ENV{SPACK_EXTRA_FLAGS})

configure_file(${CMAKE_SOURCE_DIR}/test/cmaketest.sh.in ${CMAKE_BINARY_DIR}/test/cmaketest.sh)
add_test(NAME build_fairroot_spack COMMAND ${CMAKE_BINARY_DIR}/test/cmaketest.sh)
set_tests_properties(build_fairroot_spack PROPERTIES TIMEOUT 14400)

