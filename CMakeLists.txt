cmake_minimum_required(VERSION 3.20)

project(zdr-fixed_string
    DESCRIPTION "The nth fixed_string library you've seen"
    VERSION 1.0.0
    LANGUAGES CXX)

if (NOT DEFINED CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 23)
endif()

add_library(fixed_string INTERFACE)
target_include_directories(fixed_string
  INTERFACE
    $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>)

if (NOT CMAKE_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
  add_library(zdr::fixed_string ALIAS fixed_string)
endif()
